# AI-Powered Invoice Automation Pipeline (Make + Gemini)

## 🚀 Executive Summary

Manual invoice processing is a significant operational bottleneck.  
This project delivers an end-to-end automated pipeline that detects incoming invoices in Gmail, extracts key data using Google Gemini AI, and structures it into a Google Sheets database for real-time tracking.

---

## 📈 Estimated Business Impact

**Efficiency**  
Reduced manual data entry time by **100%** for processed invoices.

**Speed**  
The entire flow from *"Email Received"* to *"Data Logged"* takes **less than 15 seconds**.

**Scalability**  
Capable of handling hundreds of invoices per month without increasing administrative headcount.

---

## 🧠 The "Intelligence" Layer: Prompt Engineering

The core of this automation is a specialized prompt designed to ensure **100% JSON validity**, which is crucial for seamless integration between the LLM and the database:

```text
Analyze the following PDF file (invoice). Extract the following information in JSON format with the keys: client, tax_id, date, invoice_number, total_amount, payment_method. Return ONLY valid JSON, no additional text.
