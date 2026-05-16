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

## 💻 Production Code Blueprints & DDL Examples

To demonstrate how to translate these enterprise standards into a modern relational architecture, see the implementation blueprints below optimized for **PostgreSQL (Neon)** and modern ORMs.

### 1. PostgreSQL DDL (Medical Claims Core)
This script demonstrates the physical implementation of the `837P/837I` medical claims data model using strict `snake_case` structural naming conventions and your standardized, descriptive abbreviations.

```sql
-- Core enterprise claims table structure
CREATE TABLE clm_hdr (
    clm_ctrl_num         VARCHAR(50) PRIMARY KEY, -- CLM01 Submitter Claim Control Number
    mbr_cd               VARCHAR(32) NOT NULL,    -- Standardized Member Code cross-reference
    bill_prov_npi        CHAR(10) NOT NULL,       -- 10-Digit National Provider Identifier
    pos_cd               CHAR(2) NOT NULL,        -- Place of Service (e.g., 11=Office, 21=Inpatient)
    tob_cd               CHAR(4),                 -- Type of Bill (Institutional specific placeholder)
    clm_tot_chg_amt      NUMERIC(12, 2) NOT NULL, -- Total Claimed Charges
    src_sys_id           VARCHAR(20) DEFAULT 'X12_837',
    rec_crt_ts           TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Service line detail table (1:M Relationship)
CREATE TABLE clm_svc_ln (
    clm_svc_ln_id        BIGSERIAL PRIMARY KEY,
    clm_ctrl_num         VARCHAR(50) REFERENCES clm_hdr(clm_ctrl_num) ON DELETE CASCADE,
    ln_num               INT NOT NULL,            -- Service Line Number (LX segment loop 2400)
    rev_cd               CHAR(4),                 -- Institutional Revenue Code
    proc_cd              VARCHAR(15) NOT NULL,    -- HCPCS/CPT Procedure Code
    diag_cd_ptr          VARCHAR(4) NOT NULL,     -- Pointer linking to header diagnosis fields
    line_chg_amt         NUMERIC(12, 2) NOT NULL
);

-- Highly optimized indexes for fast claim queries
CREATE INDEX idx_clm_hdr_mbr ON clm_hdr(mbr_cd);
CREATE INDEX idx_clm_hdr_npi ON clm_hdr(bill_prov_npi);


