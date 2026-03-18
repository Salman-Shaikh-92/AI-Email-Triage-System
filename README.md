# 📧 AI-Powered Email Triage & Auto-Responder System

![Make.com Workflow](./workflow-diagram.png)

## 🚀 Overview
An intelligent, automated email management system built using **Make.com**, **Google Gemini AI**, and **JSON Parsing**. This workflow monitors a Gmail inbox, uses Large Language Models (LLMs) to analyze incoming emails, and makes autonomous routing decisions to either draft a reply, send an urgent escalation alert, or ignore non-actionable emails.

This project eliminates manual inbox sorting and accelerates response times for business inquiries while ensuring angry customers are handled immediately.

## 🛠️ Tech Stack & Tools
* **Automation Engine:** Make.com (formerly Integromat)
* **AI Model:** Google Gemini (via Google AI SDK)
* **Integrations:** Gmail API
* **Data Handling:** JSON Parser & Make.com Router (Conditional Logic)

## 🧠 Core Architecture & Workflow
The automation follows a multi-branch conditional logic setup:

1. **Trigger (Gmail):** Watches for new, unread emails in the inbox.
2. **AI Analysis (Gemini):** Processes the email text using a strict prompt to output a structured JSON payload containing:
   - `category`: (Inquiry / Complaint / Other)
   - `sentiment`: (Positive / Negative / Neutral)
   - `draft_reply`: Context-aware professional response.
3. **Data Parsing:** A JSON Parser module extracts these variables for downstream routing.
4. **Conditional Routing (The Brain):**
   - 🟢 **Path A (Inquiries):** If `category == Inquiry`, it automatically generates a drafted reply in Gmail, attaching it to the original thread ("Re: Subject").
   - 🔴 **Path B (Escalations):** If `sentiment == Negative` or `category == Complaint`, it instantly sends an urgent alert email to the admin for manual intervention.
   - ⚪ **Path C (Noise Reduction):** If `category == Other` (e.g., spam, "thank you" emails), it silently marks the email as 'Read' to keep the inbox clean.

## ⚙️ How to Setup & Use This Blueprint
Want to use this automation for your own inbox? Follow these steps:

1. **Download the Blueprint:** Download the `blueprint.json` file from this repository.
2. **Import to Make.com:** - Create a free account on [Make.com](https://www.make.com/).
   - Create a new scenario, click the `...` (More) button at the bottom, and select **Import Blueprint**.
   - Upload the `blueprint.json` file.
3. **Configure Connections:**
   - Click on the **Gmail** modules and connect your Google Account.
   - Click on the **Google Gemini AI** module and enter your free API key from [Google AI Studio](https://aistudio.google.com/).
4. **Map Your Email:** Update the "To" email address in the Alert module (Path B) to your own email.
5. **Run & Schedule:** Click "Run once" to test it, then turn on the Scheduling toggle to let it run 24/7!

## 👨‍💻 Author
**Salman Shaikh**
* BCA Final Year Student | Python & AI Automation Developer
* Connect with me on [LinkedIn](https://www.linkedin.com/in/shaikh-salman-5b31182ba)
