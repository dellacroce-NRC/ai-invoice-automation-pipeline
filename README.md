
#AI-Powered Invoice Processing Automation: From Unstructured PDF to Google Sheets

🚀 Executive Summary

Manual data entry for financial documents is a high-cost operational bottleneck prone to human error. I developed an end-to-end automated pipeline that leverages Generative AI (Gemini 1.5 Flash) to monitor incoming emails, parse unstructured PDF invoices, and log key metadata directly into a structured Google Sheets database in real-time.

📈 Estimated Business Impact:

Operational Efficiency: Reduces administrative manual entry time by ~10-15 hours/month (based on a volume of 150+ monthly invoices).

Zero-Touch Invoicing: 100% automation from email reception to final spreadsheet logging.

Data Integrity: Eliminates transcription errors in RUT and total amounts by using AI-driven structured extraction.

🛠️ Technical Stack

Orchestrator: Make.com (Workflow automation).

AI Engine: Google Gemini AI (LLM) for high-accuracy OCR and entity extraction.

Cloud Integrations: Google Workspace (Gmail & Sheets API).

🔄 The Logical Workflow

Trigger: Watches Gmail for new messages with the subject "factura" and PDF attachments.

AI Processing Layer: Extracts binary data from the PDF and sends it to Gemini AI.

Intermediate Extraction: A custom prompt forces the LLM to convert the visual document into a structured JSON object.

Final Data Persistence: The automation parses the JSON and appends each field as a new row in a master Google Sheet (Single Source of Truth).

🛡️ Data Transformation Showcase

The pipeline bridges the gap between unstructured documents and clean databases:

1. Input (Unstructured PDF): A messy invoice file with varying layouts and fonts.

2. Intermediate Processing (The AI Logic):
The script extracts a reliable JSON schema:

{
  "cliente": "Nombre Empresa S.A.",
  "rut": "76.xxx.xxx-k",
  "fecha": "2024-05-20",
  "monto_total": 150500
}


3. Final Output (Google Sheets):
A clean, formatted row ready for accounting analysis, including: Client Name, Tax ID (RUT), Date, Total Amount, and Payment Method.

🧠 Prompt Engineering Highlight

The reliability of this automation rests on Precision Prompting. I designed the instructions to ensure 100% JSON validity, which is essential for the data to be successfully mapped into Google Sheets:

"Analyze the following PDF file (invoice). Extract the following information in JSON format with the keys: client, tax_id, date, invoice_number, total_amount, payment_method. Return ONLY valid JSON, no additional text."

📈 Key Outcomes

Scalability: The architecture is model-agnostic and can be adapted to process contracts, receipts, or shipping IDs.

Real-time Visibility: Stakeholders can access updated financial data the moment an email arrives.
