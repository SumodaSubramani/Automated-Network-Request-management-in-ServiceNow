
# 🌐 Automated Network Request Automation – ServiceNow

## 📝 Project Description
The **Network Request Automation** project is designed to digitize and automate the process of submitting, approving, and tracking **network service requests** in ServiceNow.  
Traditionally, these requests were handled manually (emails, spreadsheets, calls), causing **delays, inefficiencies, and lack of traceability**.  

This project introduces a **self-service catalog item** that allows employees to submit requests, which are then automatically:
- Stored in a **custom table**,
- Routed for **approvals**,
- Sent as **email notifications**,
- Updated in **real-time with final status**.  

This solution is scalable, reusable, and production-oriented – a perfect demonstration of **ServiceNow Flow Designer, Catalog Items, Notifications, and Approvals**.
=======
# Automated Network Request Management in ServiceNow

This project automates the end-to-end management of network-related service requests within ServiceNow. By replacing traditional manual methods (like emails and spreadsheets) with an automated workflow, this solution significantly reduces delays, improves efficiency, and enhances traceability.

The system uses a self-service catalog item where employees can submit requests, which are then automatically processed, routed for approval, and tracked in real time. This project is a practical demonstration of core ServiceNow capabilities, including Flow Designer, Service Catalog, custom tables, and notifications.
>>>>>>> 8b25052cfdd0d2d08df73d89c323534b9d6b7e67

---

## 🎯 Objectives
<<<<<<< HEAD
- Provide a **centralized catalog item** for all network-related requests.  
- Reduce manual interventions by automating **approvals, record creation, and notifications**.  
- Ensure **data consistency** via a custom database table.  
- Deliver **real-time communication** using automated emails.  
- Design with **scalability and reusability** in mind.  
=======
- Provide a centralized catalog item for all network-related requests.  
- Reduce manual intervention by automating approvals, record creation, and notifications.  
- Ensure data consistency using a dedicated custom database table.  
- Deliver real-time communication to users and technicians with automated email notifications.  
- Design a scalable and reusable solution using best practices.  
>>>>>>> 8b25052cfdd0d2d08df73d89c323534b9d6b7e67

---

## 🏗️ Architecture & Workflow
<<<<<<< HEAD


Employee Submits Request (Service Catalog)
│
▼
Variable Set (Requestor Information + Network Details)
│
▼
Flow Designer
├── Get Catalog Variables
├── Create Record (u_network_database_table)
├── Send Email Notification
├── Ask for Approval (Manager/Approver)
├── Evaluate Approval Result
└── Update Record (Status: Approved/Rejected)


---

## 📂 Project Structure


📁 Network Request Automation
│
├── 📄 README.md # Project Documentation (this file)
├── 📄 Flow_Chart.png # Flow design (workflow diagram)
├── 📄 Network_Database_Table.png # Custom table design
├── 📄 Variable_Set_Config.png # Variable set configuration
├── 📄 Relationships.png # Relationship mapping
└── 📄 Update_Set_Export.xml # Update set for import into ServiceNow

=======
The automated workflow follows a clear, logical path:

1. **Employee Submits Request**: Users access a custom catalog item from the ServiceNow Service Portal.  
2. **Flow Designer Trigger**: The submission triggers an automated workflow in Flow Designer.  
3. **Create Record**: The flow creates a new record in a custom table (`u_network_database_table`) to store all request details.  
4. **Send Notifications**: Automated email notifications are sent to both the requester and the designated approver.  
5. **Seek Approval**: The flow routes the request for approval to the appropriate manager or team.  
6. **Update Status**: Based on the approval decision, the flow automatically updates the request's status (Approved/Rejected) in the custom table.  
>>>>>>> 8b25052cfdd0d2d08df73d89c323534b9d6b7e67

---

## ⚙️ Key Components


### 1️⃣ Service Catalog Item – *Network Request*
- Entry point for end users.  
- Linked with **Requestor Information variable set**.  
- Captures:
  - Requestor Name  
  - Email Address  
  - Department  
  - Device Type  
  - Location  
  - Justification  

---

### 2️⃣ Variable Set – *Requestor Information*
- Reusable variable set across catalog items.  
- Ensures consistency & avoids duplication.  
- Designed with **unique internal variable names** to prevent conflicts.  

---

### 3️⃣ Custom Table – *u_network_database_table*
- Dedicated table to store all requests.  
- Fields:
  - Requestor Name  
  - Email ID  
  - Department  
  - Device Type  
  - Location  
  - Status (Pending / Approved / Rejected)  

---

