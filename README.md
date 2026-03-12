# Azure Projects

This repository contains a collection of projects related to Azure automation, infrastructure tooling, and security response workflows.

The goal of this repository is to explore practical Azure engineering problems such as Logic App automation, reusable deployment templates, and infrastructure utilities.

---

## Repository Structure

azure-projects/

- logic-app-parameteriser  
- sentinel-playbooks  
- deployment-tools  

---

## Projects

### Logic App Parameteriser
A tool designed to convert Azure Logic App workflow JSON files into reusable and deployable ARM templates.  
The tool focuses on automating parameter extraction and removing environment-specific values to enable repeatable deployments.

---

### Sentinel Playbooks
A collection of Azure Sentinel Logic App playbooks that can be deployed as templates.  
These playbooks automate common incident response tasks such as enrichment, alert processing, and response workflows.

---

### Deployment Tools
Utility scripts and small tools to assist with Azure infrastructure automation.  
These tools may include template validation, resource inspection, and automation helpers.

---

## Technologies Used

- Azure Logic Apps
- ARM Templates
- Python
- JSON
- Azure Sentinel
