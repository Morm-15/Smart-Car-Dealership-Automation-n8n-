# 🚗 Smart Car Dealership Automation (n8n)

This project is an automated workflow built with **n8n** designed to streamline the sales reporting process for a car dealership. It acts as a bridge between the local Point of Sale (POS) system and the management's cloud tools.

## ⚡️ Workflow Overview

Whenever a car is sold, the sales agent inputs the data into the local system. This workflow automatically triggers to perform the following actions simultaneously:
1.  **Receive Data:** Captures sales details via a `POST` Webhook.
2.  **Database Entry:** Appends a new row to **Google Sheets** for historical record-keeping.
3.  **Notification:** Sends an immediate email notification to the dealership owner via **Gmail** containing the sale details.

## 🛠 Tech Stack

* **n8n** (Workflow Automation)
* **Webhooks** (HTTP POST Request)
* **Google Sheets API** (Data Storage)
* **Gmail API** (Notifications)
* **JSON** (Data Formatting)

## 🚀 How to Run

### 1. Prerequisites
* An active instance of n8n (Cloud or Self-hosted).
* Google Cloud Platform credentials enabled for **Gmail** and **Google Sheets**.
* A tool to test API requests (e.g., **Postman** or **Insomnia**).

### 2. Setup
1.  Import the `workflow.json` file into your n8n editor.
2.  Set up your Google Credentials in n8n.
3.  Create a Google Sheet with the following columns: `Name`, `Price`, `Type`.
4.  Update the **Google Sheets Node** with your specific Sheet ID.
5.  Update the **Gmail Node** with the recipient email address.
6.  **Activate** the workflow.

## 🔌 API Documentation (Webhook)

To trigger this workflow, send a `POST` request to the Production URL provided by the Webhook node.

**Headers:**
`Content-Type: application/json`

**Body Payload (JSON Example):**
```json
{
  "car_type": "Toyota Camry",
  "price": 24000,
  "buyer_name": "Sarah Johnson"
}



