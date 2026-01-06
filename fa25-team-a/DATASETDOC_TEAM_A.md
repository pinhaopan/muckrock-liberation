# US Military Slot Machine Revenue Explorer  
**Dataset Documentation**

---

## 1. Project Information

**Project Name**  
US Military Slot Machine Revenue Explorer

**GitHub Repository**  
https://github.com/BU-Spark/ds-muckrock-liberation.git

**Spark! Google Drive Folder**  
https://drive.google.com/drive/folders/10QaHm625yED_GkwitpEqetlaiOMsvwz2?usp=drive_link

**Client Organization**  
MuckRock – a nonprofit newsroom and transparency platform that helps the public request, analyze, and share government records.

**Client Contacts**  
- Amanda Hickman – MuckRock  
- Dillon Bergin – MuckRock  

**Class**  
DS 701 – Tools for Data Science (Boston University)

**Project Summary (In Our Own Words)**  
This project focuses on converting messy, inconsistent PDF tables about slot-machine operations on U.S. military bases into a clean, well-structured, and analyzable dataset. We built a fully reproducible extraction and cleaning pipeline, documented each field, and created a data dictionary for transparency. Using the cleaned data, we generated visualizations and deployed a Datasette (SQLite) interface for interactive exploration by branch, region, and base. The goal is to provide MuckRock with reliable, accessible data that supports initial insights, answers core client questions, and raises new investigative questions about gambling-related risks on U.S. military bases.

---

## 2. Dataset Information

### 2.1 Datasets Used


**Raw PDF Reports (FY2020–FY2024)**  
https://drive.google.com/drive/folders/1_636Gffk4L2kHOYqO8FPdjLFNNJyuzBs?usp=drive_link

**Cleaned Tabular Data (CSV + SQLite / Datasette)**  
https://drive.google.com/drive/folders/1uSMtLaQQOxdr5o2JZomox1EdKCOoFFSO?usp=drive_link

**Files Used in This Project (Raw PDFs)**  
- Asset Reports FY20–FY24  
- District Revenue FY20–FY24  
- Financial Statements  
- Revenue Comparison  
- Marine Revenue FY20–FY24  
- Navy Revenue FY20–FY24  

### 2.2 Keywords / Tags

- OCR  
- PDF Table Extraction  
- Tabular Extraction  
- Data Cleaning & Standardization  
- Revenue Analysis  
- Time Series Analysis  
- Geospatial Analysis  
- Government Transparency  
- Military Recreation  
- Slot Machine Revenue  
- ARMP (Army Recreation Machine Program)  

### 2.3 Domain(s) of Application

- **OCR** – PDF table extraction and structured data creation  
- **Civic Tech / Public Interest Data** – transparency into government-operated gambling systems  
- **Geospatial Analysis** – base-level and regional analysis  
- **Time-Series Analysis** – multi-year revenue trends  
- **Anomaly / Risk Analysis (Other)** – identifying potentially high-risk bases or patterns

---

## 3. Motivation

**Q: For what purpose was the dataset created? Was there a specific task or gap?**  

The U.S. Army Recreation Machine Program (ARMP) reported operating nearly 1,889 slot machines at 79 bases worldwide, generating approximately $70.9 million in revenue in FY2024. These records were sent to MuckRock as PDF tables with inconsistent formatting, redactions, and varying structures across years and documents.

This dataset was created to address the gap between **messy PDF tables** and **usable, analyzable data**. Specifically, it enables:

- Conversion of the ARMP and related financial tables into clean, standardized tabular datasets.  
- Exploratory analysis of slot-machine revenues by base, region, and branch over time.  
- Identification of bases and regions where gambling-related risks to military personnel may be elevated.  
- Insight into why slot-machine revenues on U.S. military bases have increased steadily since 2020.

The dataset provides a foundation for investigative journalism, public-interest research, and ethical analysis of gambling in military environments.

---

## 4. Composition

### 4.1 What do the instances represent? Are there multiple types? What is the format?

**A:**  
The instances represent **tabular financial, operational, and asset-level records** related to slot machine operations on U.S. military bases worldwide. The dataset includes multiple instance types:

- **Financial Statement Tables**  
  - Monthly and year-to-date gaming revenue  
  - Cash flow summaries (assets, liabilities, equity, net income)

- **Revenue Summaries**  
  - Revenue by branch (Army, Navy, Marines, sometimes Air Force / Total)  
  - Revenue by region (Europe, Korea, Japan, Other)

