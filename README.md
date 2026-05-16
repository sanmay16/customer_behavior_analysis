# customer_behavior_analysis

End-to-end customer behavior analytics project using Python, PostgreSQL, and Power BI to identify revenue trends, customer segments, KPIs, and actionable business insights.

---

# Customer Behavior Analysis Project

## 1. Overview

This project demonstrates a complete end-to-end data analytics workflow aligned with real-world industry practices. It covers the full analytics lifecycle — from data loading and cleaning to SQL analysis, dashboard development, and executive reporting.

The objective is to transform raw data into meaningful business insights using Python, PostgreSQL, and Power BI, and to communicate findings clearly to stakeholders.

---

## 2. Dataset

* Structured dataset in CSV format
* Contains business performance metrics (e.g., sales, customers, revenue, categories)
* Loaded and processed using Python

---

## 3. Tools & Technologies

* **Python (Pandas)** – Data loading, cleaning, and exploratory analysis
* **PostgreSQL** – SQL queries and data analysis
* **Power BI** – Interactive dashboard development
* **Microsoft PowerPoint** – Executive presentation
* **Microsoft Word / PDF** – Analytical report documentation

---

## 4. Project Steps

### Step 1: Data Loading

* Imported dataset into Python using Pandas
* Reviewed structure, column types, and summary statistics

### Step 2: Data Cleaning

* Handled missing values
* Removed duplicates
* Standardized column formats
* Corrected inconsistencies

### Step 3: Exploratory Data Analysis (EDA)

* Identified key trends and performance metrics
* Analyzed revenue distribution and category performance
* Generated insights to guide deeper SQL analysis

### Step 4: SQL Analysis (PostgreSQL)

* Loaded cleaned data into PostgreSQL
* Wrote SQL queries for aggregations, filtering, joins, and KPIs
* Extracted business-critical insights

### Step 5: Dashboard Development

* Built an interactive Power BI dashboard
* Designed KPI cards, trend visuals, and category breakdowns
* Enabled filtering for dynamic analysis

### Step 6: Reporting & Presentation

* Created a structured analytical report
* Developed a PowerPoint presentation summarizing insights and recommendations

---

## 5. Dashboard Highlights

* Revenue & Sales KPIs
* Trend analysis over time
* Top and bottom performing categories
* Interactive filtering for stakeholders

---

## 6. Key Results and Insights

## Business Overview
- Analysed **3,900 customers** generating a total revenue of **$233,081**
- Achieved an overall Average Order Value (AOV) of **$59.76**
- Average customer review rating stood at **3.75 / 5**
- Customers had an average purchase history of **25 previous purchases**

---

## Revenue Analysis by Category

| Category | Revenue | Contribution | Transactions |
|----------|----------|--------------|--------------|
| Clothing | $104,264 | 44.7% | 1,737 |
| Accessories | $74,200 | 31.8% | 1,240 |
| Footwear | $36,093 | 15.5% | - |
| Outerwear | $18,524 | 7.9% | - |

### Key Findings
- **Clothing** emerged as the highest revenue-generating category contributing nearly **45%** of total revenue
- **Accessories and Clothing together contributed 76.5%** of overall sales
- **Footwear recorded the highest Average Order Value** at **$60.26**
- **Outerwear underperformed significantly**, indicating potential for promotional optimization

---

## Customer Demographic Insights

### Gender-Based Analysis
- Male customers contributed **$157,890** in revenue (**68% of total sales**)
- Female customers generated **$75,191**
- However, female customers showed a slightly higher AOV (**$60.25**) compared to males (**$59.54**)

### Age Group Analysis
- Customers aged **56–70 years** contributed the highest revenue at **$65,256 (28%)**
- The **18–25 age group** achieved the highest AOV at **$60.74**, indicating stronger premium purchasing behaviour

---

## Seasonal Performance Trends

| Season | Revenue |
|--------|----------|
| Fall | $60,018 |
| Spring | $58,679 |
| Winter | $58,607 |
| Summer | $55,777 |

### Key Findings
- **Fall was the strongest-performing season** with the highest AOV of **$61.56**
- **Summer recorded a 7.6% revenue decline** compared to Fall
- Revenue remained relatively stable across Spring and Winter

---

## Discount & Promotion Insights

- Customers **without discounts** spent slightly more on average (**$60.13**) than customers receiving discounts (**$59.28**)
- Promo codes showed **minimal impact on increasing purchase value**
- Current discount strategies may be impacting profit margins without generating proportional revenue growth

---

## Payment & Loyalty Behaviour

### Payment Distribution
Payment methods remained evenly distributed:
- PayPal: 17.4%
- Credit Card: 17.2%
- Cash: 17.2%
- Debit Card: 16.3%
- Venmo: 16.3%
- Bank Transfer: 15.7%

### Subscription Analysis
- Only **27% of customers** held active subscriptions
- Subscriber AOV (**$59.49**) remained close to non-subscribers (**$59.87**)
- This indicates significant potential for improving customer retention through subscription programs

---

## Purchase Frequency Analysis

- Purchase frequency was evenly distributed across Weekly, Monthly, Quarterly, and Annual buyers
- No single purchase cycle dominated customer behaviour
- Indicates the need for personalized customer engagement and retention strategies

---

# Business Recommendations

1. **Prioritize Clothing & Accessories**
   - These categories contribute **76.5% of total revenue**
   - High-return marketing campaigns should focus here

2. **Capitalize on Fall Seasonality**
   - Fall generated the highest revenue and AOV
   - Introduce targeted campaigns to offset Summer revenue decline

3. **Increase Subscription Conversion**
   - Current subscription adoption is only **27%**
   - Even modest growth in subscriptions could significantly improve recurring revenue

4. **Optimize Discount Strategies**
   - Discounts are not significantly increasing spending behaviour
   - Shift toward value-driven or loyalty-based promotions

5. **Target High-Value Age Segments**
   - Customers aged **56–70 years** represent the highest revenue-generating demographic
   - Tailored loyalty and retention programs could improve long-term customer value

---

## Repository Structure

```text
customer_behavior_analysis/
│
├── data/              # Raw and cleaned datasets
├── notebooks/         # Jupyter notebooks
├── sql/               # SQL analysis queries
├── dashboard/         # Power BI dashboard files
├── visuals/           # Charts and dashboard screenshots
├── reports/           # Final reports & presentations
└── README.md
```


## 7. How to Run the Project

1. Clone the repository
2. Install required Python library:

   ```
   pip install pandas psycopg2
   ```
3. Run the Python script for data cleaning
4. Import cleaned data into PostgreSQL
5. Execute SQL queries from the `/sql` folder
6. Open the `.pbix` file to explore the Power BI dashboard
7. Review the final report and presentation in the `/reports` folder

---

## 8. Business Value
This project demonstrates practical data analytics skills including data cleaning, SQL analysis, KPI reporting, dashboard development, and business insight generation. It reflects a real-world analytics workflow focused on supporting data-driven decision-making.
