# Azure Logic App Playbook – Deployment Guide

![Azure](https://img.shields.io/badge/Azure-Logic%20Apps-blue)
![Deployment](https://img.shields.io/badge/Deployment-ARM%20Template-green)
![Status](https://img.shields.io/badge/status-ready-success)

This package contains a **production-ready Azure Logic App (Playbook)** ARM template.

The solution is designed for **quick deployment and customization** within your Azure environment without requiring additional support.

---

# 📦 Package Contents

- `template.json` → ARM template for Logic App deployment  
- `README.md` → Deployment and configuration guide  

---

# 🚀 Deployment Steps

### Option 1: Deploy via Azure Portal

1. Go to Azure Portal  
2. Navigate to: **Deploy a custom template**
3. Select **Build your own template in the editor**
4. Upload or paste the contents of `template.json`
5. Click **Save**
6. Fill in required parameters
7. Click **Review + Create → Create**

📖 Reference:  
https://learn.microsoft.com/azure/azure-resource-manager/templates/deploy-portal

---

### Option 2: Deploy via Deploy to Azure Button

(If provided with this template)

Click the **Deploy to Azure** button and follow the on-screen instructions.

---

# ⚙️ Post-Deployment Configuration (MANDATORY)

After deployment, additional configuration is required inside the Logic App Designer.

---

## 1) Re-authenticate Connectors

Some connectors require manual authentication.

### Steps:
- Go to: **Logic App → Connections**
- Open each connection
- Click **Edit / Authorize**
- Authenticate using appropriate credentials

📖 Reference:  
https://learn.microsoft.com/azure/logic-apps/logic-apps-manage-connections

---

## 2) Update Connector Parameters (IMPORTANT)

For certain connectors (especially Log Analytics, HTTP, Custom APIs):

> ⚠️ Some parameters are NOT fully configurable via ARM template and must be manually selected.

### Steps:
- Open **Logic App → Designer**
- Navigate to affected actions (e.g., Log Analytics, HTTP)
- Re-select:
  - Subscription  
  - Resource Group  
  - Workspace Name  
  - Table Name (if applicable)

This ensures proper binding of resources post-deployment.

---

## 3) Managed Identity Configuration

If the Logic App interacts with Azure services:

### Enable Managed Identity:
- Go to: **Logic App → Identity**
- Enable **System Assigned Identity**

### Assign Required Roles:
- Navigate to target resource (e.g., Log Analytics Workspace)
- Go to **Access Control (IAM)**
- Assign:
  - `Log Analytics Contributor` *(recommended)*  
  - OR `Log Analytics Data Sender` *(minimum)*  

📖 Reference:  
https://learn.microsoft.com/azure/logic-apps/create-managed-service-identity

---

# 🔧 Common Configuration Areas

Depending on the playbook, you may need to update:

- API Keys / Tokens  
- Workspace details  
- Email recipients  
- Incident fields  
- Query parameters (KQL)

---

# 🧪 Validation Steps

After completing configuration:

1. Go to **Logic App → Run History**
2. Trigger the workflow manually or via source
3. Verify:
   - No failed actions  
   - Data is processed correctly  
   - Expected outputs are generated  

---

# ⚠️ Troubleshooting Guide

### 403 / Unauthorized Errors
- Check Managed Identity roles  
- Verify connector authentication  

---

### Connector Not Working
- Re-authenticate connection  
- Ensure correct tenant/subscription  

---

### Log Analytics Issues
- Verify workspace selection in Designer  
- Ensure table exists  
- Check KQL query validity  

📖 Log Analytics Docs:  
https://learn.microsoft.com/azure/azure-monitor/logs/log-analytics-overview  

---

### Deployment Successful but Runtime Fails
- Check API keys / secrets  
- Validate connector configuration  
- Review Run History for exact failure  

---

# 📚 Useful Documentation

- Azure Logic Apps Overview  
  https://learn.microsoft.com/azure/logic-apps/logic-apps-overview  

- Logic App Designer  
  https://learn.microsoft.com/azure/logic-apps/quickstart-create-first-logic-app-workflow  

- ARM Template Deployment  
  https://learn.microsoft.com/azure/azure-resource-manager/templates/overview  

- Managed Identity  
  https://learn.microsoft.com/azure/active-directory/managed-identities-azure-resources/overview  

- Azure Monitor Logs  
  https://learn.microsoft.com/azure/azure-monitor/logs/log-analytics-overview  

---

# ✅ Best Practices

- Use **Managed Identity** instead of secrets where possible  
- Avoid hardcoding credentials in templates  
- Follow **least privilege access control (RBAC)**  
- Test in a **non-production environment** before rollout  

---

# ⚡ Final Note

This playbook is designed to be **deployment-ready**, but requires **minimal manual configuration post-deployment** to align with your environment.

Always validate using **Run History** after setup.