- **District- and Base-Level Revenue Tables (FY20–FY24)**  
  - Revenue by district, base, and sometimes sub-location  

- **Asset Report Tables**  
  - Machine counts by base, region, and fiscal year  
  - Machine categories (e.g., SLOT, FRS, ACM/ITC)  
  - Manufacturers/providers (e.g., NOV, IGT, KON, BAL)  
  - Acquisition/installation dates and selected serial numbers  

- **Marine and Navy Revenue Tables (FY16–FY24 trends)**  
  - Summary and detailed monthly revenue by base  

- **Base Metadata**  
  - Base names, descriptions, and latitude/longitude (bases.json)

**Format:**  
All cleaned instances are stored as **CSV files** and compiled into a **SQLite database** for Datasette. Original inputs were **PDFs** converted via OCR/Excel into tabular form.

---

### 4.2 How many instances are there in total (of each type)?

**A:**  
Counts vary by format, but approximately:

- **Financial Statements:**  
  ~10 CSVs (Format 1, Format 2 by region, Format 3 by region, Format 4)

- **Asset Reports:**  
  3 cleaned formats (Format 1, 2, and 4) spanning FY20–FY24

- **District Revenue:**  
  3 formats (2 and 3 cleaned; Format 1 omitted due to heavy noise and time constraints)

- **Marine & Navy Revenue:**  
  2 formats each (Format 1 – cumulative / historical, Format 2 – detailed monthly per base)

- **Base Metadata:**  
  1 JSON file (bases.json)

In total, there are **~25 cleaned tabular datasets**, representing **hundreds of rows per fiscal year** across formats.

---

### 4.3 Does the dataset contain all possible instances or is it a sample?

**A:**  
The dataset includes **all records provided to MuckRock in response to their requests**, including:

- Asset reports FY20–FY24  
- District revenue FY20–FY24  
- Financial statements  
- Marine and Navy revenue reports  
- Revenue comparison tables  

Within the scope of the provided PDFs, this is a **census of all available documents**. However, it may **not** represent the entire ARMP universe if additional internal DoD records exist but were not released. The sample is thus complete *for the provided corpus*, but not necessarily for all U.S. military slot-machine operations.

---

### 4.4 What does each instance consist of—raw data or features?

**A:**  
Each instance consists of **cleaned and standardized tabular fields** derived from raw OCR/PDF tables. Examples include:

- Revenue values (monthly, quarterly, yearly, and sometimes YTD)  
- Base name, district, region, branch  
- Machine counts (total machines, slots vs other categories)  
- Provider counts per base (e.g., NOV, BAL, IGT, KON, WMS, etc.)  
- Acquisition and installation dates (where available)  
- Machine categories (SLOT, FRS, ACM/ITC)

No artificial ML-specific features were engineered; all columns correspond to fields present in or directly implied by the original reports.

---

### 4.5 Is any information missing from individual instances? Why?

**A:**  
Yes, missing information appears due to:

- **OCR and Formatting Issues**  
  - Misaligned or broken tables  
  - Stray characters or unreadable cells  

- **Redacted Data**  
  - Redacted pages in Revenue Comparison and malfunction logs (e.g., population figures, email addresses of officials)  

- **Gaps in Source Reporting**  
  - Months where no revenue data was reported for certain bases  
  - Incomplete base or district codes in some years  

Missing values were retained as `NULL` or empty cells to preserve the structure and transparency of what is and is not available.

---

### 4.6 Are there recommended data splits?

**A:**  
No explicit ML-style splits (train/validation/test) are recommended. This dataset is primarily intended for **exploratory and descriptive analysis**.

However, practical analytical splits include:

- **Fiscal Year Splits:** FY2020–FY2024  
- **Branch Splits:** Army, Navy, Marines (and Total when available)  
- **Region Splits:** Europe, Korea, Japan, Other  
- **Base-Level Splits:** per-base longitudinal analysis

These splits are for analysis, not for supervised model training protocols.

---

### 4.7 Are there errors, sources of noise, or redundancies?

**A:**  
Yes, likely sources include:

- OCR artifacts (e.g., broken currency strings, misparsed labels)  
- Duplicate header rows and repeated segment titles after extraction  
- Inconsistent base naming conventions across files, years, and formats  
- Partially redacted pages with missing or obscured values  
- Very messy formats (e.g., parts of Revenue Comparison and some District Revenue Format 1 tables)

