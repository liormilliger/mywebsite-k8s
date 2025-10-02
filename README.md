# My Personal Website Portfolio - K8s Configuration

This repository contains the Kubernetes configuration files for my personal portfolio website, managed through Helm charts and deployed via an ArgoCD app-of-apps pattern.

This repository is part of a 3-repository stack for my website application. I have "helmed" my Kubernetes files for a templated and more manageable approach. I added some instructions in the `NOTES.txt` file regarding the ArgoCD view.

## 🏛️ Project Architecture

This website is part of a larger cloud-native project, deployed on AWS EKS. The entire infrastructure and deployment pipeline are managed across three dedicated repositories:

* **🌐 [mywebsite-app](https://github.com/liormilliger/mywebsite-app.git):** Contains the Python/Flask application code, HTML/CSS for the frontend, and Docker configuration for containerization.

* **🔧 [mywebsite-k8s](https://github.com/liormilliger/mywebsite-k8s.git) (This Repo):** Holds the Kubernetes deployment files and ArgoCD App-of-Apps manifests for GitOps-based deployment.

* **🏗️ [mywebsite-iac](https://github.com/liormilliger/mywebsite-iac.git):** Includes the Terraform Infrastructure as Code (IaC) to provision the AWS VPC, EKS cluster, and deploy ArgoCD via its Helm chart.

## 🚀 ArgoCD App-of-Apps

The `argocd-apps` folder contains the application definition files for the supporting apps I am managing with ArgoCD. This includes essential cluster services such as:

* **cert-manager:** For automated management and issuance of TLS certificates.
* **nginx-ingress-controller:** To manage external access to the services in the cluster.
* **prometheus:** For monitoring and alerting.

## ⚙️ Helm Charts

The Kubernetes manifests for the main website application are packaged as a Helm chart to allow for templated, configurable, and repeatable deployments. This approach simplifies the management of different environments and configurations.