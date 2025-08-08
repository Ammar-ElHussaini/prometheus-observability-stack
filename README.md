# prometheus-observability-stack<img width="1341" height="1024" alt="284796035-6a9f9d90-e56f-4038-82c7-e8eae29d8bcf" src="https://github.com/user-attachments/assets/3d22cf85-7490-48b2-9bf9-e9946cbea988" />




📌 DevOps & Infrastructure as Code (IAC) Project
Overview
This project demonstrates a complete DevOps monitoring setup using Infrastructure as Code (Terraform) and containerized monitoring tools (Prometheus, Grafana, Node Exporter, Alertmanager) deployed on AWS EC2 instances.

Project Steps
Provision AWS EC2 Instance using Terraform

Generate an EC2 instance.

Configure Security Groups.

(Optional) Attach and configure EBS storage.

Use Terraform variables for flexibility.

Automated Environment Setup

User Data script in the Terraform configuration will:

Install and update required packages.

Install Docker and Docker Compose.

Prepare the environment for container deployment.

Prometheus Configuration

In the prometheus.yml config, set the EC2 instance IP.

Best practice: use dynamic service discovery instead of static IPs (e.g., via AWS EC2 Service Discovery).

Deploy Monitoring Stack

Bring up the containers:

Prometheus

Node Exporter (on the EC2 instance)

Grafana

Alertmanager

The system can also monitor your application containers.

Prometheus Scraping

Prometheus sends scrape requests every 15 seconds to the Node Exporter on the instance.

Grafana Integration

Connect Grafana to Prometheus as a data source.

Create dashboards to visualize system and application metrics.


Best Practices
Use Terraform variables for instance type, region, and AMI.

Use file-based or cloud API service discovery for Prometheus targets.

Secure ports using Security Group rules.

Persist Prometheus and Grafana data using Docker volumes.
