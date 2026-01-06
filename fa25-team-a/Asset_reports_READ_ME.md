## Asset Reports Overview

The **Asset Reports** consist of several data formats provided by the client, each describing different aspects of gambling-machine deployment across U.S. military installations. Because each format varies in structure, level of detail, and purpose, we treat them as separate but complementary datasets within the broader analysis pipeline.

Separating the formats allows us to clean, standardize, and interpret each dataset according to its intended use, whether that is machine-level detail, provider-level counts, or regional/field-office summaries. Together, these datasets provide a multilayered and more thorough view of machine distribution, supplier activity, and installation-level inventories allowing oppurtunity for further downstream analysis by the client or future DS701 teams.

Across all formats, the reports contain information such as:
- The number of machines installed at each base and how these counts vary by region.
- Manufacturer and provider-level totals showing supplier concentration.
- Machine-level metadata, including acquisition dates, serial numbers, and categories.

Together, these reports give us insight into the **allocation of gambling machines across bases**, the **types of machines in operation**, the **manufacturers supplying them**, and the **specific locations where each asset is deployed**.

## Key Cleaning & Processing Steps

Across all three formats, the goal of cleaning is to turn messy, inconsistent tables into clear, analyzable datasets. We begin by standardizing column names, fixing text formatting issues, converting numbers to the correct data types, and parsing all date fields into a uniform format. Each format has its own layout, so we extract the information differently. For example, Format 1 lists machine totals by field office, Format 2 lists machine totals by provider and location, and Format 4 lists individual machines.

To keep locations consistent, we unify base and field-office names using a shared reference list, ensuring that all formats refer to the same place the same way. We remove duplicate rows created by repeated tables, correct common OCR errors, and rebuild any missing totals so the data is internally consistent. After cleaning, each format is saved as a reproducible CSV file that can be used directly for trend analysis, comparisons across regions, provider summaries, and machine-level insights.

## Visualizations Supported by Formats 1, 2, and 4
Format 1 — Field Office & Regional Machine Totals
- Annual, quarterly, and monthly snapshot tables for each region
- Total machines over time (Europe, Japan, Korea)
- Indexed trends (base year = 100) for regional comparisons
- Machine-type composition (Slots / ACM / ITC / FRS) by region and year
- 2020 vs 2024 comparison charts (bars, deltas, pie charts)
- Top 10 / Bottom 10 field offices by average machine count
- Region-level dashboards combining trends, rankings, and composition
- Geographic plots (using merged coordinates) to show installations on a map

Format 2 —
??

Format 4 —
??

## Analysis Objectives

For the Asset Reports, our analysis focuses on turning raw tables in different formats into structured views of how gambling machines are deployed across bases, regions, years, and providers. 

Using **Format 1**, we aim to understand installation patterns over time:
- Summarize monthly, quarterly, and annual totals by selecting the latest report in each period.
- Track regional trends in total machines from `2020–2024`.
- Measure the machine-type composition (`Slots`, `ACM`, `ITC`, `FRS`) and how it shifts across years.
- Identify both high-capacity and low-capacity field offices using multi-year averages.
- Detect whether machine totals are expanding, contracting, or remaining stable at the regional level and base level.
- Support mapping and geospatial analytics via merged coordinate data.

Using **Format 2**, we work at the provider and location level to:
- Clean provider counts and total EGM fields for each base, year, and region.
- Summarize total machines supplied by each provider across FY20–FY24.
- Study provider mix by year and by region, and how concentrated the market is.
- Identify bases with the highest total number of machines and where each provider has its largest footprint.
- Measure how many distinct providers operate at each location and region.

Using **Format 4**, we work at the individual machine level to:
- Clean and standardize fields such as fiscal year, acquisition date, base name, and machine category (SLOT, FRS, ACM/ITC).
- Track how the number of machines in each category changes over time (`FY20–FY23`).
- Examine machine trends for key bases and regions (`Europe`, `Japan`, `Korea`).
- Measure the diversity of machine types at each base and how this evolves over time.
- Compare the distribution of machines across service branches (Army, Navy, Marine Corps).

## Key Questions We Wanted to Answer

### Regional and Base-Level Questions (Format 1)
- How many **total machines** are installed in each region (`Europe`, `Japan`, `Korea`), and how do these **totals** change from 2020 to 2024?
- Which field offices have the highest and lowest **long-term average** machine inventories?
- How does **machine composition** (`Slots` vs. `ACM`/`ITC`/`FRS`) differ across regions and over time?
- Are major installations experiencing consistent declines, growth, or stability?
- Do regional snapshots **reveal patterns** not visible in raw monthly tables?

### Provider-level questions (Format 2)

- Which **providers** (NOV, BAL, IGT, AIN, KON, WMS, ITE) supply the most machines overall from FY20–FY24?  
- How do provider totals and **market share** change by year, and does any single provider dominate the market in a given year?  
- How does the **provider mix** differ between regions (`Europe`, `Japan`, `Korea`)?  
- Which bases have the **highest total EGMs**, and where does each provider have its maximum machine count?  
- On average, how many **different providers** operate at a given location, and does provider diversity vary by region?  
- How do total EGMs and the share of the top provider change over time at a global level?

### Asset-level questions (Format 4)

- How many **SLOT**, **FRS**, and **ACM/ITC** machines are deployed in each fiscal year, and are those counts going up or down over time?  
- At major bases (e.g., `KAISERSLAUTERN`, `OKINAWA`, `PYONGTAEK`), how does the mix of machine categories change across fiscal years?  
- How many **slot machines** are installed at each base per year, and which bases have the largest slot footprints?  
- How are machines distributed across the **Army**, **Navy**, and **Marine Corps**, both overall and for slots specifically?  
- Are bases adding more **diverse machine types** over time, or relying on a smaller set of machine types?


### Note on Excluded Asset Report Formats
Some of the provided asset-report formats were not included in the final analysis. In several cases, key fields were heavily redacted by the client for confidentiality reasons, which made the tables incomplete or unusable. Other formats contained information that was either duplicated elsewhere or not relevant to our analytical objectives. For these reasons, after confirming with the MuckRock team, we focused our cleaning and visualization pipeline on the three formats—Format 1, Format 2, and Format 4 that provided complete, reliable, and analytically meaningful data.