### 4️⃣ Flow Designer Automation
A powerful flow was built with the following actions:
- **Get Catalog Variables** – Capture inputs from catalog form.  
- **Create Record** – Insert data into `u_network_database_table`.  
- **Send Email** – Notify requestor & approver dynamically.  
- **Ask for Approval** – Routed to manager/approver.  
- **If Condition** – Check outcome (Approved/Rejected).  
- **Update Record** – Change status accordingly.  

---

### 5️⃣ Notifications
- Configured **email templates** for requestor & approvers.  
- Emails include:
  - Requestor name  
  - Request ID  
  - Request status  
- Supports **To, CC, BCC** (both static & dynamic).  

---

### 6️⃣ Approvals
- Approval type: **Anyone Approves**.  
- Can be configured for **static approvers** or **dynamic (from requestor’s department)**.  
- Tracks decision in the request record.  

---

## 🧪 Testing Journey & Issues Faced

### ✅ Successful Validations
- Record creation mapped correctly in custom table.  
- Email notifications triggered after enabling properties.  
- Approval flow correctly updated status in table.  

### ⚠️ Issues & Fixes
1. **Duplicate variable conflict**  
   - ❌ Error: Variables with same names overwrote values.  
   - ✔️ Fix: Assigned unique internal names in variable set.  

2. **Journal field warning**  
   - ❌ Error: “Journal field ‘approval_history’ is not valid in table.”  
   - ✔️ Fix: Ignored, since table didn’t require journal fields.  

3. **Email sending disabled**  
   - ❌ Error: “Email sending property is currently disabled.”  
   - ✔️ Fix: Enabled in **System Properties > Email** (`glide.email.smtp.active`).  

4. **Flow stuck in pending**  
   - ❌ Cause: Approval action not configured with correct approver.  
   - ✔️ Fix: Assigned dynamic approver properly.  
=======
- **Service Catalog Item**: The user-facing entry point for submitting network requests.  
- **Variable Set**: A reusable component that ensures consistent data capture across multiple catalog items (e.g., Requester Name, Email, Department).  
- **Custom Table (`u_network_database_table`)**: A dedicated database table designed to store all network request records, providing a single source of truth.  
- **Flow Designer Automation**: The core engine that orchestrates the entire process, from record creation and notifications to approvals and status updates.  
- **Notifications & Approvals**: Configured email templates and approval actions to provide real-time updates and enable decision-making.  


---

## 🚀 Outcomes
<<<<<<< HEAD
- Fully automated **Network Request lifecycle**.  
- Eliminated manual tracking with **real-time updates**.  
- Boosted efficiency via **self-service catalog & automated approvals**.  
- Proved expertise in:
  - ServiceNow Catalog Development  
  - Flow Designer Automation  
  - Notifications & Approvals  
  - Custom Table Design  
=======
This project successfully delivers a fully automated network request lifecycle, showcasing a practical application of ServiceNow development skills. Key achievements include:

- Eliminated manual tracking and introduced real-time visibility.  
- Boosted efficiency by automating approvals and data entry.  
- Proved expertise in ServiceNow's core platform features, including Catalog Development, Flow Designer, and custom table design.  
>>>>>>> 8b25052cfdd0d2d08df73d89c323534b9d6b7e67

---

## 🛠️ Setup & Deployment

<<<<<<< HEAD
### 1️⃣ Import into ServiceNow
1. Navigate to **System Update Sets > Retrieved Update Sets**.  
2. Import `Update_Set_Export.xml`.  
3. Preview & Commit the update set.  

### 2️⃣ Enable Email Notifications
- Navigate to **System Properties > Email**.  
- Enable:
  - `glide.email.smtp.active` → **true**  
  - `glide.email.read.active` → **true**  

### 3️⃣ Test End-to-End Flow
1. Submit request from **Service Catalog**.  
2. Record created in `u_network_database_table`.  
3. Email notifications sent to requestor/approver.  
4. Approve/Reject → Status auto-updated.  

---

## 📚 Learnings
- Best practices for **variable set reuse**.  
- Handling **email configurations** in ServiceNow.  
- Building **robust flows** with condition-based logic.  
- Debugging common issues (naming conflicts, disabled properties).  

---

## 🌟 Why This Project is Recruiter & Mentor Ready
✔️ Covers **end-to-end automation** use case.  
✔️ Solves a **real ITSM problem**.  
✔️ Documents **design → build → test → fix → outcome** clearly.  
✔️ Demonstrates **ServiceNow development skills**.  
✔️ Professional **README + update set + screenshots** for verification.  

---

## 👨‍💻 Author
**N.SUMODA SUBRAMANI**  
* MERN Stack Developer | ServiceNow Enthusiast | Cyber security *  
🔗 [LinkedIn](www.linkedin.com/in/sumoda-subramani-narava/) | 🔗 [GitHub]([https://github.com/geethsreetham](https://github.com/SumodaSubramani))  
=======
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

