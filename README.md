# Pizza Sales Data Integration & Analytics Project

## Project Overview
This project demonstrates a complete data pipeline, integrating transactional data from a **MySQL database** with business metadata stored in **Excel**. The final goal was to create a unified Power BI dashboard that provides actionable business insights into sales performance, product popularity, and operational efficiency.

## Data Sources
1. **SQL Database (MySQL):** Contains 48,000+ rows of transactional data across two tables:
   - `orders`: Order ID, Date, and Time.
   - `order_details`: Order ID, Pizza ID, and Quantity.
2. **Excel Workbook:** Contains the product catalog:
   - `pizzas`: Pizza ID, Type, Size, and Price.

## Technical Workflow
- **Data Extraction:** Exported relational data from MySQL as CSV to simulate a production data dump.
- **Data Transformation (Power Query):** - Cleaned and formatted date/time strings.
    - Verified data types for keys (`order_id`, `pizza_id`) to ensure seamless joining.
- **Data Modeling:** - Established a **Star Schema** in Power BI.
    - Created 1-to-Many relationships between the Excel dimension table and the SQL fact tables.
- **DAX Calculations:** Developed custom measures including:
    - `Total Revenue`: `SUMX(order_details, order_details[quantity] * RELATED(pizzas[price]))`
    - `Total Orders`

## Business Insights
- **Revenue Drivers:** Identified which pizza sizes and categories contribute most to the bottom line.
- **Operational Peaks:** Pinpointed the busiest hours of the day to optimize kitchen staffing.
- **Product Analysis:** Used scatter plots to categorize menu items into "High Volume/High Profit" and "Underperformers."

## How to Use
1. Download the `.pbix` file included in this repo.
2. Ensure you have Power BI Desktop installed.
3. The data is embedded in the file, so visuals will load automatically.

## Tools Used
- **SQL:** Data querying and extraction.
- **Excel:** Metadata management.
- **Power BI:** Data modeling, DAX, and Visualization.
