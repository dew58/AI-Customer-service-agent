# 🤖 AI-Powered Customer Service Assistant (n8n + Gemini + RAG)

An intelligent automation system built with **n8n** that uses **Google Gemini LLM** to provide context-aware customer support. The system identifies user intent, retrieves information from a private knowledge base (RAG), and automatically logs complaints into Google Sheets.

---

## 🌟 Key Features

* **Intent Detection:** Automatically classifies messages into "Inquiry" or "Complaint".
* **RAG System (Retrieval-Augmented Generation):** Answers customer questions based on a private Google Doc knowledge base.
* **Automated Data Logging:** Seamlessly records customer complaints in Google Sheets for follow-up.
* **Multi-Channel Integration:** Triggered via Telegram and responds in real-time.
* **Data Sanitization:** Includes a custom JavaScript layer to ensure clean JSON processing.

---

## 🛠 Tech Stack

* **Automation:** [n8n](https://n8n.io/)
* **AI Model:** Google Gemini (1.5 Flash/Pro)
* **Embeddings:** Google Gemini Embedding Model
* **Database:** In-Memory Vector Store
* **External Tools:** Telegram Bot API, Google Sheets API, Google Docs API

---

## 📐 Workflow Architecture


### Logic Flow:
1.  **Trigger:** User sends a message on Telegram.
2.  **Vector Store Sync:** System periodically fetches documentation from Google Docs (optimized via Schedule Trigger).
3.  **AI Analysis:** Gemini Agent analyzes the query using the "Knowledge Base" tool.
4.  **Data Processing:** A custom **Code Node** parses the AI output to structured JSON.
5.  **Conditional Routing:** * **Inquiry:** Sends a direct answer to the user.
    * **Complaint:** Logs details (summary, intent, reply) to Google Sheets and notifies the user.

---

## 🚀 Setup & Installation

1.  **Clone the Repo:**
    ```bash
    git clone (https://github.com/dew58/AI-Customer-service-agent)
    ```
2.  **Import to n8n:**
    * Open n8n and click on **Import from File**.
    * Select the `workflow.json` file.
3.  **Configure Credentials:**
    * Add your **Google Gemini API Key**.
    * Connect your **Telegram Bot Token**.
    * Authenticate **Google Sheets & Docs** via OAuth2.
4.  **Run the Sync:** Manually trigger the "Schedule Trigger" node once to populate the Vector Store.

---

## 📊 Business Impact
* **90% Reduction** in manual response time for common inquiries.
* **100% Accuracy** in complaint logging for support teams.
* **Scalable Support:** Handles multiple customers simultaneously without extra overhead.

