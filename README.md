# Global Electronics Retailer — Sales Analysis in Excel

## Project Overview

This project analyses sales data from a fictional global electronics retailer using Microsoft Excel. The goal was to clean and prepare the data, build relationships between related tables, calculate sales performance metrics, and develop an interactive dashboard for exploring business performance.

## Tools and Techniques

- **Power Query:** Inspected and transformed the source tables, corrected data types, checked missing values and errors, and performed data-quality checks before analysis.
- **Power Pivot and Excel Data Model:** Loaded the tables into the Data Model and established relationships between the Sales table and the Customers, Products, and Stores tables.
- **PivotTables:** Summarised sales quantities, calculated revenue and profit totals, counted distinct orders, and compared performance across products, categories, countries, and time periods.
- **Calculated columns:** Used related product prices and costs to estimate revenue, total cost, and profit for sales line items.
- **PivotCharts, slicers, and timeline:** Built dashboard visualisations and interactive filters for exploring results by customer country, product category, and order date.

## Dataset

The project uses the [Global Electronics Retailer dataset from Maven Analytics](https://mavenanalytics.io/data-playground/global-electronics-retailer).

The workbook contains six tables:

| Table | Purpose |
|---|---|
| Sales | Order dates, delivery dates, product and customer keys, store keys, quantities, and currency codes |
| Products | Product names, categories, unit costs, and unit prices |
| Customers | Customer details and country |
| Stores | Store information and geographic attributes |
| Exchange Rates | Currency exchange-rate records |
| Data Dictionary | Definitions of the dataset fields |

## Data Preparation and Modelling

### Power Query

Power Query was used to inspect and prepare the source tables for analysis. The work included:

- Correcting the interpretation of order dates.
- Setting Quantity to a whole-number data type.
- Checking missing values, errors, and duplicate records.
- Retaining blank delivery dates rather than filling them with assumed values.
- Reviewing quantity values for possible return-related records.

### Power Pivot and Data Model

The tables were loaded into the Excel Data Model. Relationships were established between the Sales table and three dimension tables:

- `Sales[CustomerKey]` → `Customers[CustomerKey]`
- `Sales[ProductKey]` → `Products[ProductKey]`
- `Sales[StoreKey]` → `Stores[StoreKey]`

These relationships enabled sales records to be analysed by customer, product, and store attributes.

### Calculated Metrics

Calculated columns were used to estimate sales performance:

- **Revenue** = Unit Price USD × Quantity
- **Total Cost** = Unit Cost USD × Quantity
- **Profit** = Revenue − Total Cost

These calculations use the listed USD unit prices and costs in the Products table. They are estimates, not verified accounting figures, because the calculations do not independently account for discounts, taxes, shipping, returns, or other adjustments.

## Key Findings

### 1. Top-Selling Products by Quantity

| Product | Quantity Sold |
|---|---:|
| WWI Desktop PC2.33 X2330 Black | 550 |
| WWI Desktop PC1.80 E1800 White | 538 |
| Adventure Works Desktop PC1.60 ED160 Black | 521 |

These were the three highest-volume products identified in the analysis.

### 2. Product Category Performance

The following were the three leading categories by estimated revenue:

| Product Category | Quantity | Estimated Revenue (USD) | Estimated Total Cost (USD) | Estimated Profit (USD) |
|---|---:|---:|---:|---:|
| Computers | 44,151 | $19,301,595.46 | $8,024,147.56 | $11,277,447.90 |
| Home Appliances | 18,401 | $10,795,478.59 | $4,499,139.74 | $6,296,338.85 |
| Cameras and camcorders | 17,609 | $6,520,168.02 | $2,600,367.03 | $3,919,800.99 |

Computers recorded the highest estimated revenue and profit among these categories.

### 3. Order Distribution by Customer Country

Using the Customers table's country field, the highest distinct order counts included:

| Customer Country | Distinct Orders |
|---|---:|
| United States | 14,211 |
| United Kingdom | 3,421 |
| Germany | 2,440 |

The United States had the highest distinct order count among the countries shown.

### 4. Monthly Sales Volume

The monthly trend was analysed using the sum of Quantity rather than revenue.

- **Highest month:** December 2019 — 9,343 units.
- **Lowest month:** April 2017 — 161 units.

Annual quantities increased from 2016 through 2019, followed by a decline in 2020. The 2021 records cover January and February only, so 2021 is an incomplete year and should not be compared directly with full-year totals.

### 5. Customer Order Activity

The highest distinct order counts among the customer records analysed included:

| Customer Key | Distinct Orders |
|---:|---:|
| 723572 | 14 |
| 2080484 | 12 |
| 1349131 | 11 |

This measures order frequency, not customer spending or lifetime value.

## Interactive Executive Dashboard

The dashboard brings key performance indicators and visualisations together in one Excel worksheet.

### KPI Cards

- Total Revenue (USD)
- Total Profit (USD)
- Units Sold
- Distinct Orders

### Charts

- Top-Selling Products by Quantity
- Revenue by Product Category (USD)
- Monthly Sales Trend (Sum of Quantity)
- Order Distribution by Customer Country

### Interactive Filters

The dashboard includes:

- **Country slicer** to filter by customer country.
- **Product Category slicer** to filter by product category.
- **Order Date timeline** to filter by date range.

The workbook was saved, closed, and reopened to check that the dashboard and filters continued to work.

### Dashboard Preview

`![Global Electronics Retailer Executive Dashboard](Executive-dashboard.png)`

## Limitations

- The dataset represents a fictional retailer.
- Revenue, total cost, and profit are estimates based on listed product prices and costs.
- The monthly trend measures quantity, not revenue.
- The 2021 data covers January and February only.
- The negative-quantity check did not identify negative-quantity records; this does not prove that no returns occurred.
- The source dataset's licence should be checked before redistributing the original data within the workbook.

## Project Structure

```text
global-electronics-retail-analysis/
├── README.md
├── completed-workbook.xlsx
└── images/
    └── executive-dashboard.png
```

## Conclusion

This project demonstrates how Excel can be used for data preparation, relational modelling, calculated metrics, business analysis, and interactive dashboard development. Power Query supported data preparation, while Power Pivot and the Excel Data Model enabled related-table analysis. PivotTables, PivotCharts, slicers, and a timeline supported the analysis and presentation of results.

**Tools:** Microsoft Excel · Power Query · Power Pivot · Excel Data Model · PivotTables · PivotCharts · Slicers · Timeline

**Project type:** Data Analytics Portfolio Project
