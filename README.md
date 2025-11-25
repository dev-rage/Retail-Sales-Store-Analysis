# Retail-Sales-Store-Analysis | Revenue, Trends and Insights
Excel Project | Retail Sales Data | From Raw Data to Business Insights

## Table Of Contents
* [Project Overview](Project-Overview)
* [Tools & Techniques Used](Tools--Techniques)
* [Dataset Overview](Dataset-Overview)
* [Data Cleaning Process](Data-Cleaning-Process)
* [Exploratory Data Analysis](Exploratory-Data-Analysis)
* [Excel Dashboard](Excel-Dashboard)
* [Recommendations](Recommendations)

### Project Overview
This project explores and analyzes sales data from a retail store to uncover key business insights. The main goal is to understand sales performance trends, identify top-performing products, and create a visually appealing Excel dashboard that summarizes these insights for decision-making.

Using Microsoft Excel, the dataset is cleaned and prepared to ensure accuracy and consistency. Key analyses include exploring total sales over time, comparing product categories, and highlighting the highest revenue-generating products. The final dashboard provides an interactive view of sales trends, product performance, and profitability metrics, enabling stakeholders to make data-driven business decisions.

This project demonstrates my ability to clean, analyze, and visualize real-world sales data — showcasing practical skills in Excel functions, data visualization, and dashboard creation relevant to business analytics.

### Tools & Techniques
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

### Data Cleaning Process

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

### Excel Dashboard
The Excel dashboard includes the following visuals.
* Sales performance over Time (Year & Month)
* Top 5 Categories
* Top 7 Items
* Sales Performance: Discount vs No Discount
* Sales by Payment Method

<img width="1112" height="427" alt="Retail store dashboard" src="https://github.com/user-attachments/assets/368148c9-b812-4a47-865d-236d90ff5371" />

### Key Insights
1. Overall Sales Performance
* Sales increased steadily from 2022 to 2024, reflecting strong year-over-year business growth.
* A drop in 2025 is visible because the dataset contains partial-year data, not an actual decline.
* Monthly sales patterns show fluctuations and potential seasonality, visible through the sales-by-month chart.

2. Customer Payment Behavior
* Credit Card and Cash accounted for the majority of total revenue.
* Digital Wallet usage was minimal, indicating customers prefer more traditional payment channels.
* This suggests opportunities to explore or promote digital payment adoption.

3. Category Performance

* The Top Categories visualization shows clear dominance from:
   * Butchers
   * Electronics
   * Beverages
* These categories consistently contribute the highest revenue.
* Lower-performing categories present potential areas for strategic improvement or reassessment.

4. Item-Level Insights (Cleaned Dataset Only)
* After removing rows with missing Item names, the Top Items chart accurately highlights the most in-demand products.
* Some missing items had identical price values as known items, making them impossible to classify reliably—therefore excluded.
* This ensured item-level insights were accurate and not influenced by ambiguous data.

5. Discounts Behavior
* Most transactions had no discounts applied.
* Discounted sales formed only a small portion of total revenue.
* The store relies primarily on regular-priced sales rather than promotional strategies.

6. Transaction Activity
* KPIs such as Total Revenue, Transaction Count, and Average Order Value (AOV) show stable business performance.
* AOV indicates customers typically make purchases of moderate value per visit.
* KPI metrics were calculated using the full dataset to maintain accuracy.

7. Data Quality & Dual-Dataset Approach
* Missing values in Item, Price, Quantity, and Total Spent required a dual-dataset strategy:
   * Table1 (full dataset): used for KPIs, totals, and time-based analysis.
   * Table1_1 (clean dataset): used for Top Items to ensure item-level accuracy.
* This approach ensured insights remained reliable and not skewed by incomplete data.

### Recommendations
Based on the insights gathered from the sales dashboard, the following actions are recommended to improve business performance, optimize product strategy, and strengthen revenue outcomes:
1. Strengthen High-Performing Categories
Since Butchers, Electronics, and Food consistently contribute the highest revenue:
* Increase inventory availability for these categories.
* Allocate more shelf space and marketing efforts toward them.
* Consider bundling strategies to increase average order value among top categories.

2. Address Low-Performing Categories
Categories contributing minimal revenue should be:
* Reviewed for pricing issues, supply inconsistencies, or low customer interest.
* Considered for redesign, promotional visibility, or potential discontinuation.
This helps optimize operational focus and reduce inventory waste.

3. Improve Digital Wallet Adoption
Although Digital Wallet payments exist, their usage is significantly low:
* Introduce incentives (e.g., small discounts or loyalty points) for digital payments.
* Promote digital payment options more clearly in-store and online.
* Train staff to encourage customers to try alternative payment methods.
This diversification increases payment flexibility and customer convenience.

4. Monitor Seasonal Sales Patterns
Monthly sales fluctuations indicate possible seasonality:
* Identify high-demand months and prepare stock/inventory accordingly.
* Introduce promotions during historically low-sales months.
* Consider targeted campaigns around peak seasons to maximize revenue.

5. Improve Data Capture for Items & Discounts
Missing data significantly impacted item-level analysis. To prevent this:
* Ensure all items are correctly recorded at the point of sale.
* Require mandatory fields for Price, Quantity, and Item.
* Record discounts consistently (no blanks), even when no discount is applied.
Better data quality = more accurate insights.

6. Expand Discount Strategy (If Relevant)
Since most transactions did not include discounts:
* Analyze price sensitivity with controlled discount campaigns.
* Test whether small targeted discounts increase volume without harming margins.
* Track discount effectiveness over time before scaling.

7. Continue Monitoring KPIs
Key performance indicators such as Total Revenue, AOV, and Transaction Count should be:
* Reviewed monthly to identify emerging patterns.
* Compared year-over-year to track the effectiveness of changes.
* Combined with inventory data to optimize stock management.

8. Enhance Item-Level Promotion
* Insights from the Top Items chart suggest clear high-demand products:
* Prioritize these items in marketing banners, homepage highlights, and in-store placements.
* Use them as anchor products during promotional events to draw more customers

Dataset Source

[Download Here](https://www.kaggle.com/datasets/ahmedmohamed2003/retail-store-sales-dirty-for-data-cleaning)
