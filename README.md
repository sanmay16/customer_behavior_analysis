# Customer Behavior Analysis

> End-to-end customer behavior analytics project using Python, PostgreSQL, and Power BI to identify revenue trends, customer segments, and actionable business insights across 3,900 transactions worth $233,081.

---

## 1. Overview

This project demonstrates a complete data analytics workflow — from raw data ingestion and cleaning to SQL-based analysis, interactive dashboarding, and business reporting.

**Core objective:** Transform raw customer transaction data into clear, decision-ready business insights using Python, PostgreSQL, and Power BI.

**Dataset:** 3,900 customer records | 18 features | $233,081 total revenue

---

## 2. Dataset

| Field | Description |
|---|---|
| Customer ID, Age, Gender | Customer demographics |
| Item Purchased, Category | Product details (Clothing, Accessories, Footwear, Outerwear) |
| Purchase Amount (USD) | Transaction value ($20 – $100) |
| Season, Location | Temporal and geographic context |
| Review Rating | Customer satisfaction (2.5 – 5.0) |
| Subscription Status | Loyalty indicator (Yes/No) |
| Payment Method | PayPal, Credit Card, Cash, Debit Card, Venmo, Bank Transfer |
| Discount Applied | Promotional flag |
| Frequency of Purchases | Weekly to Annually |
| Previous Purchases | Purchase history count |

---

## 3. Tools & Technologies

| Tool | Purpose |
|---|---|
| Python (Pandas) | Data cleaning, feature engineering, EDA |
| PostgreSQL | KPI queries, aggregations, customer segmentation |
| Power BI | Interactive dashboard with slicers and KPI cards |
| Microsoft PowerPoint | Executive summary presentation |

---

## 4. Project Workflow

### Step 1 — Data Loading & Inspection
- Loaded 3,900-row CSV into Pandas
- Reviewed 18 columns, data types, null counts, and summary statistics

### Step 2 — Data Cleaning
- Identified 37 missing values in Review Rating column
- Imputed missing ratings using category-wise median via `groupby().transform()`
- Standardized all column names to lowercase with underscores
- Validated Purchase Amount range ($20 – $100) — no outliers found
- Confirmed no duplicate Customer IDs

### Step 3 — Feature Engineering
- Created `age_group` column using `pd.qcut()` — quantile-based binning into 4 segments (Young Adult: 18–31, Adult: 32–44, Middle-aged: 45–57, Senior: 58–70)
- Created `purchase_frequency_days` by mapping frequency labels to numeric day values
- Identified `promo_code_used` as 100% identical to `discount_applied` → dropped redundant column

### Step 4 — PostgreSQL Loading
- Connected Python to PostgreSQL via SQLAlchemy + psycopg2
- Loaded cleaned DataFrame into PostgreSQL using `df.to_sql()`

### Step 5 — SQL Analysis
- Wrote 10 business-focused queries covering:
  - Gender and age-based revenue segmentation
  - Discount and promo code impact analysis
  - Customer loyalty segmentation (New / Returning / Loyal)
  - Top products per category using window functions (`ROW_NUMBER OVER PARTITION BY`)
  - Subscription vs non-subscription spend comparison

### Step 6 — Dashboard Development (Power BI)
- 3 KPI cards: Total Customers, Average Review Rating, Average Purchase Amount
- Revenue and Sales breakdown by Category and Age Group
- Subscription status distribution via donut chart
- Dynamic slicers: Subscription Status, Gender, Category, Shipping Type

### Step 7 — Reporting
- Structured analytical report with findings and recommendations
- Executive PowerPoint summarizing key insights for stakeholders

---

## 5. Dashboard Preview

![Customer Behavior Dashboard](visuals/dashboard.png)

**Dashboard includes:**
- **KPI Cards** — Total Customers (3.9K) | Avg Review Rating (3.75) | Avg Purchase Amount ($59.76)
- **Donut Chart** — Subscription Status: 27% subscribed vs 73% non-subscribed
- **Bar Charts** — Revenue by Category | Sales by Category
- **Horizontal Bar Charts** — Revenue by Age Group | Sales by Age Group
- **Slicers** — Subscription Status | Gender | Category | Shipping Type

