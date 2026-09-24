<div align="center">

# 📊 Business Performance & Decision Analytics

### End-to-End Business Intelligence, Automated Data Validation, Exception Monitoring & Root Cause Analysis

**Power BI • SQL • MySQL • DAX • Power Query • n8n**

<br>

[![Power BI](https://img.shields.io/badge/Power%20BI-Business%20Intelligence-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](#)
[![MySQL](https://img.shields.io/badge/MySQL-Database-4479A1?style=for-the-badge&logo=mysql&logoColor=white)](#)
[![SQL](https://img.shields.io/badge/SQL-Analytics-336791?style=for-the-badge)](#)
[![n8n](https://img.shields.io/badge/n8n-Workflow%20Automation-EA4B71?style=for-the-badge&logo=n8n&logoColor=white)](#)

<br>

### 🔴 [View Live Power BI Dashboard](https://app.powerbi.com/groups/me/reports/90fb40a0-9359-4ef1-83dd-0d78bb2f56c0/1e951ce58e30e5c58486?experience=power-bi)

📄 [View Full Dashboard PDF](06_Report/Business-Performance-Decision-Analytics.pdf)

</div>

---

# 📌 Project Overview

This project is an end-to-end **Business Performance & Decision Analytics system** designed to help management understand not only:

> **“What happened?”**

but also:

> **“Where is the problem?” → “Why did it happen?” → “What requires attention?”**

The project combines:

- Financial performance analysis
- Customer and product analytics
- Regional and market profitability
- Forecast accuracy analysis
- Inventory risk monitoring
- Executive-level KPI reporting
- Exception / alert monitoring
- Root Cause Analysis
- Automated data validation and ingestion

The analytical journey is:

```text
RAW BUSINESS DATA
       ↓
DATA VALIDATION
       ↓
MYSQL DATABASE
       ↓
POWER BI DATA MODEL
       ↓
PERFORMANCE MONITORING
       ↓
ALERTS / EXCEPTIONS
       ↓
ROOT CAUSE ANALYSIS
       ↓
BUSINESS ACTION
```

The goal was to move beyond a traditional static dashboard and create a system that supports **management decision-making**.

---

# 🎯 Business Problem

The company operates across multiple:

- Markets
- Regions
- Customers
- Products
- Divisions
- Sales channels

and generates data across Finance, Sales, Marketing and Supply Chain.

The core management problem was that strong revenue performance did **not necessarily translate into profitability**.

Management needed answers to questions such as:

### Financial Performance

- Are sales increasing?
- Is gross margin improving or declining?
- Is revenue growth translating into profit?
- Which costs are affecting profitability?

### Customer & Product Performance

- Which customers generate the most revenue?
- Which products contribute most to sales?
- Which customers/products have weak margins?
- Which products are generating losses?

### Regional Performance

- Which regions and markets are profitable?
- Which markets are responsible for losses?
- Are high-revenue markets also profitable?

### Supply Chain

- How accurate are forecasts?
- Where are forecast errors concentrated?
- Which products are at risk of stock-out?
- Which products have excess inventory?

### Management Monitoring

- Which issues require immediate attention?
- Where should management investigate first?

### Root Cause Analysis

When a KPI deteriorates:

> **WHY did it happen?**

The system needed to allow management to drill from:

```text
Company
  ↓
Region
  ↓
Market
  ↓
Customer
  ↓
Segment
  ↓
Product
```

to identify the source of a business problem.

---

# ⭐ Project Story — STAR Framework

<details>
<summary><b>Click to expand — Interview-ready STAR explanation</b></summary>

## S — Situation

The business had data across multiple functional areas such as:

- Finance
- Sales
- Customer performance
- Product performance
- Supply Chain
- Market performance

However, simply reporting revenue was not enough.

The company could grow sales while simultaneously:

- Losing margin
- Increasing operating costs
- Generating losses
- Creating excess inventory
- Experiencing stock-outs

There was also a need to improve reliability of incoming data before it entered the reporting database.

---

## T — Task

The objective was to build an analytics solution capable of:

1. Monitoring business performance.
2. Comparing current performance with previous year / targets.
3. Identifying loss-making markets and products.
4. Monitoring forecast and inventory risk.
5. Automatically validating incoming data.
6. Highlighting important exceptions.
7. Enabling root-cause analysis.
8. Providing executives with a consolidated view of business performance.

---

## A — Action

I developed the solution using:

### Data & Database

- MySQL
- SQL
- Dimensional data model

### Data Transformation

- Power Query
- Data cleaning
- Data validation
- Data type standardization

### Analytics

- DAX
- KPI calculations
- Previous-year comparison
- Profitability analysis
- Forecast accuracy
- Net Error
- Absolute Error
- Stock risk classification

### Visualization

Power BI dashboards covering:

- Finance
- Sales / Customer
- Product / Market
- Supply Chain
- Executive Analysis
- Root Cause Analysis
- Alerts / Exceptions

### Automation

An n8n workflow was added to validate incoming CSV sales data before inserting it into MySQL.

The workflow performs:

```text
Email / CSV
      ↓
Extract Data
      ↓
Validate Structure & Values
      ↓
SQL Reference Validation
      ↓
Final Validation
      ↓
Validation Summary
      ↓
Human Approval
      ↓
Insert Validated Rows into MySQL
```

This reduces the risk of invalid records entering the analytical database.

---

## R — Result / Decision-Support Outcome

The completed analytical system revealed an important business contradiction:

> Revenue increased strongly, but profitability deteriorated significantly.

The dashboard identified:

- High revenue growth
- Margin deterioration
- Large negative Net Profit
- Major loss-making markets
- Product-level profit problems
- Customer forecast accuracy issues
- Stock-out and excess inventory risks

The addition of **Alerts** identifies where management needs to focus.

The addition of **RCA** explains why the problem is occurring.

Therefore the analytical flow became:

> **Monitor → Detect → Diagnose → Act**

> **Important:** This project demonstrates analytical findings and decision-support capability. It does not claim that these recommendations were deployed in a real company or generated measured financial improvement.

</details>

---

# 🧠 Core Business Finding

The most important finding from the dashboard is:

> ### Revenue growth is not converting into profitable growth.

For the current FY2021 dashboard context:

| KPI | Current | Previous Year | Observation |
|---|---:|---:|---|
| Net Sales | **$823.85M** | $267.98M | **+207.43%** |
| Gross Margin | **$300.63M** | $99.42M | Increased |
| Gross Margin % | **36.49%** | 37.10% | Declined |
| Operational Cost | **$355.28M** | $101.71M | Increased significantly |
| Net Profit | **-$54.65M** | -$2.29M | Loss increased |
| Net Profit Margin | **-6.63%** | -0.85% | Profitability deteriorated |

### Business interpretation

Sales growth alone gives an incomplete picture.

Although Net Sales increased significantly:

```text
Gross Margin      = $300.63M
Operational Cost  = $355.28M
--------------------------------
Net Profit        = -$54.65M
```

The company generated enough Gross Margin to cover direct product costs, but **operating costs exceeded Gross Margin**.

This ultimately pushed the company into a substantial loss.

---

# 💰 Revenue Leakage / Deduction Analysis

The P&L also reveals substantial deductions between Gross Sales and Net Sales.

```text
Gross Sales                 $1,664.64M
        ↓
Pre-Invoice Deduction         $392.50M
        ↓
Net Invoice Sales           $1,272.13M
        ↓
Post-Invoice Deductions       $448.29M
        ↓
Net Sales                     $823.85M
```

This means management should investigate:

- Discount policy
- Customer-level deductions
- Post-invoice discount leakage
- Promotion effectiveness
- Customer profitability after deductions

because revenue growth is meaningful only when sufficient margin is retained.

---

# 🌍 Regional Profitability Analysis

Regional analysis revealed that sales contribution and profitability are not always aligned.

| Region | Net Sales | Gross Margin % | Net Profit | Net Profit % |
|---|---:|---:|---:|---:|
| APAC | **$441.98M** | 35.3% | **-$33.33M** | -7.5% |
| EU | $200.77M | 38.3% | **+$2.81M** | +1.4% |
| LATAM | $3.16M | 37.5% | +$0.20M | +6.2% |
| Unclassified | $177.94M | 37.2% | **-$24.32M** | -13.7% |

### Key interpretation

APAC is the company's largest revenue region but also contributes substantial losses.

This demonstrates an important analytics principle:

> **High revenue ≠ high profitability**

EU, by comparison, generates lower sales but remains profitable.

### Data-quality observation

A material amount of revenue is currently categorized as:

> **Unclassified**

This should be investigated at the source/master-data level so revenue can be correctly mapped to geographical dimensions.

---

# 📦 Product Profitability Analysis

Major product segments generated significant revenue but still produced negative profit.

Examples:

| Product Segment | Net Sales | Net Profit | Net Profit % |
|---|---:|---:|---:|
| Notebook | **$266.49M** | **-$17.71M** | -6.6% |
| Accessories | $244.85M | **-$16.28M** | -6.7% |
| Peripherals | $166.51M | **-$11.02M** | -6.6% |
| Storage | $54.42M | -$3.46M | -6.4% |
| Networking | $45.16M | -$2.91M | -6.4% |

### Interpretation

The highest-selling product categories are not necessarily generating profit.

Management therefore needs to evaluate:

- Product pricing
- Discounts
- Manufacturing cost
- Freight cost
- Product-level operational expenses
- Customer/product mix

rather than optimizing only for sales volume.

---

# 👥 Customer Analysis

The Customer Performance page allows analysis of:

- Net Sales
- Gross Margin
- Gross Margin %
- Customer contribution
- Customer-market combinations

Examples from the dashboard include:

| Customer | Net Sales | Gross Margin | GM % |
|---|---:|---:|---:|
| Amazon | **$109.03M** | $38.59M | 35.4% |
| AtliQ Exclusive | $79.92M | $34.95M | **43.7%** |
| Atliq e Store | $70.31M | $26.40M | 37.5% |

### Analytical value

A customer generating more revenue is not automatically the better customer.

Customer profitability should be evaluated using:

```text
Revenue
+
Gross Margin %
+
Discounts / Deductions
+
Product Mix
+
Cost to Serve
```

---

# 🚚 Supply Chain & Forecast Analysis

The Supply Chain dashboard monitors:

- Forecast Accuracy
- Previous-year Forecast Accuracy
- Net Error
- Absolute Error
- Stock risk
- Product risk
- Customer forecasting performance

### Overall KPIs

| KPI | Current | Previous Year |
|---|---:|---:|
| Forecast Accuracy | **80.21%** | 72.99% |
| Net Error | **-751.71K** | +491.6K |
| Absolute Error | **9.78M** | 5.74M |

### Important analytical insight

Forecast Accuracy improved from approximately:

```text
72.99% → 80.21%
```

but Absolute Error increased by roughly:

```text
+70.3%
```

This means the overall percentage accuracy alone should **not** be used to judge forecast performance.

The business must also consider:

- Scale of forecast error
- Product volume
- Customer contribution
- Over-forecasting
- Under-forecasting
- Inventory consequence

---

# ⚠️ Inventory Risk

The dashboard classifies inventory risks into:

### Out of Stock

Generally associated with negative Net Error / insufficient supply relative to demand.

Potential impact:

- Lost sales
- Poor customer service
- Delayed orders
- Reduced market opportunity

### Excess Inventory

Generally associated with positive Net Error / excess inventory relative to demand.

Potential impact:

- Working-capital blockage
- Storage costs
- Obsolescence risk
- Markdown / discount pressure

Examples of segment-level risk include:

- Accessories → Out of Stock
- Notebook → Out of Stock
- Peripherals → Out of Stock
- Desktop → Excess
- Networking → Excess
- Storage → Excess

---

# 👔 Executive Dashboard

The Executive page consolidates the most important business KPIs:

```text
Net Sales
Gross Margin %
Net Profit %
Forecast Accuracy
```

with analysis across:

- Sub-zone
- Division
- Channel
- Market share
- Customer contribution
- Product contribution

---

## Revenue by Division

```text
P & A   → 49.93%
PC      → 37.98%
N & S   → 12.09%
```

This shows that almost half of revenue is generated by the P&A division.

---

## Revenue by Channel

```text
Retailer     → 70.55%
Direct       → 18.24%
Distributor  → 11.22%
```

### Interpretation

The company depends heavily on the Retailer channel.

This is not automatically negative, but management should monitor:

- Channel concentration
- Channel margins
- Discount requirements
- Customer dependency

---

# 🔎 Root Cause Analysis — RCA

Traditional dashboards answer:

> **WHAT happened?**

The RCA page was added to answer:

> **WHY did it happen?**

The page contains:

### 1. Net Profit Trend

Shows **when** profitability deteriorated.

### 2. Top Negative Profit Contributors

Shows **which products** are contributing most heavily to losses.

### 3. Decomposition Tree

Allows management to drill through:

```text
Net Profit
    ↓
Region
    ↓
Market
    ↓
Customer
    ↓
Segment
    ↓
Product
```

An example analytical drill path visible in the dashboard is:

```text
Overall Net Profit
      ↓
APAC
      ↓
India
      ↓
Amazon
      ↓
Notebook
      ↓
Individual Products
```

This enables management to move from a company-level KPI to the individual product responsible for the problem.

---

# 🚨 Alerts / Exception Dashboard

The Alerts page answers:

> ### “Where should management pay attention right now?”

Instead of manually scanning every dashboard, exceptions are automatically summarized.

The dashboard monitors four major alert groups:

| Alert | Meaning |
|---|---|
| Critical Alerts | Immediate high-priority exceptions |
| Loss-Making Markets | Markets where Net Profit < 0 |
| Low-Accuracy Customers | Customers below forecast threshold |
| Stock Risk Products | Products classified as OOS or Excess |

---

## Critical Alert Logic

Critical Alerts combine:

```text
Loss-Making Markets
+
Out-of-Stock Products
```

This creates an executive-level count of the most urgent exception instances.

---

## Loss-Making Markets

Markets with:

```text
Net Profit < 0
```

are surfaced and ranked so that the largest losses receive attention first.

Examples visible in the default view include:

- India
- USA
- United Kingdom
- Spain
- Canada
- Germany
- Australia

---

## Low Forecast Accuracy

A configurable threshold of:

```text
Forecast Accuracy < 70%
```

is used to highlight customers that may require forecasting review.

The 70% value is a **demonstration / monitoring threshold**, not a claim that every business should use the same target.

---

## Stock Risk Products

Products are prioritized using:

```text
Stock Risk
+
Net Error
+
Forecast Accuracy
```

Out-of-Stock products receive high attention because insufficient supply may directly affect sales.

---

# 🧭 Complete Decision Journey

The project follows this management decision flow:

```text
EXECUTIVE PAGE
       │
       ▼
How is the company performing?
       │
       ▼
ALERTS
       │
       ▼
Where is the problem?
       │
       ▼
RCA
       │
       ▼
Why is the problem occurring?
       │
       ▼
FINANCE / SALES / SUPPLY CHAIN
       │
       ▼
What operational factor caused it?
       │
       ▼
BUSINESS ACTION
```

This is the core idea behind the project:

> ### Executive → Alert → RCA → Action

---

# ⚙️ Automated Data Validation Workflow

Dashboard accuracy depends on data quality.

For this reason, an **n8n validation workflow** was added before new sales data enters the database.

### Workflow

```text
Gmail Trigger
      ↓
CSV Extraction
      ↓
Row-Level Validation
      ↓
SQL Reference Validation
      ↓
Final Validation
      ↓
Validation Summary
      ↓
Human Approval
      ↓
Validated Rows Restored
      ↓
MySQL Insert
```

### Validation checks include

- Product code validation
- Customer code validation
- Date validation
- Required-field checks
- Invalid-row identification
- Summary of valid and invalid records

Every record receives validation fields such as:

```text
product_exists
customer_exists
date_exists
_validation_errors
_is_valid
```

Only validated data is allowed to continue to the database after approval.

---

# 🤝 Human-in-the-Loop Approval

Instead of blindly inserting uploaded data, the automation creates a validation summary containing:

```text
Total Rows
Valid Rows
Invalid Rows
Validation Status
Invalid Record Details
```

A human approval step is then used before data insertion.

This provides an additional control layer for business-critical reporting data.

---

# 🗄️ Data Model

The analytical model uses fact and dimension tables including:

```text
DIMENSIONS
├── dim_date
├── dim_customer
└── dim_product

FACT / TRANSACTION TABLES
├── fact_sales_monthly
├── fact_forecast_monthly
├── fact_gross_price
├── fact_manufacturing_cost
├── fact_freight_cost
├── fact_pre_invoice_deductions
└── fact_post_invoice_deductions
```

Additional business tables support:

- Operational cost
- Targets
- Market share
- Benchmark comparisons

The core sales data is modeled at approximately:

```text
Date × Product × Customer
```

grain.

---

# 🧮 Important KPI Definitions

## Net Sales

Revenue remaining after invoice and post-invoice deductions.

---

## Gross Margin

```text
Gross Margin =
Net Sales - COGS
```

---

## Gross Margin %

```text
Gross Margin % =
Gross Margin / Net Sales
```

---

## Net Profit

```text
Net Profit =
Gross Margin - Operational Cost
```

---

## Net Profit %

```text
Net Profit % =
Net Profit / Net Sales
```

---

## Forecast Error

Represents the difference between forecasted demand and actual demand.

---

## Absolute Error

Removes positive / negative direction and measures overall magnitude of forecasting error.

---

## Forecast Accuracy

Measures how closely forecasted demand matches actual demand.

---

## Net Error

Direction of forecast error.

It helps identify:

```text
Positive Error → Excess tendency
Negative Error → Stock-out tendency
```

---

# 📊 Dashboard Pages

| Page | Main Decision Question |
|---|---|
| 🏠 Business Insights | What does each dashboard help management analyze? |
| 💰 Finance | Is revenue growth translating into profit? |
| 🤝 Customer / Sales | Which customers and products drive performance? |
| 📈 Product / Market | Which products and regions are profitable or loss-making? |
| 🚚 Supply Chain | Where are forecast and inventory risks occurring? |
| 👔 Executive | What is the overall health of the business? |
| 🔎 RCA | Why did profitability deteriorate? |
| 🚨 Alerts | Which problems require immediate attention? |

---

# 🖼️ Dashboard Preview

<details>
<summary><b>🏠 Business Insights</b></summary>

<br>

![Business Insights](01_PowerBI_Dashboard/Dashboard_Screenshots/01_Business_Insights.png)

</details>

<details>
<summary><b>💰 Finance Dashboard</b></summary>

<br>

![Finance](01_PowerBI_Dashboard/Dashboard_Screenshots/02_Finance.png)

</details>

<details>
<summary><b>🤝 Customer & Sales Analytics</b></summary>

<br>

![Customer Analytics](01_PowerBI_Dashboard/Dashboard_Screenshots/03_Sales_Customer.png)

</details>

<details>
<summary><b>📦 Product & Market Analytics</b></summary>

<br>

![Product Market](01_PowerBI_Dashboard/Dashboard_Screenshots/04_Product_Market.png)

</details>

<details>
<summary><b>🚚 Supply Chain</b></summary>

<br>

![Supply Chain](01_PowerBI_Dashboard/Dashboard_Screenshots/05_Supply_Chain.png)

</details>

<details>
<summary><b>👔 Executive Dashboard</b></summary>

<br>

![Executive](01_PowerBI_Dashboard/Dashboard_Screenshots/06_Executive.png)

</details>

<details>
<summary><b>🔎 Root Cause Analysis</b></summary>

<br>

![RCA](01_PowerBI_Dashboard/Dashboard_Screenshots/07_RCA.png)

</details>

<details>
<summary><b>🚨 Alerts & Exceptions</b></summary>

<br>

![Alerts](01_PowerBI_Dashboard/Dashboard_Screenshots/08_Alerts.png)

</details>

---

# 💡 Major Business Insights

### 1️⃣ Sales growth is not profitable growth

Net Sales increased strongly to:

> **$823.85M**

but Net Profit deteriorated to:

> **-$54.65M**

Therefore management should optimize for **profitable revenue**, not sales growth alone.

---

### 2️⃣ Operational cost is a major profitability pressure

```text
Gross Margin      = $300.63M
Operational Cost  = $355.28M
Net Profit        = -$54.65M
```

Operational expenses exceed Gross Margin.

---

### 3️⃣ APAC requires immediate profitability investigation

APAC generated:

```text
Net Sales  → $441.98M
Net Profit → -$33.33M
NP Margin  → -7.5%
```

It contributes the highest regional revenue while still producing substantial loss.

---

### 4️⃣ High-selling product categories are loss-making

Notebook and Accessories are among the largest product categories by revenue while also contributing significant negative profit.

Revenue optimization must therefore be combined with:

> **Product-level contribution margin analysis**

---

### 5️⃣ Forecast performance improved, but error magnitude increased

Overall Forecast Accuracy improved to:

> **80.21%**

while Absolute Error increased by approximately:

> **70.3%**

This indicates the need to evaluate both percentage accuracy and absolute error magnitude.

---

### 6️⃣ Inventory imbalance exists in both directions

The business experiences:

```text
OUT OF STOCK
+
EXCESS INVENTORY
```

simultaneously across different product groups.

This suggests forecasting and inventory planning needs to become more granular.

---

### 7️⃣ Data governance requires improvement

A significant revenue amount remains categorized as:

> **Unclassified**

Master-data mapping should be improved so regional profitability can be fully attributed.

---

# 🎯 Recommended Business Actions

## Priority 1 — Restore Profitability

Management should prioritize:

- APAC profitability
- India-level loss drivers
- Loss-making customers
- Loss-making products
- Discount and deduction leakage
- Operational-cost drivers

---

## Priority 2 — Protect Margin

Review:

```text
Pricing
Discounts
Pre-Invoice Deductions
Post-Invoice Deductions
Manufacturing Cost
Freight Cost
Operating Cost
```

Revenue growth should be evaluated only after considering contribution margin.

---

## Priority 3 — Improve Forecasting Where Business Impact Is Highest

Instead of optimizing only overall Forecast Accuracy:

prioritize forecasting improvements for:

- High-volume customers
- High-revenue products
- OOS products
- High absolute-error products

---

## Priority 4 — Reduce Inventory Imbalance

### OOS products

Focus on preventing:

- Lost revenue
- Order delays
- Customer dissatisfaction

### Excess products

Focus on reducing:

- Working-capital lockup
- Storage cost
- Markdown risk
- Obsolescence

---

## Priority 5 — Improve Data Governance

Resolve:

- Unclassified geographical records
- Product/customer reference inconsistencies
- Invalid incoming transaction records

The automated validation workflow helps prevent new data-quality issues from entering the database.

---

# 🧰 Technology Stack

| Area | Technology |
|---|---|
| BI & Visualization | Power BI |
| Database | MySQL |
| Analysis | SQL |
| Data Transformation | Power Query |
| Analytics Logic | DAX |
| Automation | n8n |
| Input Automation | Gmail / CSV |
| Data Modeling | Star / Dimensional Modeling |
| Version Control | GitHub |

---

# 📂 Repository Structure

```text
business-performance-decision-analytics/
│
├── README.md
├── LICENSE
│
├── 01_PowerBI_Dashboard/
│   ├── Business-Performance-Decision-Analytics.pbix
│   └── Dashboard_Screenshots/
│       ├── 01_Business_Insights.png
│       ├── 02_Finance.png
│       ├── 03_Sales_Customer.png
│       ├── 04_Product_Market.png
│       ├── 05_Supply_Chain.png
│       ├── 06_Executive.png
│       ├── 07_RCA.png
│       └── 08_Alerts.png
│
├── 02_Automation/
│   ├── n8n_Workflow/
│   ├── Screenshots/
│   └── Test_Data/
│
├── 03_SQL/
│   ├── Database_Schema.sql
│   ├── Data_Validation_Queries.sql
│   └── Test_Data_Cleanup.sql
│
├── 04_DAX/
│   ├── Core_Measures.md
│   ├── RCA_Measures.md
│   └── Alert_Measures.md
│
├── 05_Documentation/
│   ├── Project_Architecture.png
│   ├── Data_Model.png
│   ├── Business_Problem.md
│   └── Key_Insights.md
│
├── 06_Report/
│   └── Business-Performance-Decision-Analytics.pdf
│
└── 07_Assets/
    ├── Logo/
    └── Icons/
```

---

# 🧑‍💼 Interview Quick Recall

If I had only **60–90 seconds** to explain this project:

> I built an end-to-end Business Performance and Decision Analytics solution using MySQL, SQL, Power BI, DAX, Power Query and n8n. The main business problem was that strong revenue growth was not converting into profitability. In the selected 2021 view, Net Sales reached $823.85M, over 207% higher than the previous year, but Net Profit deteriorated to approximately -$54.65M because operating costs exceeded Gross Margin. I analyzed the problem across regions, markets, customers and products and found APAC to be a major loss contributor despite being the largest revenue region. On the Supply Chain side, forecast accuracy improved to around 80%, but absolute forecast error increased significantly and both stock-out and excess inventory risks existed. I therefore added an Alerts page to identify where management should focus and an RCA page using a decomposition tree to drill from company-level Net Profit down to region, market, customer, segment and product. I also built an n8n workflow that validates incoming CSV data before approved records are inserted into MySQL. The final system supports a Monitor → Detect → Diagnose → Act decision-making process.

---

# 🧠 Interview Memory Map

Remember the project in only five words:

```text
GROWTH
   ↓
LOSS
   ↓
ALERT
   ↓
ROOT CAUSE
   ↓
ACTION
```

### GROWTH

Net Sales grew strongly.

### LOSS

Profitability deteriorated despite sales growth.

### ALERT

Exception monitoring identifies where attention is needed.

### ROOT CAUSE

RCA drills from Region → Market → Customer → Segment → Product.

### ACTION

Management gets specific areas to investigate instead of only seeing dashboard KPIs.

---

# 🔑 Three Numbers to Remember for Interviews

```text
$823.85M
Net Sales

-$54.65M
Net Profit

80.21%
Forecast Accuracy
```

If I remember these three numbers, I can reconstruct almost the entire project story.

---

# ⚡ Three Business Insights to Remember

```text
1. Revenue ↑ but Profit ↓
2. APAC = High Revenue + Large Loss
3. Forecast Accuracy ↑ but Absolute Error also ↑
```

These three observations summarize the analytical value of the project.

---

# 🛡️ Portfolio Accuracy / Limitations

This project should be interpreted as a portfolio analytics and decision-support solution.

Important limitations:

- The analytics demonstrate identified business problems and recommendations.
- Recommendations have not been claimed as deployed business outcomes.
- Financial improvement resulting from the recommendations has not been measured.
- The 70% Forecast Accuracy alert level is a configurable demonstration threshold.
- Power BI Desktop refresh is used where automated Power BI Service refresh is unavailable.
- “Unclassified” geographical data indicates records requiring improved master-data mapping.

These limitations are intentionally documented to keep the project transparent and reproducible.

---

# 🚀 Skills Demonstrated

This project demonstrates practical ability in:

- Business problem understanding
- KPI design
- Financial analysis
- P&L analysis
- Customer analytics
- Product analytics
- Regional profitability
- Supply Chain analytics
- Forecast analysis
- Inventory risk
- SQL
- MySQL
- Power Query
- DAX
- Data modeling
- Power BI
- Root Cause Analysis
- Exception reporting
- Workflow automation
- Data validation
- Human-in-the-loop approval
- Business storytelling

---

# 🔗 Project Links

### 🌐 Live Dashboard

[Open Business Performance & Decision Analytics in Power BI](https://app.powerbi.com/groups/me/reports/90fb40a0-9359-4ef1-83dd-0d78bb2f56c0/1e951ce58e30e5c58486?experience=power-bi)

### 📄 PDF Report

[View Dashboard PDF](06_Report/Business-Performance-Decision-Analytics.pdf)

---

<div align="center">

## ⭐ If you found this project useful, consider starring the repository.

### Business Performance & Decision Analytics

**Monitor → Detect → Diagnose → Act**

</div>
