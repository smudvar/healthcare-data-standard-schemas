# Healthcare Enterprise Data Standards & Software Toolkit

A comprehensive open-source collection of physical data models, standardized column naming conventions (`snake_case`), and data dictionary templates optimized for Enterprise Healthcare Data Architects.

---

## 🛠️ The Full mdatool.com Engineering Toolkit (11 Core Tools)

While this repository provides static Excel templates and raw data structures, the full platform at **[mdatool.com](https://www.mdatool.com)** provides a comprehensive suite of 11 advanced utilities designed to accelerate data engineering pipelines, enforce governance, and automate schema generation.

### 🏗️ Core Schema & Conversion Tools
1. **DDL Converter Engine:** Instantly transform raw SQL DDL dialects (Oracle, SQL Server, MySQL) into highly optimized PostgreSQL/Neon target schemas without manual string manipulation.
2. **Prisma & ORM Schema Generator:** Automatically output clean, type-safe Prisma schemas and data models mapped directly to your enterprise database tables.
3. **Automated Schema GUI Loader:** Import raw layouts, CSV data matrices, or legacy flat files via an intuitive browser interface to instantly generate destination structures.

### 📋 Data Governance & Standards Tools
4. **ISO-11179 Physical Naming Engine:** Enforce strict corporate data governance by converting human-readable business terms into standardized, enterprise-approved abbreviations (e.g., automatically resolving `Member Code` to `mbr_cd` or `Billing Provider NPI` to `bill_prov_npi`).
5. **SQL Linter & Quality Checker:** Scan database code to catch unapproved shorthand, missing primary/foreign keys, and anti-patterns before they reach code review.
6. **Custom Abbreviation Dictionary Manager:** Create, update, and manage your organization's unique shorthand conventions across team boundaries to prevent column-naming divergence.
7. **Enterprise Glossary Browser:** Explore over 37,288+ pre-loaded, expert-curated healthcare, pharmacy, and corporate data definitions.

### 🚀 Advanced Integration & Export Utilities
8. **AI-Powered Data Modeler:** Leverage specialized machine-learning context layers to automatically draft complex mapping structures between legacy EHR inputs and modern analytics tables.
9. **Automated Data Pipeline Sync:** Seamlessly pull your approved schemas directly into Next.js or cloud-native environments via specialized developer pipelines.
10. **Multi-Format Matrix Exporter:** Download physical schema blueprints, metadata indexes, and validation rules instantly as production-ready CSV, Excel, or JSON structures.
11. **Team Workspace Collaboration Tool:** Manage up to 5 seats with shared glossary controls, centralized team naming governance, and detailed usage analytics.

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