Major issues were mitigated through cleaning; remaining inconsistencies are documented in field-level notes and the data dictionary where possible.

---

### 4.8 Is the dataset self-contained or dependent on external resources?

**A:**  
The dataset is largely **self-contained**, relying only on:

- **bases.json** – a publicly available GitHub file with base locations and metadata.  

Once the PDFs and bases.json are in place, no external APIs or online services are required to reproduce the cleaned datasets.

- There is **no guarantee** that the original GitHub URL for bases.json will remain unchanged forever; the version used in this project should be archived with the repository.  
- No special licenses or fees were required for bases.json beyond standard open-source usage.

All other data originates from PDFs provided by the client and stored in restricted Spark! Drive.

---

### 4.9 Does the dataset include confidential information?

**A:**  
The dataset contains **internal financial reporting** related to U.S. military operations, which is sensitive from a governance and policy perspective. For this reason:

- Data access is **Internal (Restricted)** to Spark!, MuckRock, and approved collaborators.  
- No personal, patient, or attorney–client privileged information is present.  
- Some content was originally redacted (e.g., official emails, base populations) and is not included in the cleaned dataset.

---

### 4.10 Does the dataset contain offensive or anxiety-inducing content?

**A:**  
There is no explicit offensive language or imagery. The content is purely numerical and categorical. However:

- The subject matter—gambling on military bases and potential gambling harms to service members—may be sensitive or concerning from a social and ethical standpoint.

---

### 4.11 Is it possible to identify individuals?

**A:**  
No.  
The dataset only includes **aggregate base-level financial and asset data**. No names, demographic attributes, player activity, or individual-level identifiers are present.

---

## 5. Collection Process

**Q: How was the data collected, and how was the mechanism validated?**  

- The records were obtained by MuckRock via **government transparency channels** and public records/FOIA-style requests.  
- The data was provided directly from the **Army Recreation Machine Program (ARMP)** and related military reporting offices as PDF documents.  
- We validated the collection by:
  - Confirming file completeness across FY2020–FY2024  
  - Checking document metadata where available  
  - Verifying that the fiscal year coverage and table structures matched expected reporting patterns  

No scraping, APIs, or crowdsourcing mechanisms were used.

**Q: Over what timeframe was the data collected and created?**  

- **Creation timeframe (underlying data):** Fiscal Years 2020–2024, representing slot-machine operations during those years.  
- **Collection timeframe (MuckRock acquisition):** 2024–2025, when the PDFs were obtained and shared with the Spark! team.  

The dataset preserves the original reporting years of each financial and asset record.

---

## 6. Preprocessing / Cleaning / Labeling

### 6.1 Was any preprocessing/cleaning/labeling done?

**A:**  
Yes. Significant preprocessing was performed due to the messy and inconsistent structure of the PDF tables.

Key steps:

- Extracted tables from PDFs using a combination of tools (MuckRock’s tools, Adobe Express, Adobe Acrobat, OCR pipelines).  
- Split multi-table pages into separate logical tables by format and region.  
- Removed extraneous headers, footers, and repeated page titles.  
- Corrected misaligned rows and columns caused by OCR or layout issues.  
- Standardized field names and formats across fiscal years and document types.  
- Validated revenue and machine counts against the original tables to ensure consistency.

### 6.2 What transformations were applied?

**A:**  
The following transformations were applied:

- Conversion of extracted table text into **structured CSV files**  
- Cleaning mismatched values and removing obvious duplicates  
- Handling missing or partial values (imputing or marking them explicitly as missing)  
- Converting currency strings and numeric columns into numeric types  
- Aggregating data by branch, region, base, and year as needed  
- Joining tables across fiscal years and formats to build unified views  
- Creating a **standardized schema** and **field-level notes** for each major dataset  

No anonymization was required, as there is no personal or sensitive individual-level data.

### 6.3 Was raw data saved in addition to the cleaned data?

**A:**  
Yes.

- All **original raw PDFs** are preserved in the project’s Spark!-owned Google Drive folder (restricted).  
- Cleaned CSV files and the SQLite/Datasette database are stored both in:
  - The same restricted Drive folder  
  - The project’s GitHub repository (subject to confidentiality constraints)

### 6.4 Is the preprocessing/cleaning code available?

**A:**  
Yes.

