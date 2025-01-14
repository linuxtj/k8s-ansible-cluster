# Kubernetes Cluster Setup with Ansible

This repository contains an Ansible playbook for automating the setup of a production-ready Kubernetes cluster. The playbook aims to provide a robust and scalable foundation for deploying applications. It includes:

*   **High Availability (HA) Control Plane:** Ensures resilience by setting up multiple Kubernetes master nodes.
*   **Monitoring Integration:** Includes Prometheus and Grafana for monitoring cluster health and application performance.
*   **Logging Integration:** Uses Elasticsearch and Kibana for centralized log management and analysis.
*   **Automated Deployment:** Leverages Ansible for consistent and repeatable infrastructure provisioning.

## Project Goals

*   **Automation:** Automate the complete Kubernetes cluster setup process, minimizing manual intervention.
*   **High Availability:** Ensure a robust and fault-tolerant Kubernetes control plane.
*   **Observability:** Provide comprehensive monitoring and logging capabilities to gain insights into cluster and application behavior.
*   **Reproducibility:** Make it easy to recreate the infrastructure across different environments.
*   **Maintainability:** Write clean, well-documented, and modular Ansible code.

## Project infrastructure

k8s-ansible-setup/
├── ansible/
│ ├── ansible.cfg # Ansible configuration
│ ├── inventory.yml # Host inventory
│ ├── group_vars/
│ │ ├── all.yml # Variables for all hosts
│ │ └── k8s.yml # Variables specific to Kubernetes
│ ├── roles/
│ │ ├── common/ # Common tasks (e.g., package updates)
│ │ ├── kubernetes_setup/ # Core Kubernetes installation
│ │ ├── prometheus/ # Prometheus installation
│ │ ├── grafana/ # Grafana installation
│ │ ├── elk/ # Elasticsearch installation
│ │ └── kibana/ # Kibana installation
│ └── site.yml # Main playbook
├── docs/ # Documentation about the project
└── README.md # Project overview and instructions

## Prerequisites

Before running the playbook, ensure that you have the following:

*   **Ansible:** Installed on the machine you'll be running the playbook from.
*   **Target Servers:** A set of servers or virtual machines that will become part of your Kubernetes cluster.
*   **SSH Access:** SSH access to all the target servers from the machine running Ansible.
*   **Python:** Python installed on all target servers.
*   **Basic Linux knowledge**
*   **Network Connectivity:** Your machines must be able to communicate with each other

## Getting Started

1.  Clone this repository to your machine.
2.  Configure the inventory file with IP addresses for your servers.
3.  Modify variables as needed in the group\_vars directory.
4.  Run the ansible playbook

```bash
ansible-playbook -i ansible/inventory.yml ansible/site.yml
