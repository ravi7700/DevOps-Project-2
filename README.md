This project implements a complete, end-to-end CI/CD pipeline using Terraform, Jenkins, Docker, and Kubernetes (EKS).

Project Architecture:

Tools & Technologies Used:

1. Cloud Infrastructure: AWS (VPC, EKS, EC2)
2. Infrastructure as Code (IaC): Terraform
3. CI/CD Automation: Jenkins
4. Containerization: Docker & Nginx
5. Orchestration: Kubernetes (EKS)
6. Monitoring: Prometheus & Grafana

Key Objectives Accomplished:

Automated Provisioning: Used Terraform to build a secure VPC, Jenkins build server, and an EKS cluster.

CI/CD Pipeline: Configured a Jenkins declarative pipeline that triggers on GitHub pushes, builds Docker images, and deploys to Kubernetes.

Scalability: Implemented Kubernetes deployments with multiple replicas and LoadBalancer services for high availability.

Observability: Integrated Prometheus and Grafana for real-time monitoring of cluster and application performance.

Project Screenshot:

1. Terraform configuration

<img width="1918" height="1032" alt="Terraform Apply SS - Jenkins server and other resource creation " src="https://github.com/user-attachments/assets/cc690ea9-b603-421a-974f-ca0924832ddf" />
<img width="1917" height="1030" alt="Terraform apply completion" src="https://github.com/user-attachments/assets/591a24a3-a980-452e-85d3-ed331a1d2812" />

2. Webhook configuration

<img width="1916" height="1031" alt="Webhook Configuration" src="https://github.com/user-attachments/assets/15667f45-14c5-4a6c-9071-0f969dfead07" />

3. Jenkins Pipeline Success
   
<img width="1918" height="1031" alt="Jenkins Home Page" src="https://github.com/user-attachments/assets/fc25db10-7e34-4d29-92ba-706bae6007f4" />
<img width="1917" height="1033" alt="Pipeline Success" src="https://github.com/user-attachments/assets/f22e87c0-f621-4e10-b432-da53681f43aa" />
<img width="1918" height="1035" alt="image" src="https://github.com/user-attachments/assets/5902887a-4f17-48ec-9bbf-d1699787efbd" />
<img width="1918" height="1042" alt="CI-CD Pipeline Build" src="https://github.com/user-attachments/assets/b36a4093-558f-4c69-a21f-506b1e710f9b" />
<img width="1917" height="1033" alt="CI-CD Pipeline Deploy - Success" src="https://github.com/user-attachments/assets/eef87ab2-e644-47d8-946d-c8bef33d4dfa" />
<img width="1915" height="1032" alt="CI-CD Pipeline Overview" src="https://github.com/user-attachments/assets/2a168735-3be3-45a8-a853-dd256d6cdf87" />

4. Live Application Deployment

<img width="1916" height="1032" alt="Load Balancer URL " src="https://github.com/user-attachments/assets/c0273cc2-7e7b-4b92-9915-0d7cac27ec40" />
<img width="1931" height="1044" alt="webpage screenshot " src="https://github.com/user-attachments/assets/7646a954-046e-45b6-931d-ac94ee4c7427" />

5. Kubernetes Cluster Health (Grafana Dashboard)

<img width="1913" height="1035" alt="Grafana External IP" src="https://github.com/user-attachments/assets/111f62a5-6969-46c5-bc04-34af3b4c5d8a" />
<img width="1917" height="1031" alt="Grafana Dashboard - showcasing K8 cluster health " src="https://github.com/user-attachments/assets/d7cf5c9f-071a-4a20-81c9-15039e32320c" />

6. AWS Infrastructure

EC2 console:

<img width="1918" height="1033" alt="AWS console EC2" src="https://github.com/user-attachments/assets/e128215f-dd47-480f-8589-79906696d5e7" />

EKS Cluster Console

<img width="1918" height="1033" alt="AWS Console - EKS Cluster" src="https://github.com/user-attachments/assets/a3a3cd87-478f-47cd-8b55-03c2f205a5a0" />

EKS Cluster Node Group Console:

<img width="1913" height="1030" alt="EKS Cluster Node Group" src="https://github.com/user-attachments/assets/a3d10ca2-2ea2-4a72-bec4-f1cc7aea935a" />

7. Docker Repo

<img width="1918" height="1032" alt="Docker Repo" src="https://github.com/user-attachments/assets/dbcc40c5-7ebd-458e-a3f4-e3d8e6913a3c" />

Key Technical Challenges & Solutions:

EKS Authentication: Resolved "client provides credentials" errors by upgrading to AWS CLI v2 and ensuring enable_cluster_creator_admin_permissions was set to true in Terraform.

Network Connectivity: Solved "i/o timeout" issues by configuring EKS security groups to explicitly allow traffic from the VPC CIDR (10.0.0.0/16).

Pipeline Automation: Fixed "docker not found" errors by installing the Docker engine on the Jenkins EC2 instance and adding the jenkins user to the docker group.
