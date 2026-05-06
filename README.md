Project Overview
NutriPro is an end-to-end Business Intelligence project for a health-tech nutrition platform. I designed the full data pipeline — from schema design and synthetic data generation to RFM segmentation, churn scoring, and a 3-page Power BI dashboard.
What makes this different: My background as a Biotech Engineer (MSc, Jeonbuk National University) allows me to explain the why behind user behavior patterns — not just the what. For example, Keto users churn at higher rates in weeks 2–3 due to keto flu (metabolic adaptation), which I translated into a specific CRM intervention triggered on Day 14.

Dashboard Pages
PageStoryRole TargetSales Overview"Platform health and revenue composition at a glance"Data AnalystCRM Retention"Who is about to churn, and what should we do about it?"CRM AnalystNutritionist Performance"Which nutritionists drive retention, and why?"DA + CRM

Tech Stack
Data Generation : Python (Faker, NumPy, Pandas)
Analytics       : Python (RFM scoring, Churn risk model)
Visualization   : Power BI Desktop (DAX, custom theme)
Data Model      : Star schema (2 fact tables, 3 dimension tables)

Key Insights

Keto Churn Premium: Keto users have 15–20% higher churn score vs Balanced users — driven by keto flu metabolic adaptation (weeks 2–3). CRM trigger: push notification on Day 14.
Habit Formation Threshold: Retention drops sharply at Week 3, consistent with habit formation research (Lally et al., 21-day threshold). Annotated directly on Revenue Trend chart.
Meal Log → Purchase Conversion: Users with ≥10 meal logs convert to paid products at 3× the rate of non-logging users — justifying UX investment in the meal logging feature.
Smart Matching ROI: Correct nutritionist–diet pairing estimated to reduce churn by 15–20%.


Repository Structure
nutripro-crm-analytics/
├── data/
│   ├── dim_users.csv               # 1,000 users
│   ├── fact_sales.csv              # 2,500 transactions
│   └── fact_engagement_scored.csv  # RFM + churn scores
├── notebook/
│   └── nutriPro_rfm_churn.ipynb   # Python: data gen + RFM + churn
├── dax/
│   └── NutriPro_DAX_Measures_v2.txt # 14 measures, 3 folders
├── powerbi/
│   └── NutriPro_Theme.json         # Custom Power BI theme
└── assets/
    ├── page1_sales_overview.png
    ├── page2_crm_retention.png
    └── page3_nutritionist.png

How to Run

Clone this repository
Open notebook/nutriPro_rfm_churn.ipynb in Jupyter
Run all cells → generates 3 CSV files
Open Power BI Desktop → Get Data → Excel/CSV → load 3 files
Apply powerbi/NutriPro_Theme.json (View → Themes)
Paste DAX measures from dax/NutriPro_DAX_Measures_v2.txt


Data Note

All data is synthetic, generated with Python (Faker, NumPy) to simulate realistic user behavior distributions. Generated to demonstrate analytical methodology, not reflect real business data.


About
Anh Tran · MSc Biotechnology, Jeonbuk National University
Specialization: Plant disease gene research → Data Analytics
Currently: Ho Chi Minh City, Vietnam · Open to remote roles
