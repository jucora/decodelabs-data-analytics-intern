# Project 3: SQL Data Analysis

## Table of Contents

- [1. Introduction](#1-introduction)
- [2. Project Objective](#2-project-objective)
- [3. Data Loading and Exploration](#3-data-loading-and-exploration)
- [4. SQL Database Creation](#4-sql-database-creation)
- [5. SQL Data Analysis](#5-sql-data-analysis)
  - [5.1. Basic SELECT Queries](#51-basic-select-queries)
  - [5.2. WHERE Clause Analysis](#52-where-clause-analysis)
  - [5.3. ORDER BY Analysis](#53-order-by-analysis)
  - [5.4. COUNT Aggregation](#54-count-aggregation)
  - [5.5. SUM Aggregation](#55-sum-aggregation)
  - [5.6. AVG Aggregation](#56-avg-aggregation)
  - [5.7. Advanced GROUP BY Analysis](#57-advanced-group-by-analysis)
- [6. Key Findings](#6-key-findings)
- [7. Conclusion](#7-conclusion)
- [8. Resources](#8-resources)

## 1. Introduction

This project demonstrates SQL data analysis capabilities using a sales dataset. The goal is to extract meaningful business insights by applying fundamental SQL operations and aggregate functions.

## 2. Project Objective

The primary objective is to analyze a sales dataset using SQL queries to understand data distributions, identify patterns, and support data-driven decision-making. Key tasks include filtering, sorting, grouping, and summarizing data using standard SQL commands.

## 3. Data Loading and Exploration

The sales data was loaded from an Excel file (`Cleaned_Dataset_Project1.xlsx`) into a pandas DataFrame. Initial exploration confirmed the dataset contains 1200 rows and 15 columns with no missing values, indicating a clean dataset ready for analysis.

## 4. SQL Database Creation

An in-memory SQLite database was created, and the pandas DataFrame was successfully loaded into a table named `sales_data`. This setup allows for convenient SQL querying directly within the environment.

## 5. SQL Data Analysis

Various SQL queries were executed to explore different aspects of the sales data.

### 5.1. Basic SELECT Queries

- **View All Records**: Displayed the first 10 rows to get a general overview of the data.
- **Select Specific Columns**: Demonstrated how to select specific columns (`OrderID`, `Product`, `Quantity`, `TotalPrice`) for focused analysis.

### 5.2. WHERE Clause Analysis

- **Delivered Orders**: Filtered for orders with `OrderStatus = 'Delivered'`, identifying 231 successful deliveries.
- **High Value Orders**: Identified 180 orders with `TotalPrice > 2000`, highlighting significant revenue contributors.

### 5.3. ORDER BY Analysis

- **Highest Sales**: Ordered transactions by `TotalPrice` in descending order, showing the top 10 sales. The highest single sale was a `Tablet` at 3456.40.
- **Lowest Sales**: Ordered transactions by `TotalPrice` in ascending order, revealing the 10 lowest sales. The lowest was a `Phone` at 11.39.

### 5.4. COUNT Aggregation

- **Total Number of Orders**: Confirmed 1200 total orders in the dataset.
- **Orders by Status**: Grouped orders by `OrderStatus`, showing 'Cancelled' orders as the most frequent (250), followed by 'Returned' (247), 'Pending' (237), 'Shipped' (235), and 'Delivered' (231).

### 5.5. SUM Aggregation

- **Total Revenue**: Calculated the total revenue from all sales, which amounted to 1,264,761.96.
- **Revenue by Product**: Grouped by `Product`, `Chair` was the top revenue-generating product (195,620.11), followed by `Printer` and `Laptop`.

### 5.6. AVG Aggregation

- **Average Order Value**: Determined the overall average order value to be approximately 1053.97.
- **Average Revenue by Product**: Analyzed the average revenue per product, with `Laptop` having the highest average (1110.56) and `Phone` the lowest.

### 5.7. Advanced GROUP BY Analysis

- **Payment Method Performance**: Grouped sales by `PaymentMethod`, revealing that `Credit Card` is the highest revenue generator (263,847.63) and has the highest average order value (1127.55).
- **Referral Source Performance**: Grouped by `ReferralSource`, `Instagram` emerged as the leading source for both revenue (275,285.45) and number of orders (259).

## 6. Key Findings

Based on the SQL analysis, the following key insights were observed:

1.  **Dataset Size**: The dataset comprises 1,200 sales transactions.
2.  **Product Performance**: Revenue generation is concentrated among a few key products, with `Chair`, `Printer`, and `Laptop` being the top performers.
3.  **Payment Method Preferences**: `Credit Card` payments contribute the most to overall revenue and have the highest average transaction value.
4.  **Order Status Distribution**: 'Cancelled' orders are the most frequent, which might warrant further investigation into the reasons for cancellation.
5.  **Referral Source Effectiveness**: `Instagram` is the most effective referral source in terms of both total revenue and the number of orders generated.

## 7. Conclusion

This project successfully utilized SQL to extract critical business insights from a sales dataset. The analysis provided a clear understanding of product performance, customer behavior patterns related to payment methods and referral sources, and order status distributions. These insights can be leveraged for strategic business decisions, such as optimizing marketing campaigns, improving product offerings, or streamlining order processing.

## 8. Resources

- **Original Dataset**: `Cleaned_Dataset_Project1.xlsx`
- **Libraries Used**: `pandas`, `sqlite3`
- **Tools**: Google Colaboratory

### Prepared by

**[Julian Andres Belmonte Ortiz](https://www.linkedin.com/in/julianbel/)**

### Organization

DecodeLabs – Training Program 2026
