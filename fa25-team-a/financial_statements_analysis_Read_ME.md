## Financial Statements Analysis Read Me

This notebook cleans and analyzes financial statement and gaming revenue data for slot machine operations across Army, Navy, Marines, and Air Force locations.

### Goal

Turn OCR-exported PDFs into a consistent, analyzable view of:
- Monthly and year-to-date gaming revenue
- Top revenue-generating bases
- Branch and region performance over time

---

### Data Used

The notebook reads pre-formatted CSVs stored under `data/`:

- `data/Financial Statements/Financial Statements Format-1.csv`
- `data/Financial Statements/Financial Statements Format-4.csv`
- Additional Financial Statement formats (2 and 3) by region  
- Navy revenue files (`data/Navy Revenue/`)
- Marine revenue files (`data/Marine Revenue/`)
- Base location metadata (`bases.json`)

---

### Key Cleaning Steps

- Standardize inconsistent `Details` labels in `Format-1` caused by OCR errors.
- Convert currency fields with commas, spaces, and stray characters into numeric float values.
- Clean and normalize base names and align them with a predefined list of top 10 bases:
  - Camp Humphreys, Okinawa Marines, Yokosuka Navy, AFRC Dragon Hill Lodge, Daegu, Kaiserslautern, Wiesbaden, Casey & Hovey, Sasebo Navy, Stuttgart
- Generate new fields:
  - `Branch` (Army, Navy, Marines, Air Force, Total)
  - `Region` (Europe, Korea, Japan, Singapore, Other)
  - `Date` from parsed `Month` and `Year`
  - `Monthly_Revenue` and `YTD_Revenue` by summing regional values

---

### Main Questions

This notebook is designed to answer:

- Which bases generate the highest slot machine revenue?
- How does monthly revenue change over time for the top 10 bases?
- How is revenue distributed across branches and geographic regions?
- How does branch revenue performance evolve year over year?

---

### Outputs and Visualizations

The notebook produces:

- Summary metrics:
  - Total revenue
  - Average revenue per base
  - Top 10 bases by total revenue (from actual data)
- Analysis visuals:
  - Total and average revenue by branch
  - Total and average revenue by region
  - Revenue trends for the top 10 bases from 2020–2024
  - Annual revenue ranking charts for the top bases
  - Branch performance trends over time

---

### How to Run

1. Ensure the `data/` directory matches the structure shown above.
2. Install the necessary Python libraries:

   ```bash
   pip install pandas numpy matplotlib seaborn

3. Open the notebook in Jupyter or VS Code and run all cells.
The notebook will load, clean, summarize, and visualize financial and revenue data.
