# Data Cleaning & Exploratory Data Analysis (EDA)
### DecodeLabs Internship – Project 1

## Overview

This project analyzes an e-commerce orders dataset in two stages:

1. **Data Cleaning & Preparation** – handling missing values, verifying data types, checking duplicates, and validating calculated fields.
2. **Exploratory Data Analysis (EDA)** – statistical summarization, distribution analysis, outlier detection, and correlation analysis to uncover patterns and trends in the cleaned data.

## Dataset

**File:** `Cleaned_Orders_Dataset.csv`
**Records:** 1200 orders
**Columns:**

| Column | Description |
|---|---|
| OrderID | Unique identifier for each order |
| Date | Order date |
| CustomerID | Unique identifier for each customer |
| Product | Product purchased (Monitor, Phone, Tablet, Chair, Printer, etc.) |
| Quantity | Number of units ordered |
| UnitPrice | Price per unit |
| ShippingAddress | Delivery address |
| PaymentMethod | Method used for payment |
| OrderStatus | Current status of the order (Shipped, Delivered, Cancelled, Returned) |
| TrackingNumber | Shipment tracking ID |
| ItemsInCart | Number of items in the cart at checkout |
| CouponCode | Coupon applied, if any (missing values filled as "No Coupon") |
| ReferralSource | Channel through which the customer arrived |
| TotalPrice | Final order value |

## Project Structure

```
├── data.csv                       # Raw dataset (input to cleaning stage)
├── Cleaned_Orders_Dataset.csv     # Cleaned dataset (output of cleaning stage)
├── EDA_Orders_Dataset.py          # EDA script (this project)
├── monthly_sales_trend.png        # Generated chart
├── distributions.png              # Generated chart
├── boxplots.png                   # Generated chart
├── correlation_heatmap.png        # Generated chart
└── README.md
```

## Requirements

```
pandas
numpy
matplotlib
seaborn
scipy
```

Install with:
```
pip install pandas numpy matplotlib seaborn scipy
```

## How to Run

1. Place `Cleaned_Orders_Dataset.csv` in the same directory as `EDA_Orders_Dataset.py`.
2. Run the script:
```
python EDA_Orders_Dataset.py
```
3. All statistics print to the console; charts are saved as PNG files in the working directory.

## Methodology

### Stage 1: Data Cleaning
- Loaded and inspected dataset structure (shape, types, summary statistics).
- Identified missing values in `CouponCode` (25.75%) and filled them with "No Coupon".
- Verified no duplicate rows or duplicate OrderIDs.
- Converted `Date` to datetime format and confirmed no invalid dates.
- Cross-checked `TotalPrice` against `Quantity × UnitPrice` to confirm data integrity.

### Stage 2: Exploratory Data Analysis
- **Descriptive statistics**: mean, median, mode, standard deviation, min/max for all numeric fields.
- **Categorical distribution**: frequency counts for Product, PaymentMethod, OrderStatus, ReferralSource, and CouponCode.
- **Trend analysis**: monthly aggregation of total sales to identify growth or seasonal patterns.
- **Distribution shape**: skewness and kurtosis calculated for each numeric column, visualized through histograms.
- **Outlier detection**: performed using both the IQR method (quartile-based, robust to skewed data) and the Z-score method (mean/std-based, assumes near-normal distribution), for cross-validation.
- **Boxplots**: visual confirmation of outliers and spread across numeric fields.
- **Correlation analysis**: Pearson correlation matrix and heatmap to examine relationships between numeric variables (correlation only — not evidence of causation).
- **Group-wise summaries**: average and median order value by Product and by OrderStatus.

## Outputs

| File | Description |
|---|---|
| monthly_sales_trend.png | Line chart of total sales by month |
| distributions.png | Histograms of Quantity, UnitPrice, ItemsInCart, TotalPrice |
| boxplots.png | Boxplots for outlier inspection |
| correlation_heatmap.png | Correlation matrix heatmap for numeric fields |

## Key Skills Applied

Data analysis, descriptive statistics, distribution analysis, outlier detection (IQR and Z-score), correlation analysis, analytical thinking.

## Author

Shanum Shahzad — BS Computer Science, University of South Asia
Data Analytics Intern, DecodeLabs
