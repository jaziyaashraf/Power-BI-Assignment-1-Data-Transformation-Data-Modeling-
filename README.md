
# Power BI Assignment 1 – E-Commerce Sales Analysis

## Project Overview
This project focuses on data transformation, data cleaning, data modeling, and data analysis using Microsoft Power BI. The objective is to prepare e-commerce sales data for meaningful analysis.

## Dataset
The project uses three CSV files:
- List of Orders.csv
- Order Details.csv
- Sales Target.csv

## Tools Used
- Microsoft Power BI
- Power Query Editor
- DAX
- Data Modeling

## 1. Data Transformation
- Imported all three CSV files into Power BI.
- Restricted the List of Orders table to the first 500 rows.
- Changed Order Date to the Date data type.
- Changed Amount and Target to Fixed Decimal Number.
- Converted CustomerName to Proper Case.
- Merged State and City columns to create a Location column in the format City, State.
- Created a custom Profit Margin column using Profit divided by Amount.
- Created a conditional Profit Status column:
  - Profit less than 0: Loss
  - Profit equal to 0: Break-Even
  - Profit greater than 0: Profit

## 2. Merging Data
- Merged List of Orders and Order Details using Order ID.
- Created a combined table named Orders Data.
- Used the matching Order ID values to connect order information with product and sales details.

## 3. Missing Values and Duplicates
- Checked the tables for null and missing values.
- Identified duplicate rows and checked whether they represented actual duplicate records.
- Planned to replace or remove missing values where appropriate.
- Removed only unnecessary duplicate records to avoid losing valid sales data.

## 4. Sorting and Filtering
- Sorted Order Date in descending order to identify recent orders.
- Applied a State filter, such as Tamil Nadu, for regional analysis.
- Used Category and other relevant columns to filter sales information.

## 5. Grouping and Aggregation
- Duplicated the Order Details table for separate aggregation tasks.
- Calculated the count of orders by Order ID.
- Calculated average profit by Category.
- Calculated total Amount by Sub-Category.
- Duplicated the Sales Target table and grouped target amounts by month to calculate total monthly targets.

## 6. Data Modeling
- Created a relationship between List of Orders and Order Details using Order ID.
- Created a relationship between Order Details and Sales Target using Category.
- Checked the relationships in Manage Relationships and ensured the required relationships were active.

## 7. Key Formulas

### Profit Margin
 [Profit] / [quantity]*[Amount]
```
Set the Profit Margin column to Percentage format.

### Profit Status
```DAX
Profit Status =
SWITCH(
    TRUE(),
    'Orders Data'[Profit] < 0, "Loss",
    'Orders Data'[Profit] = 0, "Break-Even",
    'Orders Data'[Profit] > 0, "Profit"
)
```

### Location
```powerquery
[City] & ", " & [State]
```

## Conclusion
This project demonstrates the use of Power BI and Power Query for data cleaning, transformation, merging, grouping, and data modeling. These steps prepare the e-commerce sales dataset for further analysis and reporting.


