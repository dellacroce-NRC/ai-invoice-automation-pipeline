# AI-Powered Invoice Automation Pipeline

## Overview

This project presents a small operational automation workflow built with Make, Gmail, Google Gemini and Google Sheets.

The goal is to simulate a common administrative problem: businesses often receive invoices, receipts or payment documents by email, but the relevant information remains trapped in unstructured attachments or message bodies. When this information has to be copied manually into spreadsheets, the process becomes repetitive, error-prone and difficult to audit.

This automation shows how a no-code / low-code workflow can detect incoming invoice-related emails, extract structured information with generative AI, and store the result in Google Sheets for later review or reporting.

## Business Context

Many small businesses, agencies and operational teams manage financial or administrative documents through email. Invoices and receipts may arrive in different formats, from different providers, and with inconsistent wording. Even when the volume is not extremely high, manual registration creates friction:

- repeated data entry;
- inconsistent records;
- delays between receiving a document and logging it;
- limited visibility over accumulated invoices;
- higher risk of missing or misclassifying information.

This project does not claim to be a production accounting system. It is a portfolio simulation of how AI-assisted automation can reduce manual handling and create a structured operational log from semi-structured documents.

## Workflow

```text
Incoming Gmail message
        |
        v
Filter emails related to invoices or receipts
        |
        v
Extract relevant attachment or document content
        |
        v
Use Gemini to identify key invoice fields
        |
        v
Return structured JSON output
        |
        v
Append validated fields into Google Sheets
        |
        v
Create a simple operational record for review and reporting
```

## What The Automation Extracts

The workflow is designed to extract fields such as:

- client or issuer name;
- tax ID or document identifier;
- invoice or receipt number;
- date;
- total amount;
- payment method or relevant payment information.

The extracted information is then organized into a Google Sheets table, making it easier to review, filter, validate and use for basic reporting.

## Why This Matters

The value of this project is not only the technical automation itself. The main point is the business pattern it represents:

> turning unstructured operational information into a structured dataset that can be reviewed, reported and improved over time.

This is useful for teams that receive information through email but need that information in a cleaner format for tracking, reporting or decision-making.

## Tools Used

- **Make:** automation orchestration.
- **Gmail:** email trigger and document source.
- **Google Gemini:** AI-assisted information extraction.
- **Google Sheets:** structured output table and lightweight reporting layer.
- **Prompt engineering:** instruction design to produce consistent structured fields.

## Prompting Logic

The automation uses a prompt designed to return structured information rather than free-form text. A simplified version of the extraction instruction is:

```text
Analyze the invoice or receipt document.
Extract the relevant fields in JSON format:
client, tax_id, date, invoice_number, total_amount, payment_method.
Return only valid JSON and no additional explanation.
```

This structure is important because downstream automation tools need predictable outputs. If the AI response is inconsistent, the spreadsheet logging step becomes less reliable.

## What This Project Demonstrates

- Building an end-to-end workflow with Make.
- Using Gmail as an operational trigger.
- Applying generative AI to extract structured fields from unstructured documents.
- Sending AI outputs into Google Sheets for review and reporting.
- Designing prompts for machine-readable outputs.
- Thinking about automation as a way to reduce manual administrative friction.

## Limitations

This project should be understood as a controlled automation prototype, not a production accounting solution.

Important limitations:

- extraction quality depends on the document format and the clarity of the source file;
- financial or tax-critical workflows should include human validation;
- the prompt may need adjustment for different invoice formats or languages;
- production use would require stronger error handling, logging and security controls;
- Google Sheets works well for lightweight tracking, but larger operations may require a database or accounting system integration.

## Possible Extensions

Future improvements could include:

- adding a validation status column in Google Sheets;
- flagging low-confidence or incomplete extractions;
- sending alerts when required fields are missing;
- categorizing expenses automatically;
- connecting the output to a BI dashboard;
- storing processed files in organized Drive folders.

## Key Takeaway

This project shows how AI-assisted automation can help transform scattered invoice or receipt information into a structured operational record. For small teams, this kind of workflow can reduce repetitive manual work, improve traceability and create a cleaner foundation for reporting.

The broader analytical lesson is that automation is most useful when it does not only move data from one tool to another, but also improves the structure, reliability and usability of the information a team depends on.
