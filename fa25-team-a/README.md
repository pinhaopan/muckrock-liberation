
<h1 align="center">
  <br>
  <a href="https://www.bu.edu/spark/" target="_blank"><img src="https://www.bu.edu/spark/files/2023/08/logo.png" alt="BUSpark" width="200"></a>
  <br>
  Project README <change to project name>
  <br>
</h1>

## Key Features
In this section you will be including a list of key features of the project.

You should also include a short description of what each part of your code does. (Detailed description in the readme of each directory, if applicable)
In this section, you will find a list of the major components of this project and what each part of the codebase does.

 **/data_extraction/** 
- Extracts tables from PDFs
- Handles messy and inconsistent table structures
- Splits multi-table pages
- Uses Textract / Adobe OCR where needed

**/cleaning_scripts/** 
- Cleans and standardizes all datasets
- Fixes misaligned rows and merged cells
- Normalizes column names across fiscal years
- Ensures numeric formatting for revenue fields

**/datasets_clean/**
– Final cleaned datasets
- Asset Reports (Formats 1, 2, 4)
- District Revenue (Formats 2, 3)
- Marine & Navy Revenue
- Financial Statements

**/datasette/**
– SQLite database powering an interactive exploration interface
- Browse revenue by base, branch, region
- Lightweight charts and summaries

**/visualizations/**
– EDA notebooks
- Time-series revenue trends
- Geographic and branch-level analyses
 
## How To Use

To clone and run this application, you'll need <a href="https://git-scm.com" target="_blank">Git</a>
From your command line:

```bash
# Clone this repository
$ git clone [[repo link]](https://github.com/BU-Spark/ds-muckrock-liberation.git)

$ cd muckrock-slot-machine-revenue-explorer
```

Create a new branch from dev, add changes on the new branch you just created.

You will want to look into <a href="https://git-scm.com/docs/git-branch" target="_blank">git branch</a> and <a href="https://git-scm.com/docs/git-checkout" target="_blank">git checkout</a>

```bash
# Create and Checkout a new branch if it doesn't exist
$ git checkout -b your-branch main

```

Open a Pull Request to dev. Add your PM and TPM as reviewers. 

At the end of the semester during project wrap up open a final Pull Request to main from dev branch.
 
## Project Description

In this section, you should include the project description, either from the client or spark.

This project focuses on transforming a newly released cache of slot-machine records from U.S. military bases—obtained through MuckRock from the Army Recreation Machine Program (ARMP)—into a clean, analyzable dataset. ARMP currently operates 1,889 slot machines across 79 overseas locations and reported $70.9 million in revenue during fiscal year 2024. Because the raw data exists only as tables embedded in PDFs, the first objective is to extract all fields, standardize the schema, resolve inconsistencies, and prepare a reliable foundation for analysis. With a structured dataset, the project will produce an initial exploratory interface that highlights revenue patterns and other key metrics across branches, regions, and individual bases, ultimately surfacing early insights and follow-up questions worth pursuing.

Beyond simple cleaning, this analysis aims to uncover deeper patterns regarding financial concentration, machine-type performance, and potential behavioral-risk indicators for deployed service members. A reproducible extraction and cleaning pipeline—paired with documentation, a data dictionary, and transparent code—will support ongoing work and enable additional analyses as more data becomes available. Final deliverables include a fully cleaned dataset, all scripts and documentation pushed to GitHub and shared via Google Drive, visualizations and preparation code, and a deployed Datasette

## Methodology
The data we are assigned fall into 2 categories: Revenue and Asset Reports. The Revenue documents give detailed information on the earnings and cash flow of each district base. The asset report gives us a complete overview of the total slot machine inventory in each branch as well. These two reports also fall into 2 other categories for each of the service branches: Marine and Navy. The collected report ranges from the time frames of 2020 - 2024.

Extracting the information required us to implement Optical Character Recognition (OCR) methods. The largely varying format structure in each file in addition to its size created challenges for analysis. To overcome these challenges we opted to split each individual file into categories of formats that appear to repeat throughout the reports. At the individual format level, we are then able to carry out a cleaner analysis of the contents of the file. The final step in the extraction process would then be to convert these broken down files into digestible CSVs.


  ## 📂 README Directory

This section serves as a directory for more detailed, topic-specific README files within the repository.  
Use the links below to dive into specific parts of the project:

- [Asset Reports README](Asset_reports_READ_ME.md)
- [Financial Statements Analysis README](financial_statements_analysis_Read_ME.md)
- [Coordinate Mapping Utility README](update_coordinates_READ_ME.md)
- [Data Overview README](data_readme.md)
- [Financial Statements Analysis README](financial_statements_analysis_Read_ME.md)


 


