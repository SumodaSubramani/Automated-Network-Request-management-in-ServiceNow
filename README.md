# Automated Network Request Management in ServiceNow

This project automates the end-to-end management of network-related service requests within ServiceNow. By replacing traditional manual methods (like emails and spreadsheets) with an automated workflow, this solution significantly reduces delays, improves efficiency, and enhances traceability.

The system uses a self-service catalog item where employees can submit requests, which are then automatically processed, routed for approval, and tracked in real time. This project is a practical demonstration of core ServiceNow capabilities, including Flow Designer, Service Catalog, custom tables, and notifications.

---

## 🎯 Objectives
- Provide a centralized catalog item for all network-related requests.  
- Reduce manual intervention by automating approvals, record creation, and notifications.  
- Ensure data consistency using a dedicated custom database table.  
- Deliver real-time communication to users and technicians with automated email notifications.  
- Design a scalable and reusable solution using best practices.  

---

## 🏗️ Architecture & Workflow
The automated workflow follows a clear, logical path:

1. **Employee Submits Request**: Users access a custom catalog item from the ServiceNow Service Portal.  
2. **Flow Designer Trigger**: The submission triggers an automated workflow in Flow Designer.  
3. **Create Record**: The flow creates a new record in a custom table (`u_network_database_table`) to store all request details.  
4. **Send Notifications**: Automated email notifications are sent to both the requester and the designated approver.  
5. **Seek Approval**: The flow routes the request for approval to the appropriate manager or team.  
6. **Update Status**: Based on the approval decision, the flow automatically updates the request's status (Approved/Rejected) in the custom table.  

---

## ⚙️ Key Components
- **Service Catalog Item**: The user-facing entry point for submitting network requests.  
- **Variable Set**: A reusable component that ensures consistent data capture across multiple catalog items (e.g., Requester Name, Email, Department).  
- **Custom Table (`u_network_database_table`)**: A dedicated database table designed to store all network request records, providing a single source of truth.  
- **Flow Designer Automation**: The core engine that orchestrates the entire process, from record creation and notifications to approvals and status updates.  
- **Notifications & Approvals**: Configured email templates and approval actions to provide real-time updates and enable decision-making.  

---

## 🚀 Outcomes
This project successfully delivers a fully automated network request lifecycle, showcasing a practical application of ServiceNow development skills. Key achievements include:

- Eliminated manual tracking and introduced real-time visibility.  
- Boosted efficiency by automating approvals and data entry.  
- Proved expertise in ServiceNow's core platform features, including Catalog Development, Flow Designer, and custom table design.  

---

## 🛠️ Setup & Deployment

### 1. Import Update Set
- Navigate to **System Update Sets > Retrieved Update Sets**.  
- Click **"Import Update Set from XML"** and upload the `Update_Set_Export.xml` file.  
- Preview and **Commit** the update set.  

### 2. Enable Email Notifications
Go to **System Properties > Email** and ensure the following properties are set to `true`:

glide.email.smtp.active
glide.email.read.active

pgsql
Copy code

### 3. Test the End-to-End Flow
- Submit a new request from the Service Catalog.  
- Verify that a new record is created in the `u_network_database_table`.  
- Check for email notifications sent to the requester and approver.  
- Approve or reject the request and confirm that the status is automatically updated.  

---
