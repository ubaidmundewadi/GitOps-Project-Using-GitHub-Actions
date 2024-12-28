# GitOps Project Using GitHub Actions

## Overview
In this project, we implemented a complete GitOps approach to manage both infrastructure and application workflows using GitHub Actions. The goal was to automate the provisioning of infrastructure and the deployment of applications on AWS Cloud while ensuring that all changes were version-controlled and reviewed before being applied. The following sections outline the details of the workflows and the tools used in this project.

---

## Workflows
### 1. **Infrastructure Workflow**

#### Objective:
Provision and manage AWS infrastructure, including a VPC and an Amazon EKS cluster with two managed node groups, using Terraform.

#### Workflow Details:
- **Branches**:
  - **Staging Branch**: Used for testing infrastructure changes in a staging environment.
  - **Main Branch**: Used for applying approved changes to the production environment.
- **Steps**:
  1. Fetch the staging branch.
  2. Run Terraform `plan` to validate the proposed changes.
  3. After approval, merge the changes into the main branch.
  4. Apply the changes using Terraform `apply`.
- **Terraform Configuration**:
  - Utilized Terraform modules for simplicity and reusability.
  - Created a VPC and an Amazon EKS cluster with 2 managed node groups.

#### Tools Used:
- **Terraform**: For infrastructure as code.
- **GitHub Actions**: For CI/CD pipeline.
- **AWS Cloud**: For infrastructure provisioning.

---

### 2. **Application Workflow**

#### Objective:
Perform unit testing, code analysis, containerize the application, and deploy it to the EKS cluster.
Repository URL: https://github.com/ubaidmundewadi/vprofile-action.git

#### Workflow Details:
- **Steps**:
  1. Perform unit tests to validate application functionality.
  2. Run code quality and security checks using SonarQube.
  3. Build the Docker image of the application.
  4. Push the Docker image to the Amazon ECR repository.
  5. Deploy the application to the Amazon EKS cluster using Helm.

#### Tools Used:
- **SonarQube**: For code analysis and quality checks.
- **Docker**: For containerizing the application.
- **Amazon ECR**: For storing Docker images.
- **Helm**: For deploying the application to the Kubernetes cluster.
- **GitHub Actions**: For CI/CD pipeline.

---

## GitOps Approach
We adhered strictly to the GitOps principles throughout this project:
- All changes, whether for infrastructure or applications, were made via Git pull requests to ensure proper review and approval.
- Avoided manual intervention to eliminate configuration drift and maintain consistency.
- GitHub Actions workflows ensured automated testing, building, and deployment processes.

---

## Diagram
The architecture and workflow diagram for this project is provided below:

![GitOps_Project](https://github.com/user-attachments/assets/41290644-269e-4e57-8bce-03630af1366a)

---

## Key Features
1. **Infrastructure as Code (IaC):**
   - Used Terraform to automate the creation and management of AWS resources.
   - Simplified configuration with reusable Terraform modules.

2. **Continuous Integration and Continuous Deployment (CI/CD):**
   - Automated testing and deployment using GitHub Actions workflows.
   - Integrated SonarQube for maintaining code quality.

3. **Containerization and Orchestration:**
   - Containerized applications using Docker.
   - Deployed to an Amazon EKS cluster with Helm charts.

4. **Version Control:**
   - All changes tracked via Git to maintain transparency and accountability.
   - Leveraged separate branches for staging and production environments.

5. **GitOps Practices:**
   - Ensured consistency and reliability by using Git as the single source of truth.
   - Eliminated configuration drift through automated workflows.

---

## Conclusion
This project demonstrated the effective use of GitOps principles to automate and manage infrastructure and application workflows. By leveraging GitHub Actions, Terraform, and Kubernetes, we ensured a scalable, secure, and maintainable solution for deploying applications on AWS Cloud. The approach reduced manual effort and increased the reliability of both infrastructure and application deployments.

