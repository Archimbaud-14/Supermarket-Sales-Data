# 🛒 Basic EDA on Supermarket Sales Data

> Exploratory Data Analysis on supermarket transactions to uncover sales patterns across branches, product lines, and customer segments.

![Python](https://img.shields.io/badge/Python-3.13-3776AB?logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-2.3-150458?logo=pandas&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-3.10-11557C)
![Seaborn](https://img.shields.io/badge/Seaborn-0.13-4C72B0)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![Level](https://img.shields.io/badge/Level-Intermediate-orange)

---

## 📋 Table of Contents

- [About the Project](#-about-the-project)
- [Dataset Overview](#-dataset-overview)
- [Project Structure](#-project-structure)
- [Getting Started](#-getting-started)
- [Analysis Workflow](#-analysis-workflow)
- [Key Findings](#-key-findings)
- [Visualizations](#-visualizations)
- [Business Insights](#-business-insights)
- [Bonus Features](#-bonus-features)
- [Technologies Used](#-technologies-used)

---

## 📖 About the Project

This project performs a comprehensive **Exploratory Data Analysis (EDA)** on a supermarket sales dataset containing **1,000 transactions** from 3 branches across Myanmar. The goal is to understand sales patterns, customer behavior, and product performance using **groupby aggregations** and **data visualizations**.

### Objectives
- Assess data quality (missing values, data types, duplicates)
- Analyze sales by Branch, Product Line, Customer Type and Gender
- Identify the busiest shopping hours
- Rank top and bottom performing product lines
- Generate actionable business insights supported by visualizations

---

## 📊 Dataset Overview

| Property | Detail |
|----------|--------|
| **Source** | `supermarket_sales - Sheet1.csv` |
| **Records** | 1,000 transactions |
| **Columns** | 17 features |
| **Date Range** | January 2019 – March 2019 |
| **Branches** | A (Yangon), B (Mandalay), C (Naypyitaw) |
| **Missing Values** | None |
| **Duplicates** | None |

### Column Descriptions

| Column | Type | Description |
|--------|------|-------------|
| `Invoice ID` | String | Unique transaction identifier |
| `Branch` | Categorical | Store branch (A, B, C) |
| `City` | Categorical | City of the branch |
| `Customer type` | Categorical | Member or Normal |
| `Gender` | Categorical | Male or Female |
| `Product line` | Categorical | Product category (6 types) |
| `Unit price` | Float | Price per unit ($) |
| `Quantity` | Integer | Number of items purchased |
| `Tax 5%` | Float | 5% tax on purchase |
| `Total` | Float | Total including tax |
| `Date` | Date | Transaction date |
| `Time` | Time | Transaction time |
| `Payment` | Categorical | Payment method (Cash, Ewallet, Credit card) |
| `cogs` | Float | Cost of goods sold |
| `gross margin percentage` | Float | Gross margin % |
| `gross income` | Float | Gross income |
| `Rating` | Float | Customer rating (1–10) |

---

## 📁 Project Structure

```
Basic EDA on Supermarket Sales Data/
│
├── 📓 Supermarket_Sales_EDA.ipynb      # Main Jupyter notebook with full EDA
├── 📝 note.md                          # Methodology and key findings
├── 📄 README.md                        # Project documentation (this file)
├── 📊 supermarket_sales - Sheet1.csv   # Raw dataset
│
├── 🖼️ chart1_sales_by_product_line.png  # Bar chart — Sales by Product Line
├── 🖼️ chart2_customer_type_pie.png      # Pie chart — Customer Type distribution
├── 🖼️ chart3_hourly_sales_line.png      # Line chart — Hourly sales pattern
├── 🖼️ chart4_branch_customer_type.png   # Grouped bar — Branch & Customer Type
├── 🖼️ chart5_gender_product_line.png    # Horizontal bar — Gender & Product Line
└── 🖼️ chart6_heatmap_branch_product.png # Heatmap — Branch × Product Line (⭐ Bonus)
```

---

## 🚀 Getting Started

### Prerequisites

- Python 3.10+
- Jupyter Notebook

### Installation

```bash
# Clone or navigate to the project directory
cd "Basic EDA on Supermarket Sales Data"

# Install required packages
pip install pandas matplotlib seaborn jupyter

# Launch Jupyter Notebook
jupyter notebook Supermarket_Sales_EDA.ipynb
```

### Quick Run (without Jupyter)

```bash
jupyter nbconvert --to notebook --execute Supermarket_Sales_EDA.ipynb
```

---

## 🔄 Analysis Workflow

```
┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐
│  1. Data Load    │────▶│  2. Quality      │────▶│  3. Preprocess   │
│  & Inspection    │     │  Check           │     │  Date/Time       │
└─────────────────┘     └─────────────────┘     └─────────────────┘
                                                         │
         ┌───────────────────────────────────────────────┘
         ▼
┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐
│  4. Groupby      │────▶│  5. Time         │────▶│  6. Product      │
│  Analysis        │     │  Analysis        │     │  Ranking         │
└─────────────────┘     └─────────────────┘     └─────────────────┘
                                                         │
         ┌───────────────────────────────────────────────┘
         ▼
┌─────────────────┐     ┌─────────────────┐     ┌─────────────────┐
│  7. Visualize    │────▶│  8. Bonus        │────▶│  9. Business     │
│  (6 Charts)      │     │  Features        │     │  Insights        │
└─────────────────┘     └─────────────────┘     └─────────────────┘
```

**Step Details:**

1. **Data Loading** — Read CSV, inspect shape and column names
2. **Quality Check** — Missing values, duplicates, data types, descriptive stats
3. **Preprocessing** — Convert `Date` to datetime, extract `Hour` from `Time`
4. **Groupby Analysis** — Aggregate sales by Branch, Product Line, Customer Type, Gender
5. **Time Analysis** — Identify busiest/slowest hours
6. **Product Ranking** — Rank product lines by total revenue
7. **Visualizations** — 6 professional charts (bar, pie, line, grouped bar, horizontal bar, heatmap)
8. **Bonus** — Gross margin per product line + heatmap
9. **Insights** — 4 actionable business recommendations

---

## 🔍 Key Findings

| Metric | Value |
|--------|-------|
| 💰 **Total Revenue** | $322,966.75 |
| 📦 **Total Transactions** | 1,000 |
| 🧾 **Avg Order Value** | ~$322.97 |
| 🏆 **Top Product Line** | Food and beverages ($56,145) |
| ⚠️ **Bottom Product Line** | Health and beauty ($49,194) |
| ⏰ **Busiest Hour** | 19:00 (7 PM) |
| 👥 **Member vs Normal** | 50.1% vs 49.9% |
| 📊 **Gross Margin** | ~4.76% (uniform across all lines) |

---

## 📈 Visualizations

### Chart 1 — Total Sales by Product Line (Bar Chart)
> Shows revenue comparison across all 6 product categories. Food & beverages leads at $56,145.

### Chart 2 — Customer Type Distribution (Pie Chart)
> Nearly perfect 50/50 split between Member (501) and Normal (499) customers.

### Chart 3 — Hourly Sales Pattern (Dual-Axis Line Chart)
> Reveals 19:00 as the peak hour with both highest sales volume and order count. Features an annotated busiest hour marker.

### Chart 4 — Sales by Branch & Customer Type (Grouped Bar)
> Compares Member vs Normal spending at each branch. Shows balanced distribution with minor variations.

### Chart 5 — Sales by Gender & Product Line (Horizontal Bar)
> Highlights purchasing preferences between male and female customers across product categories.

### Chart 6 — Heatmap: Branch × Product Line (⭐ Bonus)
> Color-coded matrix revealing that Branch C dominates Food & beverages ($23,767) while Branch A leads in Home & lifestyle ($22,417).

---

## 💡 Business Insights

### 1. 🏪 Balanced Branch Performance
All three branches generate comparable revenue (~$106K–$110K each). Branch C (Naypyitaw) has a slight edge, suggesting it captures higher-value transactions. **Recommendation:** Investigate and replicate C's successful practices across A and B.

### 2. ⏰ Strategic Peak Hour at 19:00
The busiest shopping hour is 7 PM with notable afternoon peaks around 13:00. **Recommendation:** Maximize staffing during 13:00 and 18:00–20:00 windows; schedule promotions and flash sales during these periods.

### 3. 👥 Untapped Membership Potential
The Member/Normal split is nearly 50/50 with no significant spending difference. **Recommendation:** Introduce tiered loyalty benefits (exclusive discounts, early access) to incentivize Normal customers to join and Members to increase basket sizes.

### 4. 🛍️ Narrow Product Line Spread
Revenue difference between top and bottom product lines is only ~$7K. **Recommendation:** Bundle lower-performing categories (Health & beauty) with popular ones (Food & beverages) for cross-selling to boost underperforming segments.

---

## ⭐ Bonus Features

| Feature | Description |
|---------|-------------|
| **Gross Margin Analysis** | Calculated margin % per product line — uniform 4.76% indicates standardized pricing |
| **Branch × Product Heatmap** | Visual matrix showing hot/cold spots in branch-product performance |
| **Payment Method Analysis** | Breakdown of Cash, Ewallet, and Credit card usage patterns |
| **Dual-Axis Chart** | Hourly sales with both revenue and order count on the same chart |

---

## 🛠️ Technologies Used

| Tool | Purpose |
|------|---------|
| **Python 3.13** | Core programming language |
| **pandas** | Data manipulation and groupby analysis |
| **matplotlib** | Chart creation and customization |
| **seaborn** | Heatmap and enhanced styling |
| **Jupyter Notebook** | Interactive development environment |

---

## 📝 Deliverables Checklist

- [x] Jupyter notebook with EDA code and comments
- [x] `note.md` with methodology and key findings
- [x] Bar chart of sales by Product Line
- [x] Pie chart of Customer Type
- [x] Line chart of hourly sales
- [x] 4 business insights
- [x] ⭐ Gross margin per product line
- [x] ⭐ Heatmap of sales by Branch & Product Line

---

## 📜 License

This project is for educational purposes as part of a data analysis learning track.

---

<p align="center">
  <i>Built with 🐍 Python | 📊 pandas | 🎨 matplotlib + seaborn</i>
</p>
