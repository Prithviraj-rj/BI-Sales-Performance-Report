# BI-Sales-Performance-Report
An interactive Power BI dashboard analyzing sales performance against budget goals, using data from SQL Server and Excel.
# Power BI Sales Performance Dashboard

## Project Title
**AdventureWorks Sales Performance Dashboard**

## Problem Statement / Business Context
The sales department at AdventureWorks relied on static, manual sales reports, which were inefficient for dynamic analysis and performance tracking. The Sales Manager, Steven, required a transition to a modern business intelligence solution. The key need was to create a visual and interactive dashboard to analyze internet sales performance. The analysis needed to cover sales volume, product performance, customer insights, and performance over time, while also comparing actual sales against established budget goals.

## Objective / Goal
The primary objective was to develop an end-to-end BI solution that empowers the sales team with actionable insights. The goal was to create a dynamic Power BI dashboard that allows stakeholders to:
*   Track key sales KPIs, specifically total revenue against budget.
*   Analyze sales trends over a two-year period.
*   Identify top-performing products and product categories.
*   Pinpoint the most valuable customers and their geographic locations.
*   Provide interactive filtering capabilities by customer, product, and date.
*   Automate the reporting process with daily data refreshes.

## Tools & Technologies Used
*   **Data Source:** Microsoft SQL Server (`AdventureWorksDW2022` Database), Microsoft Excel
*   **Data Extraction & Transformation (ETL):** SQL
*   **Data Modeling & Visualization:** Microsoft Power BI
*   **Data Analysis Language:** DAX (Data Analysis Expressions)

## Data Sources
1.  **SQL Server Database:** The primary data was sourced from the `AdventureWorksDW2022` data warehouse.
    *   `FactInternetSales`: Contains detailed records of all internet sales transactions.
    *   `DimCustomer`: Contains customer dimension data.
    *   `DimProduct`: Contains product dimension data, including categories and subcategories.
    *   `DimDate`: A date dimension table for time-based analysis.
2.  **Excel Spreadsheet:** A file named `SalesBudget.xlsx` containing the monthly sales budget for the year 2021 was used for variance analysis.

## Methodology / Process

1.  **Requirement Gathering:** Analyzed the business requirements provided by the Sales Manager through email and structured user stories to define the project scope and key deliverables.

2.  **Data Extraction (ETL):**
    *   Connected to the `AdventureWorksDW2022` SQL Server database.
    *   Wrote SQL queries to select, cleanse, and transform data from the fact and dimension tables.
    *   Data was filtered to include the last two years of sales to ensure performance and relevance.
    *   Joined related tables (e.g., `DimProduct` with `DimProductSubcategory`) to create a flattened, analysis-ready view.

3.  **Data Modeling:**
    *   Imported the cleansed datasets from SQL Server and the budget data from Excel into Power BI.
    *   Established a **Star Schema** data model in Power BI, creating relationships between the `FactInternetSales` table and the dimension tables (`DimCustomer`, `DimProduct`, `DimDate`). This model is optimized for BI queries and performance.
    *   Created calculated measures using DAX, such as `Total Revenue`, `Total Budget`, and `Revenue vs Budget Variance`.

4.  **Dashboard Development & Visualization:**
    *   Designed a multi-page dashboard with a clean and intuitive user interface.
    *   **Sales Overview Page:**
        *   **KPI Cards:** Displaying total revenue and the variance against budget.
        *   **Line & Clustered Column Chart:** Visualizing monthly sales performance against the budget.
        *   **Doughnut Chart:** Showing the proportion of sales by product category.
        *   **Bar Charts:** Ranking the Top 10 customers and Top 10 products by revenue.
        *   **Map Visual:** Illustrating sales distribution by customer city.
    *   **Customer Details Page:** A drill-down view providing a monthly sales breakdown for each customer.
    *   **Interactivity:** Implemented slicers for Year, Month, Customer, Product Category, and Sub Category to allow for dynamic data exploration.

5.  **Deployment:** Published the final report to the Power BI Service and configured a scheduled daily data refresh to ensure the sales team always has access to the most current data.

## Key Insights & Results
The dashboard provided several immediate and actionable insights:
*   **Overall Performance:** The company achieved a total revenue of **$16.35M**, exceeding the **$15.30M** budget by over **$1.05M**.
*   **Product Dominance:** **Bikes** are the primary revenue driver, accounting for **95.93%** of total sales. This suggests a high dependency on a single category.
*   **Seasonal Trends:** The line chart revealed a strong upward trend in sales during the second half of the year, consistently outperforming the budget in the later months.
*   **Top Performers:** The dashboard clearly identified the top 10 customers and products, enabling the sales team to focus their efforts on high-value accounts and popular items.
*   **Geographic Concentration:** The map visual showed that sales are heavily concentrated in specific regions of North America, Europe, and Australia.

## Dashboard Output

### Sales Overview Dashboard
*This high-level view provides key KPIs and performance summaries at a glance.*
<img width="1378" height="765" alt="image" src="https://github.com/user-attachments/assets/1581e631-8d26-4cae-81a4-b56402905980" />


### Customer Details View
*This page allows for a detailed analysis of individual customer performance over time.*
<img width="1377" height="773" alt="image" src="https://github.com/user-attachments/assets/061670c9-4128-42ad-8cdb-6e9549ec481a" />



## How to Run / Use
To run this project locally, you will need:
*   Power BI Desktop installed.
*   Access to a SQL Server instance with the `AdventureWorksDW2022` sample database. You can download it from [Microsoft's official repository](https://learn.microsoft.com/en-us/sql/samples/adventureworks-install-configure?view=sql-server-ver16&tabs=ssms).

**Steps:**
1.  Clone this GitHub repository.
2.  Download the `.pbix` file (`Sales Dashboard.pbix`).
3.  Place the `SalesBudget.xlsx` file in a local directory.
4.  Open the `.pbix` file in Power BI Desktop.
5.  Go to `Transform data` -> `Data source settings`.
6.  Update the credentials for the SQL Server database to point to your local instance.
7.  Update the path for the `SalesBudget.xlsx` file to its new location on your machine.
8.  Click "Refresh" on the Home ribbon to load the data. You can now interact with the dashboard.
