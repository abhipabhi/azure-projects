# Azure Projects

![License](https://img.shields.io/badge/license-MIT-blue)
![Platform](https://img.shields.io/badge/platform-Azure-blue)
![Language](https://img.shields.io/badge/language-Python-yellow)

A collection of Azure automation, infrastructure, and security engineering projects.

This repository focuses on practical tooling and templates for working with Azure services such as Logic Apps, ARM templates, and security automation workflows.

---

## Repository Structure

```
azure-projects/
│
├── logic-app-parameteriser/   # Tool for converting Logic App JSON to ARM templates
├── sentinel-playbooks/        # Deployable Azure Sentinel Logic App playbooks
├── deployment-tools/          # Utility scripts for Azure infrastructure
│
└── README.md
```

---

## Projects

### Logic App Parameteriser

Tool that converts Azure Logic App workflow JSON files into reusable and deployable ARM templates.

Key goals:

- Extract environment-specific values into parameters
- Remove unnecessary metadata
- Normalize template structure
- Enable repeatable deployments across environments

---

### Sentinel Playbooks

Collection of Azure Sentinel Logic App playbooks designed for security incident automation.

Example playbooks include:

- Incident enrichment workflows
- Automated response actions
- Alert processing pipelines

Each playbook is structured as a deployable template.

---

### Deployment Tools

Utility scripts and tools for Azure infrastructure automation.

Examples include:

- ARM template validation utilities
- Azure resource inspection tools
- deployment automation helpers

---

## Technologies

- Azure Logic Apps
- Azure Sentinel
- ARM Templates
- Python
- JSON

---

## Goals of this Repository

This repository focuses on building practical tools around:

- Azure infrastructure automation
- security response workflows
- reusable deployment templates
- developer tooling for Azure environments

---

## License

This project is licensed under the MIT License.
