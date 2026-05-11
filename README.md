🥗 NutriPro CRM Analytics
End-to-end Business Intelligence for a Health-Tech Nutrition Platform

"My background as a Biotech Engineer lets me explain the why behind user behavior — not just the what."
<img width="949" height="439" alt="image" src="https://github.com/user-attachments/assets/378b106b-1f23-4788-9349-d63e3796c07f" />
📋 Project Overview
NutriPro is a full end-to-end BI project simulating a health-tech nutrition platform. I designed the complete data pipeline — from schema design and synthetic data generation through RFM segmentation, churn scoring, and a 3-page interactive Power BI dashboard.
What makes this different: As a Biotech Engineer (MSc, Jeonbuk National University), I bring domain knowledge that goes beyond standard analytics. For example: Keto users churn at higher rates in weeks 2–3 due to keto flu (metabolic adaptation phase) — I translated this into a specific CRM intervention triggered automatically on Day 14.
Pipeline: Schema Design → Synthetic Data Generation → RFM Scoring → Churn Prediction → Power BI Dashboard

🎯 Key Findings
InsightFindingBusiness ActionKeto Churn PremiumKeto users have 15–20% higher churn score vs BalancedPush notification trigger on Day 14 (keto flu window)Habit Formation ThresholdRetention drops sharply at Week 3Annotated on Revenue Trend — aligns with Lally et al. 21-day researchMeal Log Conversion≥10 meal logs → 3× paid conversion rateJustify UX investment in meal logging featureSmart Matching ROICorrect nutritionist–diet pairingEstimated 15–20% churn reduction
📊 Dashboard Pages
Page 1 — Sales Overview
"Platform health and revenue composition at a glance"
Role target: Data Analyst


Revenue trend with Week 3 habit-formation threshold annotated
Diet plan breakdown: Keto vs Balanced vs Mediterranean
Product category performance
MoM growth tracking


Page 2 — CRM Retention
"Who is about to churn, and what should we do about it?"
Role target: CRM Analyst


RFM segmentation: Champions, Loyal, At Risk, Lost
Churn risk scoring with intervention priority tiers
Day 14 Keto trigger: automated CRM alert
Cohort retention curve with Week 3 drop annotation
Page 3 — Nutritionist Performance
"Which nutritionists drive retention, and why?"
Role target: DA + CRM


Nutritionist–diet match quality score
Retention rate by nutritionist × diet plan pairing
Smart matching ROI estimation
Performance benchmarking across cohort


🛠 Tech Stack
LayerToolDetailData GenerationPythonFaker, NumPy, Pandas — realistic behavior distributionsAnalyticsPythonRFM scoring, Churn risk modelVisualizationPower BI DesktopDAX measures, custom theme, star schemaData ModelStar Schema2 fact tables · 3 dimension tables

📁 Repository Structure
nutripro-crm-analytics/
│
├── README.md
│
├── data/
│   ├── dim_users.csv                  # 1,000 synthetic users
│   ├── fact_sales.csv                 # 2,500 transactions
│   └── fact_engagement_scored.csv     # RFM + churn scores
│
├── notebook/
│   └── nutriPro_rfm_churn.ipynb       # Data gen + RFM + churn pipeline
│
├── dax/
│   └── NutriPro_DAX_Measures_v2.txt   # 14 measures across 3 folders
│
├── powerbi/
│   └── NutriPro_Theme.json            # Custom Power BI theme
│
└── assets/
    ├── page1_sales_overview.png
    ├── page2_crm_retention.png
    └── page3_nutritionist.png

🚀 How to Run
Step 1 — Generate Data
bash# Clone the repository
git clone https://github.com/YOUR_USERNAME/nutripro-crm-analytics.git
cd nutripro-crm-analytics

# Install dependencies
pip install faker numpy pandas scikit-learn jupyter

# Open and run the notebook
jupyter notebook notebook/nutriPro_rfm_churn.ipynb
Run all cells → generates 3 CSV files in /data/
Step 2 — Load into Power BI

Open Power BI Desktop
Get Data → Text/CSV → load 3 files from /data/
Apply theme: View → Themes → Browse → select powerbi/NutriPro_Theme.json
Paste DAX measures from dax/NutriPro_DAX_Measures_v2.txt


🧬 Domain Insight — Why Biotech Background Matters
Standard analytics would flag Keto users as "high churn" and stop there. My biotech background lets me go further:
Keto flu timeline:
  Day 1–3   → Glycogen depletion, fatigue begins
  Day 7–10  → Electrolyte imbalance, peak discomfort
  Day 14–21 → Metabolic adaptation OR dropout decision ← intervention window
  Day 21+   → Fat-adapted state, churn risk drops sharply
CRM Implementation: Automated push notification on Day 14 with messaging tailored to metabolic adaptation — "Your body is shifting fuel sources. This is normal. Here's what to expect this week."
This is a clinically-grounded intervention, not a generic re-engagement email.
📐 Data Model
┌─────────────┐
                    │  dim_users  │
                    │  (1,000)    │
                    └──────┬──────┘
                           │
           ┌───────────────┼───────────────┐
           │               │               │
    ┌──────▼──────┐  ┌─────▼──────┐  ┌────▼────────────────┐
    │ fact_sales  │  │ dim_plans  │  │ fact_engagement      │
    │ (2,500 txn) │  │ (diet types│  │ _scored              │
    └─────────────┘  │ + nutrition│  │ (RFM + churn scores) │
                     │ ists)      │  └─────────────────────┘
                     └────────────┘
Star schema: 2 fact tables · 3 dimension tables · optimized for Power BI DirectQuery

📝 Data Note
All data is 100% synthetic, generated with Python (Faker, NumPy) to simulate realistic user behavior distributions — including seasonality, diet-specific churn curves, and nutritionist performance variance.

Generated to demonstrate analytical methodology. Does not reflect real user or business data.


📈 RFM Segmentation Logic
SegmentCriteriaCountStrategyChampionsR≥4, F≥4, M≥4~18%VIP rewards, communityLoyal UsersR≥3, F≥3~25%Streak incentives, upsellAt RiskR≤2, F≥3~20%Re-engage within 48–72hKeto At RiskAt Risk + Diet=Keto~12%Day 14 trigger specificallyLostR≤2, F≤2~15%Win-back or accept churn

🔗 Related Projects

Fitbit Health Data Analysis — Real-world Fitbit dataset: EDA + RFM + Churn prediction (Random Forest AUC=0.87)
👤 About
Anh Tran
MSc Biotechnology · Jeonbuk National University, South Korea
Specialization: Plant disease gene research → Data Analytics
Currently based in Ho Chi Minh City, Vietnam · Open to remote roles
