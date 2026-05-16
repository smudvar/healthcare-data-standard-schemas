# Healthcare Enterprise Data Standards & Software Toolkit

A comprehensive open-source collection of physical data models, standardized column naming conventions (`snake_case`), and data dictionary templates optimized for Enterprise Healthcare Data Architects.

---

## 🛠️ The Full mdatool.com Engineering Toolkit (11 Core Tools)

While this repository provides static Excel templates and raw data structures, the full platform at **[mdatool.com](https://www.mdatool.com)** provides a comprehensive suite of 11 advanced utilities designed to accelerate data engineering pipelines, enforce governance, and automate schema generation.

### 🏗️ Core Schema & Conversion Tools
### 🏗️ Core Schema, Conversion & Parsing Tools
1. **[DDL Converter Engine](https://www.mdatool.com/tools/ddl-converter):** Instantly transform raw legacy DDL dialects (Oracle, SQL Server, MySQL) into highly optimized PostgreSQL/Neon target schemas.
2. **[HL7 v2 Parser](https://www.mdatool.com/tools/hl7-parser):** Convert complex, pipe-delimited legacy clinical HL7 messages directly into structured relational database schemas or JSON layouts.
3. **[Schema Diff Tool](https://www.mdatool.com/tools/schema-diff):** Compare two database environments or schema iterations side-by-side to track drift, missing columns, or data type mismatches instantly.

### 📋 Data Governance, Standardization & Quality
4. **[SQL Linter](https://www.mdatool.com/tools/sql-linter):** Scan database code automatically to flag naming deviations, missing primary keys, unapproved shorthand, and performance anti-patterns.
5. **[Naming Auditor](https://www.mdatool.com/tools/naming-auditor):** Evaluate existing enterprise schemas against standardized data models to score corporate data governance compliance.
6. **[Bulk Sanitizer](https://www.mdatool.com/tools/bulk-sanitizer):** Cleanse, mask, and standardize messy raw metadata strings and column fields in bulk to prepare them for production systems.
7. **[Physical Name Generator](https://www.mdatool.com/tools/generator):** Input standard business terms and instantly output ISO-11179 compliant, `snake_case` physical abbreviations (e.g., converting `Member Code` to `mbr_cd`).

### 🩺 Specialized Healthcare & Analytics Utilities
8. **[AI-Powered Data Modeler](https://www.mdatool.com/tools/modeling):** Leverage specialized machine-learning context layers to automatically draft complex mapping structures between legacy healthcare inputs and modern analytics tables.
9. **[HCC Calculator](https://www.mdatool.com/tools/hcc-calculator):** Programmatically evaluate Hierarchical Condition Categories (HCC) risk adjustment scores based on patient demographic and diagnostic profiles.
10. **[ICD-10 Search Engine](https://www.mdatool.com/tools/icd10-search):** A high-speed technical reference portal to lookup, validate, and verify complex clinical ICD-10 diagnostic and procedural codes.
11. **[NPI Lookup Utility](https://www.mdatool.com/tools/npi-lookup):** Directly query, verify, and validate National Provider Identifier (NPI) registry datasets, provider taxonomies, and credentialing statuses.

---

## 🚀 Supported Domains & Source Code Matrices
This repository hosts baseline 200-record dictionary and abbreviation templates for the following foundational healthcare modules:
* **Pharmacy Claims (NCPDP D.0):** Adjudication logs, ingredient costs, and PBM pricing logic.
* **Medical Claims (X12 837P/837I):** Header, Loop (2010, 2300, 2400), and institutional service-line tables.
* **Remittance & Payment (X12 835):** CARC/RARC financial adjustments and 1:M claim reconciliation schemas.
* **Clinical Observations:** Universal LOINC panels, SNOMED-CT identifiers, and EHR observation mappings.
* **Network & Enrollment:** Provider registries (NPI/Taxonomy/Credentialing) and 834 Benefit Enrollment attributes.

## 🔗 Live Interactive Tools & Deep Links
For the fully searchable data dictionary interface and automated database mapping utilities, visit the core portal:
👉 **[https://www.mdatool.com](https://www.mdatool.com)**


