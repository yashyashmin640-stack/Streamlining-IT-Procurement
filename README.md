# ServiceNow Standard Laptop Task Flow Automation

**Automating the IT procurement lifecycle for standard corporate laptops using ServiceNow Flow Designer.**

## 📋 Project Overview
This project completely automates the manual, fragmented lifecycle of ordering corporate laptops. By utilizing **ServiceNow Flow Designer**, the organization transitions from spreadsheet tracking and manual email threads to a low-code, trigger-based workflow. This automation drastically shortens fulfillment cycles, eliminates manual data-entry bottlenecks, and establishes end-to-end accountability.

## 🎯 Core Objectives
* **Reduce Cycle Time:** Lower average fulfillment turnarounds from days to minutes for initial dispatch.
* **Eliminate Human Error:** Auto-populate device profiles based on user roles and Active Directory attributes.
* **Enhance Visibility:** Provide real-time status updates to the end-user and the IT Asset Management (ITAM) desk.

## ⚙️ Automated Workflow Architecture
The system is divided into four distinct phases seamlessly managed by Flow Designer:

| Stage | Trigger / Action | System Integration |
| :--- | :--- | :--- |
| **1. Request Intake** | User submits an order form via the Service Catalog. | ServiceNow Service Catalog |
| **2. Dynamic Approvals** | Flow evaluates manager hierarchy. Automatically bypasses or routes approvals based on threshold. | Active Directory / HR Profile |
| **3. Fulfillment & Inventory** | Checks stock records. Deducts an asset or triggers a procurement task if below safety limit. Routes task to **Hardware Assignment Group**. | IT Asset Management (ITAM) |
| **4. Logistics & Closure** | Generates a courier ticket, pushes shipping info to the user, and closes the request. | Shipping APIs (e.g., FedEx/UPS) |

## 🚀 Technical Implementation Details
* **Trigger:** Service Catalog request submission (`sc_req_item`).
* **Approval Condition:** Evaluates the request against pre-configured approval workflows before task creation.
* **Fulfillment Task:** Upon approval, a **Catalog Task (`sc_task`)** is auto-created under the related Requested Item and assigned to the **Hardware** assignment group for configuration.
* **Synchronous Execution:** The parent flow halts execution until the Hardware group completes the task, ensuring real-time state synchronization.

## 📈 Expected Business Outcomes
* **Operational Savings:** Saves up to 4 hours of manual processing time per laptop request.
* **Zero Touch Approvals:** Up to 60% of standard hardware swaps are auto-approved under set budget limits.
* **Perfect Inventory Sync:** Real-time updates eliminate physical stock discrepancies.

---
drive link:[https://drive.google.com/drive/folders/1pPAzZttZ_A3evOMbNr2f1VLgjCla_oxK?usp=drive_link]
