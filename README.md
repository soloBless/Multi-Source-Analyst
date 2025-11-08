# 📊 Multi-Source Analyst  
**AI-Powered Multi-Channel Data Aggregator (n8n Workflow)**  

The **Multi-Source Analyst** is an intelligent **data aggregation and reporting workflow** built with **n8n**.  
It collects, cleans, and analyzes data from multiple sources (APIs, databases, sheets, or files), applies AI-driven insights, and automatically delivers structured analytics reports to stakeholders through Slack, Gmail, or Google Drive.

---

## 🌐 Overview
This workflow automates the **entire analytics pipeline** — from collecting and consolidating datasets across multiple systems, to summarizing and interpreting key performance metrics using AI models like **Google Gemini**, **Mistral**, or **Cohere**.  

Designed for **analysts, marketing teams, and data operations**, the Multi-Source Analyst enables consistent, real-time insights without manual spreadsheet updates or repetitive reporting tasks.

![EOM Multi Source Analyst](https://github.com/user-attachments/assets/5bf42545-292e-47fd-b92b-991cea9dbc29)


---

## ✨ Key Features
- **Multi-Source Data Integration** – Pulls data from APIs, databases, or cloud files  
- **Automated Cleaning & Transformation** – Normalizes formats, deduplicates records  
- **AI-Powered Insights** – Uses LLMs (Gemini / Mistral / Cohere) for summarization and pattern detection  
- **Dynamic Report Generation** – Creates narrative summaries, charts, and key KPIs  
- **Automated Distribution** – Sends reports to Slack, email, or Drive folders  
- **Scalable Scheduling** – Runs hourly, daily, or weekly with n8n triggers  
- **No-Code Extensibility** – Easily integrate new data sources or reporting outputs  

---

## 🧱 Architecture
Data Sources (APIs, DBs, Sheets)
↓
n8n Workflow Trigger (Schedule / Webhook)
↓
Data Collection & Cleaning
↓
AI Model (Gemini / Mistral / Cohere)
↓
Insight Extraction & Report Generation
↓
Distribution (Slack / Gmail / Google Drive)


---

## 🧩 Workflow Breakdown

### **1️⃣ Data Collection**
- Triggered manually, on schedule, or via webhook.  
- Gathers input from:
  - Google Sheets or CSV files  
  - REST APIs (marketing data, CRM, finance, etc.)  
  - Databases (PostgreSQL / MySQL)  
- Data is aggregated and standardized into JSON format.

### **2️⃣ Data Processing & Validation**
- Cleans data by removing duplicates and normalizing dates.  
- Uses **Function** and **Merge** nodes to combine multiple streams.  
- Applies conditional logic for missing or inconsistent entries.

### **3️⃣ AI Analysis**
- **Gemini**, **Mistral**, or **Cohere** language models process the cleaned dataset:  
  - Extract trends, anomalies, and summaries  
  - Generate natural-language insights  
  - Compute KPI explanations (“Sales rose 12% due to increased retention”)  
- The LLM agent operates within an n8n **LangChain** environment, using memory and tool nodes.

### **4️⃣ Report Generation**
- Outputs structured summary text and optional visuals (charts/tables).  
- Stores generated insights in:
  - **Google Drive** (PDF or DOCX)
  - **Google Sheets** (raw results)
  - **Slack messages** or **Gmail summaries**

### **5️⃣ Report Distribution**
- Automatically sends formatted reports to:
  - Marketing or leadership channels in Slack  
  - Distribution lists via Gmail  
  - Shared analytics folder in Google Drive  

---

## 🧠 Technology Stack
| Component | Role |
|------------|------|
| **n8n** | Workflow orchestration |
| **LangChain (n8n nodes)** | Agent orchestration and memory |
| **Google Gemini / Mistral / Cohere** | LLMs for insight generation |
| **Google Drive** | Report storage |
| **Slack / Gmail** | Notifications and sharing |
| **Google Sheets / APIs / Databases** | Data sources |

---

## 💼 Use Cases
- 📊 Marketing performance summaries (Google Ads, Meta, SEO)  
- 💰 Sales and revenue growth trend analysis  
- 📈 Weekly business intelligence digest for leadership  
- 🧠 Centralized data aggregation from multiple platforms  
- 📧 Automated delivery of KPI updates  

---

## 🔧 Prerequisites
| Service | Requirement |
|----------|-------------|
| **n8n Instance** | Cloud or self-hosted (v1.0+) |
| **LLM API Key(s)** | Gemini, Cohere, or Mistral account |
| **Google Workspace Access** | Drive, Gmail, and Sheets enabled |
| **Slack Workspace** | For notifications (optional) |
| **Data Sources** | APIs, databases, or cloud spreadsheets |

---

## ⚙️ Quick Start (Setup Time ≈ 30–40 mins)

1. **Import the Workflow**
   - In n8n: *Import from File → `Multi-Source Analyst.json`*

2. **Configure Credentials**
   - Add API keys for your selected LLMs:
     - Gemini API (Google Cloud)
     - Cohere API
     - Mistral API
   - Connect integrations:
     - Google Drive
     - Slack
     - Gmail
     - Data source APIs or Sheets

3. **Set Workflow Variables**
   - Time intervals or triggers  
   - Target folder IDs  
   - Email or Slack recipients  

4. **Run a Test Execution**
   - Check that data is pulled, analyzed, and distributed correctly  

5. **Activate the Workflow**
   - Enable scheduling for daily or weekly runs  

---

## 🗂️ Project Structure

multi-source-analyst/
├── Multi-Source Analyst.json
├── docs/
│ ├── SETUP.md
│ └── TROUBLESHOOTING.md
├── .env.example
└── README.md

📘 Setup Guide (Summary)
Step 1: Import Workflow

- Go to n8n → Import from File
- Select Multi-Source Analyst.json

Step 2: Connect Accounts

- Use n8n’s Credential Manager to connect:
- Google Drive → for report saving
- Gmail → for email distribution
- Slack → for notifications
- Cohere / Gemini / Mistral → for AI summarization

Step 3: Define Targets

- Folder IDs for Drive storage
- Slack channels or email recipients
- Data source URLs and API keys

Step 4: Run & Verify

- Click Execute Workflow to test
-Verify outputs:

  - Reports in Drive

  - Slack or email summaries

  - Logs in n8n execution history

---
| Metric                 | Value                    |
| ---------------------- | ------------------------ |
| Average Runtime        | 6–10 seconds             |
| Supported Data Sources | 10+                      |
| AI Response Accuracy   | ~90%                     |
| Max File Size Tested   | 20MB                     |
| Average Monthly Cost   | $10–25 (API + n8n cloud) |

---
| Parameter            | Description                 | Default      |
| -------------------- | --------------------------- | ------------ |
| **Report Frequency** | Cron or scheduled trigger   | Daily        |
| **Top K Results**    | AI context window size      | 5            |
| **Output Format**    | PDF, DOCX, or Slack message | PDF          |
| **Insight Depth**    | Model response temperature  | 0.7          |
| **Recipients**       | Slack or Gmail destinations | Configurable |

---
| Issue             | Cause                         | Solution                      |
| ----------------- | ----------------------------- | ----------------------------- |
| No data pulled    | Invalid API key or source URL | Check credentials             |
| Empty report      | Missing data mapping          | Review input JSON schema      |
| AI timeout        | Large data size               | Split into smaller chunks     |
| Gmail not sending | OAuth expired                 | Reauthorize Gmail credentials |
| Slack not posting | Wrong webhook URL             | Update connection in n8n      |

---
## 🛡️ Security Notes

- Store credentials securely in n8n’s Credential Manager
- Exclude .env and sensitive files from version control
- Rotate all API keys every 90 days
- Log and monitor execution history for data audits
- Avoid uploading sensitive personal data to public models

## 🤝 Contributing

Contributions and extensions are welcome!

- 🧩 Add more data source integrations
- 🧠 Improve AI prompts or summarization logic
- 🧾 Add visualization or dashboard exports (e.g., Looker, Sheets charts)
- 🐛 Submit bug fixes or optimization pull requests

---

## 🙌 Acknowledgments

- n8n community for no-code workflow innovation
- Google Cloud AI, Cohere, and Mistral for LLM support
- Slack & Google Workspace APIs for communication and reporting tools

## 🔗 Resources

- n8n Documentation
- Google Gemini API
- Cohere API Docs
- Mistral AI API
- Slack Webhooks
- Google Drive API