- All extraction, cleaning, and transformation scripts (Python notebooks and scripts) are available in the project’s GitHub repository, including the pipeline to:
  - Convert PDFs to intermediate .xlsx/CSV  
  - Clean and standardize fields  
  - Generate final datasets and Datasette DB  

https://github.com/BU-Spark/ds-muckrock-liberation.git

---

## 7. Uses

### 7.1 Tasks the dataset has been used for so far

- Extracting and cleaning PDF-embedded tables from FY2020–FY2024 military slot-machine reports  
- Standardizing fields across years to create a unified multi-year dataset  
- Conducting exploratory data analysis (EDA) on revenue by branch, region, and base  
- Creating visualizations of trends, rankings, and geographic patterns  
- Deploying a Datasette instance to enable interactive browsing and filtering  
- Supporting a final written report and presentation with evidence-based findings

### 7.2 Potential future uses

- Long-term revenue trend forecasting and time-series modeling  
- Risk assessments related to gambling behavior and potential harm on military bases  
- Machine-type or game-type profitability comparisons across bases and branches  
- Policy analysis or investigative journalism into how slot-machine profits are generated and used  
- Integration with demographic or behavioral datasets (if safely and ethically available)  
- Geospatial mapping of high-revenue or potentially high-risk bases and regions

### 7.3 Factors that may impact future uses

- Dependence on OCR and PDF extraction may introduce subtle errors or inconsistencies.  
- Changes in reporting formats across fiscal years can complicate cross-year comparisons.  
- Lack of contextual variables (e.g., base population, on-base vs off-base gambling alternatives) limits certain types of analysis.  
- Redacted or missing data (e.g., malfunction logs, base population counts) may restrict deeper risk modeling.

### 7.4 Tasks the dataset should **not** be used for

- Any **individual-level behavioral analysis** (no player-level data exists).  
- **Causal claims** about gambling addiction, mental health, or medical outcomes.  
- **Financial auditing or compliance determinations** beyond what is explicitly shown in the PDFs.  
- Real-time or operational decision-making that requires current, verified transactional data.  
- Public release or publication without explicit client approval.

---

## 8. Distribution

**Access Type**  
Based on discussions with the client and the sensitivity of internal government financial records, this dataset should be classified as:

> **Internal (Restricted)** – Access limited to BU Spark!, MuckRock, and authorized collaborators.

Any external sharing or publication of data or derived products should follow MuckRock’s policies and approval processes.

---

## 9. Maintenance

**Q: How can others extend, augment, or contribute to the dataset?**

- **GitHub Contributions:**  
  - Fork and clone the repository  
  - Modify or extend the extraction/cleaning scripts  
  - Submit pull requests for corrections, enhanced cleaning, or new derived views  

- **New Data Ingestion:**  
  - Append new fiscal years by running the same pipeline on additional PDFs  
  - Add new formats or edge cases while documenting changes to the schema  

- **Coordination with Stakeholders:**  
  - Coordinate with MuckRock and BU Spark! for dataset versioning, validation, and access control  

All future extensions should follow the same **reproducible pipeline** to maintain consistency and transparency.

---

## 10. Dataset Snapshot & Size Summary

### 10.1 Example Snapshot (Base-Level Revenue Table)

| Fiscal Year | Branch  | Region | Base Name       | Machine Count | Total Revenue | Provider Mix     | Category (SLOT/FRS/etc.) |
|------------:|---------|--------|-----------------|--------------:|--------------:|------------------|---------------------------|
| 2021        | Army    | Korea  | Camp Humphreys  | 142           | 6,540,000     | NOV / IGT / KON  | SLOT                      |
| 2022        | Marines | Japan  | Okinawa         | 95            | 3,210,000     | BAL / IGT        | SLOT / FRS                |
| 2023        | Navy    | Europe | Sigonella       | 34            | 1,020,000     | KON / ITC        | SLOT                      |

*(Replace with actual rows from your cleaned dataset.)*

### 10.2 Dataset Size Summary

| Attribute              | Value                                                |
|------------------------|------------------------------------------------------|
| Total datasets         | ~25 cleaned CSV files                                |
| Instances (rows)       | Hundreds of rows per fiscal year (varies by format) |
| Fields per table       | ~6–20 columns depending on the specific format      |
| Labeled classes        | Machine categories (SLOT, FRS, ACM/ITC), Branches, Regions |
| Number of labels       | 3 machine categories, 4 military branches, 3 major regions |


---
