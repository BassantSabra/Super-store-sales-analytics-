
# Super Store Dashboard

![Screenshot 2025-01-30 041535](https://github.com/user-attachments/assets/172da686-c5c0-4cf4-ac5b-4d7947250454)

## Overview
This Power BI project follows a **star schema** structure, designed for efficient analysis of sales, profit, and returns data. The model consists of a central fact table (`fact-Orders`) surrounded by multiple dimension tables, enabling powerful filtering and aggregations.

## Data Model Structure

### Fact Table
#### `fact-Orders`
- **Purpose**: Stores sales transaction data.
- **Columns**:
  - `Customer ID` (FK) → Links to `dim-customer`.
  - `Order Date` (FK) → Links to `dim-date`.
  - `Order ID` → Unique identifier for each order.
  - `Product ID` (FK) → Links to `dim-products`.
  - `Category`, `City`, `Country/Region`, `Postal Code`
  - `Discount` → Discount applied to the order.
- **Relationships**:
  - One-to-Many with `dim-products` (Product ID).
  - One-to-Many with `dim-date` (Order Date).
  - One-to-Many with `dim-customer` (Customer ID).

---

### Dimension Tables
#### `dim-products`
- **Purpose**: Stores product-related information.
- **Columns**:
  - `Product ID` (PK) → Links to `fact-Orders`.
  - `Category`, `Product Name`, `Sub-Category`.
- **Relationships**:
  - One-to-Many with `fact-Orders` (Product ID).

#### `dim-customer`
- **Purpose**: Stores customer-related data.
- **Columns**:
  - `Customer ID` (PK) → Links to `fact-Orders`.
  - `Customer Name`.
- **Relationships**:
  - One-to-Many with `fact-Orders` (Customer ID).

#### `dim-date`
- **Purpose**: A standard date table for time-based analysis.
- **Columns**:
  - `Date` (PK) → Links to `fact-Orders`.
- **Relationships**:
  - One-to-Many with `fact-Orders` (Order Date).

#### `dim-Returns`
- **Purpose**: Tracks returned orders.
- **Columns**:
  - `Order ID` (PK) → Links to `fact-Orders`.
- **Relationships**:
  - Many to-Many with `fact-Orders` (Order ID).

---

## Key Measures (DAX Calculations)
### `key measures`
#### **Key Metrics:**
- `% Returned Orders` → Percentage of returned orders.
- `Profit` → Sales profit calculation.
- `Total Sales` → Total revenue.

#### **Previous Year (PY) Metrics:**
- `% Return Percentage PY` → Return percentage from last year.
- `Profit PY` → Last year's profit.
- `Sales PY` → Last year's sales.

#### **Variance (vs PY) Metrics:**
- `vs PY - % Return Orders` → Change in return orders YoY.
- `vs PY - Profit` → Change in profit YoY.
- `vs PY - Sales` → Change in sales YoY.

---

![Screenshot 2025-01-30 033349](https://github.com/user-attachments/assets/d27f3698-e720-4d30-af29-8d4b4a2c0914)


## Key Performance Indicators (KPIs)
- **Profit:**
  - CY: $286.40K, PY: $192.96K, YoY Growth: 48.42%
  - Strong financial performance.
- **Total Sales:**
  - CY: $2.30M, PY: $1.56M, YoY Growth: 46.88%
  - Reflects increased revenue generation.
- **% Returned Orders:**
  - CY: 5.91%, PY: 8.91%, YoY Change: -3.00%
  - Improved customer satisfaction or better product quality.

---

## Sales Trends Over Time
- **Sales vs. Previous Year Over Time:**
  - Data from Jan 2020 - Jul 2023.
  - Sales consistently higher in CY vs PY, with an upward trend.
  - Accelerated growth from 2022 onwards.

---

## Sales by Segment
- **Total Sales by Segment:**
  - Consumer: 50.56%
  - Corporate: 30.74%
  - Home Office: 18.70%
  - Consumer segment dominates sales.

---

## Profit by State
- **Regional Performance:**
  - New York and California leading in profits.
  - Identifying successful strategies for replication.

---

## Profit by Product Category
- **Profitability by Category:**
  - Furniture: ($17.73K)
  - Office Supplies: $18.95K
  - Technology: $55.62K
  - Technology is the most profitable.
  - Loss in Furniture requires corrective actions.

---

## Filters and Drill-Downs
- **Filters Available:**
  - Region, Customer Name, Date Range (1/1/2020 - 12/1/2023)
  - Enables deep-dive analysis.

---

## Additional Insights
- **Product Performance:**
  - Categories analyzed: Chairs, Tables, Accessories, Copiers, etc.
  - High-performing vs. underperforming products.

---

## Actionable Recommendations
 **you can check the finial report**
   


