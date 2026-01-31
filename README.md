# AI-Powered Invoice Processing Automation

## 🚀 Executive Summary
Manual data entry for financial documents is a major operational bottleneck. I developed an automated pipeline that leverages **Generative AI (Gemini 1.5 Flash)** to monitor incoming emails, parse unstructured PDF invoices, and log key financial metadata into a structured database (Google Sheets) in real-time.

## 🛠️ Technical Stack
* **Orchestrator:** Make.com (formerly Integromat).
* **AI Engine:** Google Gemini AI (LLM) for OCR and structured data extraction.
* **Cloud Integrations:** Google Workspace (Gmail & Sheets).

## 🔄 The Logical Workflow
1.  **Trigger:** Watches for new emails in Gmail with the subject "factura" and PDF attachments.
2.  **File Processing:** Extracts the PDF binary data and uploads it to the Gemini AI environment.
3.  **Entity Extraction (The AI Layer):** A specific prompt instructs Gemini to analyze the document and return a valid JSON object with the following fields: `cliente`, `rut`, `fecha`, `folio`, `monto_total`, and `forma_pago`.
4.  **Data Persistence:** Appends the structured output into a master Google Sheet, creating a Single Source of Truth (SSOT) for accounting.



## 🧠 Prompt Engineering Highlight
A key part of this project was designing a prompt that ensures 100% JSON reliability for the automation to work without human intervention:
> *"Analyze the following PDF file (invoice). Extract the information in JSON format... Return ONLY valid JSON, no additional text."*

---
## 📈 Business Impact
* **Zero-Touch Invoicing:** Reduces manual entry time by 100% per document.
* **Data Integrity:** Minimizes human error in RUT and total amount recording.
* **Scalability:** The architecture is model-agnostic and can be adapted to process any type of business document (contracts, receipts, IDs).
