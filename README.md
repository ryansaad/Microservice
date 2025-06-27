# E-commerce Microservices with Automated CI/CD on AWS EKS

## This project showcases an e-commerce application built with 11 independent microservices, fully automated with CI/CD pipelines using Jenkins and GitHub webhooks, deployed on an AWS EKS cluster. It demonstrates independent service deployment and a robust, real-time automation workflow.

---

## Key Features

* **Microservices Architecture:** Built with 11 distinct microservice components for an e-commerce application (e.g., Email, Cart, Shipping, Payment, Frontend UI).
* **Independent Deployment:** Each microservice can be built and deployed independently without affecting other services.
* **Automated CI/CD:**
    * **Continuous Integration (CI):** GitHub pushes automatically trigger Jenkins pipelines to build and push Docker images.
    * **Continuous Delivery (CD):** A dedicated Jenkins pipeline automates the deployment of the entire application to EKS.
    * **GitHub Webhooks:** Configured for automatic pipeline triggering upon code pushes.
    * **Jenkins Multibranch Pipelines:** Dynamically creates pipelines for each microservice branch, streamlining CI.
* **Kubernetes Orchestration on AWS EKS:** Leverages AWS Elastic Kubernetes Service for robust container orchestration, including:
    * **EKS Cluster:** Managed Kubernetes service.
    * **Node Group Autoscaling:** Automatically scales worker nodes (min 2, max 4) based on demand.
    * **Service Accounts & RBAC:** Implements secure, role-based access control for deployments within Kubernetes.
* **Dockerization:** All microservices are containerized using Docker, with images pushed to Docker Hub.
* **Infrastructure as Code (IaC) Principles:** AWS EKS cluster setup is managed through commands and documented in a dedicated GitHub branch.

---

## Technologies Used

* **Cloud Platform:** AWS (Amazon Web Services)
* **Container Orchestration:** AWS EKS (Elastic Kubernetes Service), Kubernetes
* **CI/CD Tool:** Jenkins
* **Version Control:** GitHub
* **Containerization:** Docker
* **Operating System:** Ubuntu (for Jenkins server and EKS worker nodes)
* **Command Line Tools:** AWS CLI, `kubectl`, `eksctl`
* **Core Languages/Frameworks :** Java (for Jenkins prerequisites), YAML (for Kubernetes configurations)

---

---

## Project Structure

This repository is organized to facilitate the modular development and automated deployment of the microservices. Here's an overview of the key branches:

* **`main` Branch:**
    * Contains the core Kubernetes YAML manifests (e.g., `app.yaml`) responsible for deploying all 11 microservice components to the EKS cluster.
    * Includes the Jenkinsfile for the Continuous Delivery (CD) pipeline, which orchestrates the deployment of the entire application.
* **Microservice Branches (e.g., `email-service`, `front-end-service`, `payment-service`, `shipping-service`, `cart-service`, etc.):**
    * Each of the 11 independent microservice components resides in its own dedicated branch.
    * Every microservice branch includes a `Jenkinsfile` that defines its specific Continuous Integration (CI) pipeline, responsible for building and pushing its Docker image to Docker Hub.
* **`infra-setup` Branch:**
    * Holds comprehensive documentation and scripts (e.g., in a `README.md` or similar file) for setting up the foundational AWS infrastructure.
    * This includes steps for configuring the AWS EKS cluster, creating necessary IAM users and policies, and installing required command-line tools like AWS CLI, `kubectl`, and `eksctl`.

---
