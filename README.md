Automated Sales Reporting & Data Validation Pipeline

🚀 Executive Summary

Manual data entry in CRM systems often leads to naming inconsistencies that compromise financial reporting accuracy. I developed a Python-based pipeline that resolves these entity errors using Fuzzy String Matching and automates the generation of executive-level performance reports in PDF format.

📈 Estimated Business Impact:

Efficiency: Automated the reconciliation of transactional data, reducing manual data cleaning time by ~5-8 hours per reporting cycle.

Accuracy: Reached 100% data integrity by implementing a dual-layer validation (algorithmic matching + manual QC flagging).

🛡️ Data Quality Spotlight: Entity Resolution (Before & After)

The core value of this project is the transformation of "dirty" manual entries into standardized, joinable data. Using the Levenshtein Distance algorithm, the script reconciles high-variance strings with a master representative list:

Raw Input (Manual Entry)

Resolved Entity (Master List)

Match Confidence

"Gogle"

"Google"

80%+

"Micro-soft"

"Microsoft"

90%+

"Amzon Corp"

"Amazon"

85%+

"Unkown_Vendor"

NULL

Flagged for Review

Analyst Insight: To guarantee 100% accuracy, I implemented a 30% similarity threshold. Any record falling below this score is automatically diverted to registros_sin_cruce.csv for manual validation, preventing false positives in executive KPIs.

🛠️ Technical Implementation

Fuzzy Logic Layer: Utilized the thefuzz library to calculate similarity scores between transactional data and the representative database.

Data Aggregation: Executed complex joins and grouping logic with pandas to calculate performance metrics (Sales by Representative and Client).

Automated PDF Assembly: Developed a reporting engine using FPDF that programmatically inserts tables, timestamps, and visualizations.

📊 Key Outcomes

Data-Driven Decisions: Stakeholders receive a standardized PDF report with automated Matplotlib visualizations, eliminating the need for manual spreadsheet manipulation.

Scalability: The pipeline can handle thousands of rows of inconsistent data, maintaining performance where manual auditing would fail.
