#  Marketing ETL Pipeline & Looker Dashboard

## Overview
This project demonstrates a lightweight end-to-end marketing analytics workflow, transforming raw campaign and lead data into actionable insights using Python, regex, and a Looker dashboard.

The goal was to simulate a real-world marketing data pipeline: ingest messy data, clean and structure it, and visualize performance across the funnel.

---

##  Tech Stack
- Python (Pandas)
- Regex (data cleaning & feature engineering)
- Jupyter Notebook
- Looker Studio (dashboard visualization)

---

##  ETL Pipeline

### Extract
- Imported raw marketing dataset (CSV) containing leads, campaigns, and customer data

### Transform
Key transformations performed in Jupyter Notebook:

- Standardized lead sources using regex  
  - Example: `fb`, `facebook` → `Facebook`

- Extracted email domains for segmentation  
  - Example: `user@gmail.com` → `gmail.com`

- Created customer segments (B2B vs B2C)  
  - Free email providers classified as B2C

- Cleaned inconsistent and missing values  
  - Normalized nulls and "(not set)" values

### Load
- Exported cleaned dataset to `clean_marketing_data.csv`
- Connected dataset to Looker Studio for dashboarding

---

##  Dashboard Highlights

- **Conversion Funnel**
  - Leads → Qualified Leads → Customers

- **Performance by Source**
  - Conversion rate by marketing channel

- **Customer Segmentation**
  - B2B vs B2C performance comparison

- **Campaign Insights**
  - Cost per lead and conversion trends

---

##  Project Structure

```
marketing-etl-dashboard/
│
├── data/
│   ├── raw_marketing_data.csv
│   └── clean_marketing_data.csv
│
├── notebook/
│   └── marketing_etl.ipynb
│
├── dashboard/
│   │   └── dashboard_screenshot.png
│
└── README.md
```

---

##  Key Takeaways

- Demonstrates how regex can be used to clean and structure marketing data at scale
- Shows a simple but effective ETL workflow using Python
- Bridges the gap between raw data and business insights through dashboarding
- Mimics real-world marketing analytics use cases (lead funnel, attribution, segmentation)

---

##  How to Run

1. Open `marketing_etl.ipynb` in Jupyter Notebook  
2. Run all cells to clean and transform the dataset  
3. Output will generate `clean_marketing_data.csv`  
4. Upload the cleaned dataset to Looker Studio to recreate the dashboard  

---

##  Future Improvements

- Automate pipeline with scheduled ETL (Airflow or cron)
- Store data in BigQuery instead of CSV
- Build LookML model in Looker (instead of Studio)
- Add real-time event tracking integration (GA4 / GTM)

---
