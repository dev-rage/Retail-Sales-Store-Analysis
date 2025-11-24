# Retail-Sales-Store-Analysis | Revenue, Trends and Insights
Excel Project | Retail Sales Data | From Raw Data to Business Insights

### Project Overview
This project explores and analyzes sales data from a retail store to uncover key business insights. The main goal is to understand sales performance trends, identify top-performing products, and create a visually appealing Excel dashboard that summarizes these insights for decision-making.

Using Microsoft Excel, the dataset is cleaned and prepared to ensure accuracy and consistency. Key analyses include exploring total sales over time, comparing product categories, and highlighting the highest revenue-generating products. The final dashboard provides an interactive view of sales trends, product performance, and profitability metrics, enabling stakeholders to make data-driven business decisions.

This project demonstrates my ability to clean, analyze, and visualize real-world sales data — showcasing practical skills in Excel functions, data visualization, and dashboard creation relevant to business analytics.

### Tools & Techniques Used
Tools
* Microsoft Excel
* Power Query
* PivotTables & PivotCharts
* Slicers

Techniques
* Data cleaning using Power Query (removing blanks to create Table1_1)
* Formatting and standardizing dataset columns
* Building KPIs (Total Revenue, Total Transactions, AOV)
* Creating sales trend charts (Yearly & Monthly)
* Identifying Top 5 Categories
* Dashboard layout design using a consistent color palette

### Dataset Overview
1. Description
   The dataset contains retail sales transactions from a store serving both online and walk-in customers. Each record represents a single transaction and includes details about the product purchased, its category, price, quantity, total spent, payment method, and transaction date. This dataset provides a complete view of sales activities and customer behavior.
   
2. Size
* Rows: 12,575
* Columns: 11

3. Columns
   
| Column Name	    | Description|
|------------------|------------|
| Transaction ID   |	Unique identifier for each transaction|
| Customer ID	    | Unique identifier for each customer |
| Category	       | Product category (e.g., Beverages, Food) |
| Item	          | Specific item purchased                 |
| Price Per Unit   | Price of one unit of the item          |
| Quantity	       | Number of units purchased           |
| Total Spent	    | Total amount spent (Price × Quantity)   |
| Payment Method   | Mode of payment (e.g., Cash, Credit Card) |
| Location	       | Online or Walk-in purchase     |
| Transaction Date |	Date of the transaction  |
| Discount Applied |	Whether a discount was applied (True/False) |

4. Sample Preview
   
| Transaction ID |	Customer ID	| Category	| Item	| Price Per Unit | Quantity	| Total Spent	| Payment Method	| Location	| Transaction Date |	Discount Applied |
|----------------|---------------|-----------|--------|----------------|------------|--------------|-----------------|-----------|------------------|-----------------|
| TXN_6867343	  | CUST_09	      | Patisserie|	Item_10_PAT | 	18.5	| 10	| 185	| Digital Wallet | 	Online	| ########	| TRUE |
| TXN_3731986	  | CUST_22	      | Milk Products |	Item_17_MILK	| 29	| 9	| 261 |	Digital Wallet | Online	| ########	| TRUE |
| TXN_9303719	 | CUST_02	| Butchers	| Item_12_BUT	| 21.5	| 2	| 43	| Credit Card	| Online	 | ########	| FALSE |

5. Missing Values
   
Some columns contain missing data that will be handled during cleaning:

* Item – 1,213 missing
* Price Per Unit – 609 missing
* Quantity – 604 missing
* Total Spent – 604 missing
* Discount Applied – 4,199 missing

### Data cleaning

* Imported the raw sales dataset into Excel for initial review.
* Removed rows with missing Price Per Unit and Quantity, since these prevented accurate calculation of Total Spent.
* Computed Total Spent using Price × Quantity after validating required fields.
* Extracted Month and Year from the Transaction Date to support trend and seasonal analysis.
* Loaded the dataset into Power Query for deeper cleaning.
* Filtered out blank Item values only for the Top Items analysis — since blanks distort item-level ranking.
* Did not filter blanks for Top Categories, because blank items do not change how categories aggregate.
* Loaded the cleaned dataset into Excel as Table1_1 for use in all pivot tables and dashboard visuals.
* Kept the original dataset (Table1) only for KPI totals where blank-item transactions still contribute to overall revenue.

### Exploratory Data Analysis

The Exploratory Data Analysis focused on understanding sales patterns, category performance, item trends, and the structure of missing data within the dataset. After cleaning, two versions of the dataset were used to ensure insight accuracy:

* Table1: Full dataset (including blanks) — used for KPIs and total sales calculations
* Table1_1: Cleaned dataset (blanks in Price, Quantity, Total Spent, and Item removed where necessary) — used for category and item-level analysis

### 1. Sales Trends Over Time

Using extracted Month and Year columns, a time-series view was generated to understand overall performance trends.

Findings:
* Sales increased steadily from 2022 → 2024, indicating consistent business growth.
* A decline in 2025 occurs due to incomplete-year data.
* Monthly analysis helped reveal fluctuations and potential seasonality.

### 2. Category Performance

Category-level insights were generated using Table1 to ensure accuracy.

Key observations:
* Butchers, Electronics, and Food emerged as top-performing categories.
* Categories with missing items were excluded deliberately to avoid skewed results.
* These findings highlight where revenue is concentrated.

### 3. Item-Level Insights

Item performance was analyzed only from clean records to avoid incorrect assumptions.

Key notes:
* Rows with missing Item values were excluded for ranking visuals.
* A Top Items chart was created using only complete data.
* Some blanks could not be reliably inferred because different items shared similar price points.
This ensured all item-level insights remained valid

### 4. Discounts Overview

The Discount Applied field contained many blanks, which were cleaned by replacing empty values with FALSE.

Findings:
* The majority of purchases were not discounted.
* Discount values were used only to understand distribution, not to compare spending behavior.

### 5. Missing Data Patterns

Significant missing values were identified across:
* Item
* Price Per Unit
* Quantity
* Total Spent
* Discount Applied

Actions taken:
* Completely unusable rows (missing both Price per Unit & Quantity) were removed as they were analytically unusable.
* Blanks in Item were filtered out only in Table1_1.
* Discount blanks were set to FALSE for consistency.
This produced a cleaner dataset suitable for accurate analysis and visualization.

### 6. Dual-Dataset Strategy

Two structured datasets were intentionally maintained to ensure clean analysis without compromising KPI accuracy:

Table1 (Full Dataset)

Used for all high-level metrics and visuals where blanks must be included for correct totals:

* Total Revenue
* Transaction Count
* Average Order Value (AOV)
* PivotTables for:
   * Sales by Payment Method
   * Sales Performance Over Time (Year & Month)
   * Top Categories
This ensured that KPIs reflect the complete business activity, even when some fields had missing item-level details.

Table1_1 (Cleaned Dataset)

Used exclusively for insights requiring complete item information, specifically:

* Top Items Analysis

Blank or incomplete items were removed so that the ranking of top-performing items would be reliable and not influenced by missing or ambiguous values.

Why This Approach Was Necessary

Because the dataset contained missing values in key fields (Item, Price, Quantity, Total Spent), separating the data ensured:
* KPIs and time-based trends remained accurate.
* Item-level insights remained clean and trustworthy.
* No visual or metric was distorted by incomplete records.
