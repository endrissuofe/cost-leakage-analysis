[![Python](https://img.shields.io/badge/Python-3.8+-blue?style=flat-square&logo=python)](https://www.python.org/)
[![SQL](https://img.shields.io/badge/SQL-SQLite-blue?style=flat-square&logo=sqlite)](https://www.sqlite.org/)
[![Excel](https://img.shields.io/badge/Excel-Advanced-green?style=flat-square&logo=microsoft-excel)](https://www.microsoft.com/en-us/microsoft-365/excel)
[![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)](LICENSE)

# Operational Duplicate Detection & Cost Leakage Analysis

## Overview

A real-world financial leakage detection system built for KYC/verification operations. Engineered end-to-end duplicate detection logic on a 35,000-record dataset — exposing a **99.75% data inflation rate** and preventing **₦2M+ in unnecessary agent payments**.

> **Note on data scale**: This repo uses a reduced simulation for demonstration. The production analysis at Nester Verify covered 35,000+ records and identified 86 unique entries across the full file.

## Key Results

| Metric | Result |
|--------|--------|
| Dataset Size | 35,000+ records (production) |
| Unique Records Found | 86 |
| Inflation Rate | 99.75% |
| Financial Leakage Prevented | ₦2,000,000+ |
| Disputed Cases Resolved | 100% |

## Business Problem

Field agents were submitting duplicate verification jobs, causing:
- **Double payments** — agents paid multiple times for the same job
- **Inflated reporting** — KPIs based on fraudulent record counts
- **Billing disputes** — clients questioning inflated invoices

## Methodology

1. **Data Generation** — Simulated realistic agent verification dataset
2. **Duplicate Detection** — SQL `GROUP BY` + `HAVING COUNT(*) > 1` logic
3. **Leakage Quantification** — Financial impact calculated per agent
4. **Root Cause Analysis** — Identified top 10 agents driving leakage (see `Top_10.png`)
5. **Recommendations** — Unique constraint on `Verification_ID`, automated validation pipeline

## Project Structure
```
cost-leakage-analysis/
├── Duplicate_Detection_Project.ipynb  # Full analysis notebook
├── raw_agent_verifications.csv        # Source data with duplicates
├── agent_leakage_summary.csv          # Output: leakage by agent
├── Top_10.png                         # Chart: top 10 agents by leakage
└── README.md
```

## How to Run
```bash
git clone https://github.com/endrissuofe/cost-leakage-analysis.git
cd cost-leakage-analysis
pip install pandas numpy matplotlib seaborn jupyter
jupyter notebook
```

Open `Duplicate_Detection_Project.ipynb` and run all cells.

## Tools Used

- **Python (Pandas, NumPy)** — Data generation and transformation
- **SQL (SQLite)** — Duplicate detection via CTEs and aggregation
- **Excel** — Executive summary and visualization
- **Matplotlib/Seaborn** — Charts and reporting

## Author

**Endris Suofe** — Data & Operations Analyst | KYC Compliance Specialist
[LinkedIn](https://www.linkedin.com/in/endrissuofe/) · [GitHub](https://github.com/endrissuofe)