---

## 6. Key Results & Insights

### Business Overview
- Analysed **3,900 customers** generating **$233,081** in total revenue
- Average Order Value (AOV): **$59.76**
- Average customer review rating: **3.75 / 5.0**
- Average purchase history: **25 previous purchases per customer**

### Revenue by Category

| Category | Revenue | Contribution | Transactions |
|---|---|---|---|
| Clothing | $104,264 | 44.7% | 1,737 |
| Accessories | $74,200 | 31.8% | 1,240 |
| Footwear | $36,093 | 15.5% | 599 |
| Outerwear | $18,524 | 7.9% | 324 |

- **Clothing and Accessories together contribute 76.5%** of total revenue
- **Footwear has the highest AOV** at $60.26 despite lower transaction volume
- **Outerwear is significantly underperforming** — a clear opportunity for targeted promotion

### Customer Demographics

**Gender Analysis:**
- Male customers (68%) generated **$157,890** in revenue
- Female customers had a slightly higher AOV (**$60.25** vs $59.54) — stronger per-transaction value

**Age Group Analysis:**

| Age Group | Age Range | Revenue |
|---|---|---|
| Young Adult | 18–31 | $62,143 ← highest |
| Middle-aged | 45–57 | $59,197 |
| Adult | 32–44 | $55,978 |
| Senior | 58–70 | $55,763 |

- **Young Adults (18–31) are the highest revenue-generating segment** at $62,143
- Consistent with Power BI dashboard — Young Adult bar is longest in both Revenue and Sales by Age Group charts

### Discount & Promo Code Insights
- Customers **without discounts spent more** on average ($60.13 vs $59.28)
- Promo codes showed **no meaningful uplift** in AOV
- Current discount strategy is reducing margins without proportionally increasing spend

### Subscription & Loyalty Behaviour
- Only **27% of customers** hold active subscriptions — significant retention growth opportunity
- Subscriber AOV ($59.49) is almost identical to non-subscribers ($59.87)
- Subscription growth is a low-cost, high-impact lever for recurring revenue

### Business Recommendations

1. **Prioritise Clothing & Accessories** — 76.5% of revenue; highest ROI marketing target
2. **Grow subscription base from 27%** — even 10% conversion growth adds ~$6,200 in recurring revenue
3. **Re-evaluate discount strategy** — shift from blanket discounts to loyalty-based rewards
4. **Target Young Adult segment (18–31)** — highest revenue cohort; ideal for retention and upselling programmes
5. **Promote Outerwear aggressively** — lowest performing category at 7.9%; targeted campaigns could improve contribution

---

## 7. Repository Structure

```
customer_behavior_analysis/
│
├── data/                  # Raw and cleaned datasets
├── notebooks/             # Jupyter notebooks (Python cleaning + EDA)
├── sql/                   # SQL analysis queries (PostgreSQL)
├── dashboard/             # Power BI .pbix file
├── visuals/               # Dashboard screenshots
├── reports/               # Final reports and presentations
└── README.md
```

---

## 8. How to Run the Project

```bash
# 1. Clone the repository
git clone https://github.com/sanmay16/customer_behavior_analysis.git
cd customer_behavior_analysis

# 2. Install dependencies
pip install pandas psycopg2-binary sqlalchemy

# 3. Run the Jupyter notebook
jupyter notebook notebooks/customer_shopping_business_analysis.ipynb

# 4. Load cleaned data into PostgreSQL and run SQL queries
psql -U postgres -d customer_behavior -f sql/customer_behavior.sql

# 5. Open Power BI dashboard
# Open dashboard/customer_behavior_dashboard.pbix in Power BI Desktop
```

---

## 9. Business Value

This project mirrors the end-to-end workflow of a professional data analyst — from raw data to board-ready insights. It demonstrates ability to clean real-world data, write business-relevant SQL using advanced techniques (CTEs, window functions), build interactive dashboards, and communicate findings as actionable recommendations.

**Skills demonstrated:** Data Cleaning · Feature Engineering · Exploratory Data Analysis · Advanced SQL · KPI Design · Power BI Dashboard · Business Storytelling · Stakeholder Reporting
