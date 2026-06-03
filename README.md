# Advanced AI & Marketing Automation Workflows for n8n

This repository contains a collection of production-ready, advanced **n8n** workflows designed to automate lead generation, data enrichment, multi-channel AI assistants equipped with robust session memory, and AI-driven email marketing cycles.

---

## 🚀 Core Workflows

### 1. Lead Magnet & Autonomous Voice Agent Pipeline
A cutting-edge workflow that automates the entire cold-outreach and lead nurturing cycle.
* **How it works:** Validates incoming webhook data -> Scrapes the lead's business website -> Processes content and generates a custom knowledge base via OpenAI -> Dynamically provisions a tailored voice agent using Vapi API -> Triggers an automated outbound call.

### 2. Enterprise Chatbot with Distributed Memory (Redis + LangChain)
A highly scalable, context-aware conversational agent tailored for coaching and consulting businesses.
* **How it works:** Receives user messages via Webhook -> Manages chat history and session persistence using **Redis Chat Memory** -> Empowers the LangChain agent with custom tools to query internal documents and upsert lead data directly into **Airtable**.

### 3. AI-Driven Email Marketing & Nurturing Engine
An automated funnel closer designed to maintain hyper-personalized, ongoing communications with leads.
* **How it works:** Triggers based on CRM/Airtable lead updates -> Leverages OpenAI to analyze lead behavior and draft hyper-segmented email copies -> Automatically dispatches the email via marketing tools (e.g., Mailchimp, HubSpot, or SMTP/Gmail nodes) -> Updates logs and conversion metrics back in the central database.

---

## ⚠️ CRITICAL SETUP NOTE (Credentials & Configuration)

**IMPORTANT:** The JSON files provided in this repository contain only the logical structure of the workflows. They **DO NOT** include any API keys, tokens, or credentials. 

To run these workflows successfully, you **MUST manually configure the credentials for each node** after importing. n8n will not recognize or execute the nodes until your own accounts are linked.

You will need to set up credentials for the following services:
* **OpenAI API** (For `gpt-4o-mini` and LangChain models)
* **Redis Instance** (Host, port, and password for Chat Memory persistence)
* **Airtable API** (Personal Access Token, along with updating your specific Base and Table IDs)
* **Vapi API** (For outbound AI voice calls)
* **Email Marketing / CRM Credentials** (API keys for platforms like Mailchimp, HubSpot, or secure SMTP/Gmail connections utilized in the email sequence)

---

## 🛠 How to Import and Run

1. Download the desired `.json` workflow file from this repository.
2. Open your n8n instance and create a new workflow.
3. Click on the top-right menu and select **Import from File**, then choose the downloaded JSON (or simply copy the raw JSON text and paste it directly onto the n8n canvas).
4. **Crucial Step:** Open each node (OpenAI, Redis, Airtable, Webhook, Mailchimp/SMTP, etc.) and assign your own **Credentials** and environment variables.
5. Toggle the workflow status to **Active**.
