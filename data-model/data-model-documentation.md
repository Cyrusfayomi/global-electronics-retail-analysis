# Data Model Documentation

## Overview

The Global Electronics Retailer project uses the Excel Data Model to organise and analyse data across multiple related tables.

The model connects the Sales table to the Customers, Products, and Stores tables through their respective key fields. This relational structure supports analysis of sales transactions using customer, product, and store attributes without combining all source tables into one flat table.

## Tables and Their Roles

| Table | Role | Description |
|---|---|---|
| Sales | Fact Table | Contains transaction-level records, dates, keys, quantities, and currency codes. |
| Customers | Dimension Table | Provides customer details and geographic attributes. |
| Products | Dimension Table | Contains product names, categories, unit prices, and unit costs. |
| Stores | Dimension Table | Provides store information and geographic attributes. |
| Exchange Rates | Reference Table | Contains historical currency exchange-rate information. |

## Table Relationships

The following relationships were established in the Excel Data Model:

| Primary Table | Related Table | Relationship Fields |
|---|---|---|
| Sales | Customers | Sales[CustomerKey] → Customers[CustomerKey] |
| Sales | Products | Sales[ProductKey] → Products[ProductKey] |
| Sales | Stores | Sales[StoreKey] → Stores[StoreKey] |

The Customers, Products, and Stores tables serve as lookup tables for analysing the Sales fact table.

## Data Model Diagram

The diagram below illustrates the structure of the model and the relationships between its tables.

![Global Electronics Retailer Data Model](data-model/data-model-relationships.png)

## Reference Table

The Exchange Rates table is retained in the workbook as a reference table containing historical currency exchange-rate information.

It is not connected to the Sales table in the current model.

## Analytical Application

The Data Model supports analysis across multiple business dimensions, including:

- Sales performance by product and product category.
- Order distribution by customer country.
- Store-level sales analysis.
- Customer purchasing activity.
- Revenue, estimated cost, and profit calculations.

Using relationships between the tables allows PivotTables and PivotCharts to analyse information from different tables within a unified model.

## Modelling Considerations

- The Sales table serves as the central fact table.
- Customers, Products, and Stores provide descriptive attributes for sales analysis.
- Exchange Rates is retained as a reference table and is not connected to Sales in the current implementation.
- The model retains the original source tables rather than merging them into a single flat dataset.

## Conclusion

The Excel Data Model provides a structured foundation for analysing the Global Electronics Retailer dataset.

By establishing relationships between transaction records and their corresponding customer, product, and store information, the model supports flexible reporting and interactive business analysis within Microsoft Excel.

**Tools Used:** Microsoft Excel · Power Pivot · Excel Data Model
