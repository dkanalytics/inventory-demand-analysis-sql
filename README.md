# Inventory Demand Analysis SQL

SQL analysis of inventory, orders, and stock shortfalls to find which products sell best, and whether demand is driven by low prices or customer loyalty.



## About

[Dataset name] is a [simulated / public] dataset for a [type of business, e.g. wholesale distributor] selling products across [categories/regions]. It contains customers, products, orders, and order line items, along with stock levels and reorder levels.

## The Brief

Which products sell best, where does the business run short of stock, and is demand driven by low prices or by repeat customers?

### To answer this, the project:

1) Ranks products by units sold and revenue
2) Identifies stock shortfalls (stock on hand vs. reorder level, and demand vs. availability)
3) Tests whether top sellers are priced below their category average
4) Tests whether top sellers rely on repeat customers
5) Database Choice: PostgreSQL

I used PostgreSQL (managed through DBeaver) for this project.

### Why PostgreSQL:

1) Free and open source: no license cost, and it runs well on a standard personal laptop.
2) Widely used in industry: it appears frequently in data analyst job requirements.
3) Standard SQL: the skills (joins, CTEs, window functions) transfer easily to MySQL, SQL Server, and other databases.
4) Full analytical feature set: strong support for window functions, CTEs, and aggregation, which this analysis relies on.
5) Large community: extensive documentation and learning resources.

I considered SQLite (simpler, but fewer features and less common in industry), MySQL (a solid option, but PostgreSQL is stronger for analytics work), and SQL Server (heavier to install and Windows-focused).

## Dataset
- Source: [link to dataset]
- Size: [number of tables, rows]
- Note: [state clearly if any data, such as stock levels, was created or modified by me]

Table	Description
customers	Customer ID, name, region
products	Product ID, category, price, cost, stock on hand, reorder level
orders	Order ID, customer ID, order date
order_items	Order ID, product ID, quantity, price paid, discount

## Analysis Approach
- Data cleaning and validation: checked for duplicates, nulls, inconsistent values, and incorrect data types.
- Exploration: basic counts, date ranges, and distributions.
- Best sellers: ranked products by units sold and revenue, overall and within each category.
- Stock shortfall: compared stock on hand with reorder levels and with demand.
- Price effect: compared each product's average selling price and discount level with its category average.
- Loyalty effect: calculated the share of each product's units bought by repeat customers (customers with 2 or more orders).

## Key Findings

Fill this in after running the analysis. Include real numbers.

Best sellers: [top products, units sold, revenue]
Stock shortfall: [number of products below reorder level, most affected categories]
Price vs. demand: [what the data showed, with figures]
Loyalty vs. demand: [what the data showed, with figures]
Conclusion: [what appears to drive demand, and how confident you are]

## Recommendations
[Action based on the findings, e.g. restock these products first]
[Action based on the findings, e.g. review pricing on these items]

## Limitations
The analysis shows association, not proof of cause. A product may sell well because it is essential, not because it is cheap.
[Dataset limitations, e.g. small sample, limited time period, simulated data]

## Skills Demonstrated
- Database setup and schema design in PostgreSQL
- Data cleaning and validation in SQL
- Multi-table JOINs
- Aggregation with GROUP BY and HAVING
- CASE statements for segmentation
- Common Table Expressions (CTEs) and subqueries
- Window functions (RANK, running totals)
- Turning query results into business insights and recommendations

## Tools
PostgreSQL
DBeaver

[Optional: Excel / Power BI for visualising results]
How to Run
Install PostgreSQL and DBeaver.
Create a new database, e.g. inventory_analysis.
Run schema.sql to create the tables.
Import the CSV files from the data/ folder.
Run the scripts in queries/ in numerical order.
