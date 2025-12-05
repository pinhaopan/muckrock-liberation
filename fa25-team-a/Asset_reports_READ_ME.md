## 📊 Asset Reports Overview

The **Asset Reports** section contains data provided by our client that describes the number and distribution of gambling machines supplied by various vendors. Each asset report includes multiple tables, and these tables differ in structure, column layout, and level of detail. Because each table format conveys different types of information about the machines, we separated the reports into distinct sections based on their formatting.

This separation allowed us to clean, standardize, and analyze each table type independently, ensuring accurate extraction of machine counts, supplier information, and additional metadata relevant to downstream analysis.


The reports include information such as:
- The number of assets installed at each military base, grouped by geographical region  
- Manufacturer-level counts showing how many machines each supplier provided  
- Acquisition details for each machine, including purchase dates and serial numbers  

Together, these reports give us insight into the **allocation of gambling machines across bases**, the **types of machines in operation**, the **manufacturers supplying them**, and the **specific locations where each asset is deployed**.

## 🎯 Analysis Objectives

For the Asset Reports, our analysis focuses on turning raw tables in different formats into structured views of how gambling machines are deployed across bases, regions, years, and providers. 

Using **Format 4**, we work at the individual machine level to:
- Clean and standardize fields such as fiscal year, acquisition date, base name, and machine category (SLOT, FRS, ACM/ITC).
- Track how the number of machines in each category changes over time (FY20–FY23).
- Examine machine trends for key bases and regions (Europe, Japan, Korea).
- Measure the diversity of machine types at each base and how this evolves over time.
- Compare the distribution of machines across service branches (Army, Navy, Marine Corps).

Using **Format 2**, we work at the provider and location level to:
- Clean provider counts and total EGM fields for each base, year, and region.
- Summarize total machines supplied by each provider across FY20–FY24.
- Study provider mix by year and by region, and how concentrated the market is.
- Identify bases with the highest total number of machines and where each provider has its largest footprint.
- Measure how many distinct providers operate at each location and region.

---

## 🔍 Key Questions We Wanted to Answer

### Asset-level questions (Format 4)

- How many **SLOT**, **FRS**, and **ACM/ITC** machines are deployed in each fiscal year, and are those counts going up or down over time?  
- At major bases (e.g., KAISERSLAUTERN, OKINAWA, PYONGTAEK), how does the mix of machine categories change across fiscal years?  
- How many **slot machines** are installed at each base per year, and which bases have the largest slot footprints?  
- How are machines distributed across the **Army**, **Navy**, and **Marine Corps**, both overall and for slots specifically?  
- Are bases adding more **diverse machine types** over time, or relying on a smaller set of machine types?

### Provider-level questions (Format 2)

- Which **providers** (NOV, BAL, IGT, AIN, KON, WMS, ITE) supply the most machines overall from FY20–FY24?  
- How do provider totals and **market share** change by year, and does any single provider dominate the market in a given year?  
- How does the **provider mix** differ between regions (Europe, Japan, Korea)?  
- Which bases have the **highest total EGMs**, and where does each provider have its maximum machine count?  
- On average, how many **different providers** operate at a given location, and does provider diversity vary by region?  
- How do total EGMs and the share of the top provider change over time at a global level?
