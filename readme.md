# Project Documentation: Automated Deployment of Socks Shop Microservices on Kubernetes

**Objective:**
The goal of this project was to deploy a microservices-based application, specifically the Socks Shop, using Infrastructure as Code (IaaC) for rapid and reliable deployment on Kubernetes. This documentation outlines the tools and technologies used, the deployment process, and the achieved outcomes.

**Tools and Technologies Used:**

1. **Terraform:**
   - **Purpose:** Terraform was chosen for managing infrastructure configurations due to its declarative syntax and support for various cloud providers.
   - **Achievement:** Terraform enabled the provisioning of infrastructure components on AWS, including the Kubernetes cluster.

2. **Amazon Web Services (AWS):**
   - **Purpose:** AWS was selected as the Infrastructure as a Service (IaaS) provider for hosting the Kubernetes cluster and other necessary resources.
   - **Achievement:** An EC2 instance (t2 medium) was created in the eu-west-2 region to serve as the deployment environment.

3. **AWS ACM Certificate (ACL Certificate):**
   - **Purpose:** An ACL certificate from AWS Certificate Manager (ACM) was used for securing the application over HTTPS, as it integrates seamlessly with other AWS services.
   - **Achievement:** The ACL certificate was requested to encrypt the communication between the client and the Socks Shop application.

4. **Jenkins:**
   - **Purpose:** Jenkins was utilized as the continuous integration and continuous deployment (CI/CD) tool for automating the deployment pipeline.
   - **Achievement:** Jenkins facilitated the creation of a CI/CD pipeline for building and deploying the Socks Shop application on the Kubernetes cluster.

5. **Route 53:**
   - **Purpose:** Route 53, AWS's DNS web service, was used for managing domain names and routing traffic to the deployed application.
   - **Achievement:** A DNS hosted zone was created on Route 53 to associate the Socks Shop application with the domain name "sock-shop.toluwanimi.com.ng".

6. **Grafana:**
   - **Purpose:** Grafana was employed for monitoring and visualizing metrics collected from the Kubernetes cluster and applications.
   - **Achievement:** Grafana provided insights into the performance and health of the deployed resources, including CPU usage and pod status.

7. **Nginx:**
   - **Purpose:** Nginx served as the ingress controller for routing external traffic to the Socks Shop application running on Kubernetes.
   - **Achievement:** Nginx facilitated the secure and efficient handling of incoming requests to the application.

**Deployment Process and Achievements:**

1. **Infrastructure Setup:**
   - A Terraform script was used to provision the required infrastructure components on AWS, including the Kubernetes cluster and EC2 instance.

2. **Jenkins Configuration:**
   - Jenkins was set up by accessing the EC2 instance via "EC2 instance connect" and configuring it to run on port 8080.
   - Proxy compatibility was enabled in Jenkins for seamless integration with the deployment environment.

3. **CI/CD Pipeline Creation:**
   - GitHub credentials were added to Jenkins to access the source code repository.
   - AWS access key and secret access key credentials were configured in Jenkins for interaction with AWS services.
   - A build pipeline for deploying the EKS cluster was created in Jenkins, automating the deployment process.

4. **Application Deployment:**
   - The Socks Shop application and Grafana were deployed on the Kubernetes cluster using Jenkins and Helm charts.

5. **SSL/TLS Encryption:**
   - An ACL certificate was requested from AWS ACM for securing the application over HTTPS.
   - A DNS hosted zone was created on Route 53 to map the domain name to the deployed application.

6. **Monitoring and Logging:**
   - Grafana was used to monitor CPU usage and pod status, providing insights into the performance of the deployed resources.

7. **Attached Images:**
   - Below is a picture of the stage view on Jenkins.
![stage view](/images/2024-03-20%20(6).png)

- Below is a picture of my sock-shop application.
![sock shop](/images/2024-03-20%20(7).png)

- Below is a picture of Grafana coming up.
![Grafana](/images/2024-03-21.png)

- Below is a picture of Grafana monitoring the CPU usage.
![CPU Usage](/images/2024-03-21%20(2).png)

- Below is a picture of ACL certificate issuance from AWS ACM.
![ACL certificate](/images/2024-03-21%20(7).png)

**Challenges Faced:**

- **Certificate Encryption Issue:**
Despite the issuance of the ACL certificate by AWS, encryption of the sites was not achieved.
Investigation into the root cause of the encryption failure was inconclusive, leading to unresolved issues.

**Conclusion:**

In conclusion, the deployment of the Socks Shop microservices application on Kubernetes using automated tools and technologies such as Terraform, Jenkins, and AWS was successfully accomplished. While certain challenges were encountered, including the SSL/TLS encryption issue, the project demonstrated the effectiveness of Infrastructure as Code and CI/CD practices in achieving rapid and reliable deployment of microservices-based applications. Ongoing efforts will be directed towards resolving outstanding issues and optimizing the deployment process for future projects.
