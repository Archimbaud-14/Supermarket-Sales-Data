# 📝 Note: Basic EDA on Supermarket Sales Data

## Methodology

### 1. Data Loading & Quality Check
- Loaded `supermarket_sales - Sheet1.csv` containing **1,000 transactions** across 17 columns
- Checked for **missing values** → No missing data found
- Checked for **duplicate rows** → No duplicates detected
- Reviewed all **data types** and identified Date/Time columns that needed conversion

### 2. Data Preprocessing
- **Date column**: Converted from string to `datetime64` format for temporal analysis
- **Time column**: Converted to proper time format and extracted the `Hour` component
- Created additional features: `Day_of_Week`, `Month` for deeper analysis

### 3. Groupby Analysis
Aggregated total sales and order counts by four dimensions:
- **Branch** (A – Yangon, B – Mandalay, C – Naypyitaw)
- **Product Line** (6 categories)
- **Customer Type** (Member vs Normal)
- **Gender** (Male vs Female)

### 4. Time Analysis
- Extracted hour from the Time column to identify hourly traffic patterns
- Identified the **busiest** and **slowest** hours of the day

### 5. Product Line Performance
- Ranked all 6 product lines by total revenue
- Identified top and bottom performers

### 6. Visualizations Created
| # | Chart Type | Description | File |
|---|-----------|-------------|------|
| 1 | Bar Chart | Total Sales by Product Line | `chart1_sales_by_product_line.png` |
| 2 | Pie Chart | Customer Type Distribution | `chart2_customer_type_pie.png` |
| 3 | Line Chart | Hourly Sales Pattern (dual-axis) | `chart3_hourly_sales_line.png` |
| 4 | Grouped Bar | Sales by Branch & Customer Type | `chart4_branch_customer_type.png` |
| 5 | Horizontal Bar | Sales by Gender & Product Line | `chart5_gender_product_line.png` |
| 6 | Heatmap ⭐ | Sales by Branch & Product Line | `chart6_heatmap_branch_product.png` |

### 7. Bonus Features
- **Gross Margin Percentage**: Calculated per product line — the gross margin is uniformly ~4.76% across all product lines, indicating a standardized pricing policy
- **Heatmap**: Shows how each branch performs across different product lines, revealing which branch-product combinations are strongest

---

## Key Findings

### 🏪 Branch Performance
- All three branches generate **similar total revenue**, showing a well-balanced geographic distribution
- Branch C (Naypyitaw) has a slight lead in total sales
- Average order values are comparable across branches

### 🛍️ Product Line Insights
- **Food and beverages** is among the top-performing categories
- The revenue spread between the highest and lowest product lines is relatively **narrow** (~$4k–$6k difference), indicating balanced demand
- All product lines maintain the **same gross margin percentage** (~4.76%)

### 👥 Customer Demographics
- **Member vs Normal** split is nearly 50/50 in both volume and revenue
- Gender distribution is also balanced — both male and female customers contribute similarly
- No significant spending difference between customer types suggests room for a stronger loyalty program

### ⏰ Time Patterns
- Supermarket traffic is spread across operating hours (10:00–20:00)
- There are clear **peak hours** in the afternoon window
- Slowest hours tend to be at the edges of operating time

---

## 💡 4 Business Insights

### 1. Balanced Branch Performance with Slight Naypyitaw Lead
All three branches (A – Yangon, B – Mandalay, C – Naypyitaw) generate comparable total revenue, showing a well-distributed customer base. Branch C (Naypyitaw) has a slight edge in total sales, suggesting it captures higher-value transactions. Management should investigate whether this is due to product mix, customer demographics, or pricing strategies and replicate successful practices across branches.

### 2. Peak Sales Hours from 10:00 to 20:00 with Notable Spikes
The supermarket experiences significant traffic during afternoon hours, with the busiest shopping window clearly visible in the hourly analysis. Staffing strategies should ensure **maximum checkout capacity** during peak hours, and promotional campaigns (flash deals, sampling events) should be timed to these windows to maximize conversion.

### 3. Member vs Normal Customers Are Nearly Equal
The customer type split between Member and Normal is nearly 50/50, both in volume and total sales. This suggests the membership program is well-adopted but may not be driving significantly higher spending. The business should **introduce tiered loyalty benefits** (e.g., exclusive discounts, early access) to incentivize Normal customers to sign up and encourage Members to increase basket sizes.

### 4. Product Line Revenue Spread Is Narrow
The difference between the top-performing and bottom-performing product lines is relatively small, indicating a balanced product portfolio. Categories like **Food and beverages** consistently rank among the top, suggesting they are staple drivers. The store could **bundle lower-performing categories** with popular ones for cross-selling opportunities to boost underperforming segments.

---

## Technical Stack
- **Python**: pandas, matplotlib, seaborn
- **Environment**: Jupyter Notebook
- **Dataset**: `supermarket_sales - Sheet1.csv` (1,000 rows × 17 columns)

---

*Analysis completed on April 2026*
