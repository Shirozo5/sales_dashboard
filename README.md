# Sales Dashboard: Data Cleaning & Analysis with Python

A end-to-end data analysis project that takes a raw, messy e-commerce transactions CSV (~540K rows), cleans it with **Python and pandas**, and turns it into clear business insights and visualizations: monthly revenue trends, best-selling products, top customers, and revenue by country.

> **Built to demonstrate:** data cleaning, exploratory analysis, KPI reporting, and clean visual storytelling, the core of Python data analyst work.

---

## Project Highlights

- Cleaned **541,909 raw rows down to 392,692 analysis-ready rows**
- Handled missing values, duplicates, cancelled orders, and invalid prices/quantities
- Engineered a `Revenue` column and a monthly time dimension
- Produced **5 business views**: monthly trend, top products, top customers, country breakdown, and average order value
- Exported a clean CSV ready for Excel, Power BI, Tableau, or further analysis

---

## Tech Stack

| Tool | Purpose |
|------|---------|
| **Python 3** | Core language |
| **pandas** | Data cleaning and aggregation |
| **Matplotlib** | Charting |
| **Seaborn** | Statistical visualizations |
| **Jupyter Notebook** | Interactive workflow |

---

## Dataset

The project uses the public **Online Retail** transactions dataset (`online_retail.csv`, encoded in `ISO-8859-1`).

| Column | Description |
|--------|-------------|
| `InvoiceNo` | Invoice number (prefix `C` = cancellation) |
| `StockCode` | Product code |
| `Description` | Product name |
| `Quantity` | Units per line item |
| `InvoiceDate` | Date and time of the transaction |
| `UnitPrice` | Price per unit |
| `CustomerID` | Unique customer identifier |
| `Country` | Customer country |

---

## Data Cleaning Pipeline

Each step is logged in the notebook so the row count is traceable from start to finish.

| Step | Action | Result |
|------|--------|--------|
| 1 | Load raw CSV | 541,909 rows |
| 2 | Drop rows with missing `CustomerID` | 406,829 rows |
| 3 | Remove duplicate rows | 5,225 removed |
| 4 | Separate cancelled orders (`InvoiceNo` starting with `C`) | 8,872 rows set aside |
| 5 | Remove invalid `Quantity` / `UnitPrice` (≤ 0) | 40 removed |
| 6 | Standardize `Description` (trim whitespace, normalize case) | Consistent text |
| 7 | Convert `InvoiceDate` to datetime | Proper time-series support |
| 8 | Create `Revenue = Quantity × UnitPrice` | New calculated column |

**Final dataset: 392,692 rows × 9 columns, with zero missing values.**

---

## Key Insights

- **Total revenue:** roughly **8.89M** across the period (Dec 2010 – Dec 2011)
- **Seasonality:** revenue climbs sharply in the fall, peaking in **November 2011 (about 1.16M)**, which points to strong holiday-season demand
- **Geography:** the **United Kingdom accounts for about 7.29M (~82%)** of revenue. The next-largest markets are the Netherlands, Germany, EIRE, and France
- **Customer concentration:** a small group of high-value customers (e.g. IDs 14646 and 18102, each above 250K) drive a significant share of sales
- **Top products by revenue:** *Paper Craft, Little Birdie*, *Regency Cakestand 3 Tier*, and *White Hanging Heart T-Light Holder*
- **Average line-item value:** about 22.63

> **Notes:**
> - The `Paper Craft, Little Birdie` result comes from a single very large order (80,995 units), so it's a good candidate for outlier analysis in a future iteration.
> - December 2011 is a partial month in the source data, so its drop should not be read as a decline.
> - Items such as `POSTAGE` and `MANUAL` appear in the product ranking. They are not physical products and could be excluded for a stricter analysis.

---

## Visualizations

The notebook generates:

1. **Monthly Revenue Trend** (line chart)
2. **Top 10 Best-Selling Products** (horizontal bar chart)
3. **Top 10 Customers by Spend** (horizontal bar chart)
4. **Revenue by Country** (horizontal bar chart)

<!-- Add screenshots here after exporting your charts, e.g.:
![Monthly Revenue](images/monthly_revenue.png)
-->

---

## Getting Started

### 1. Clone the repository
```bash
git clone https://github.com/<your-username>/<your-repo-name>.git
cd <your-repo-name>
```

### 2. Install dependencies
```bash
pip install pandas matplotlib seaborn jupyter
```

### 3. Add the data
Place `online_retail.csv` in the project folder (same location as the notebook).

### 4. Run the notebook
```bash
jupyter notebook clean.ipynb
```

Run all cells top to bottom. The cleaned dataset will be saved as a new CSV in the same folder.

---

## Project Structure

```
01-sales-dashboard/
├── clean.ipynb                  # Cleaning, analysis, and charts
├── online_retail.csv            # Raw input data
├── cleaned_online_retail.csv    # Cleaned output
└── README.md
```

---

## Possible Extensions

- Build an interactive dashboard in **Power BI**, **Tableau**, or **Streamlit**
- Add **RFM customer segmentation** and cohort retention analysis
- Forecast monthly revenue with a simple time-series model
- Analyze cancelled orders separately to understand return patterns

---

## Services I Offer

I'm a freelance Python data analyst. I can help you with:

- Data cleaning and preparation (CSV / Excel)
- Exploratory analysis and KPI reporting
- Charts, reports, and dashboards
- Automating repetitive spreadsheet work with Python

**Let's work together:**
- Upwork: *[add your profile link]*
- Fiverr: *[add your gig link]*
- Email: *[add your email]*

---

## Author

**Muhammad Abdullah**
Software Engineering student and freelance Python data analyst

---

*If you found this project useful, consider giving it a star.*
