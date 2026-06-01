# Data Cleaning & Preparation – Project 1

## Data Analytics Internship Program

### Prepared by

**Julian Andres Belmonte Ortiz**

---

## Project Overview

This project was completed as part of the **Data Analytics Internship Program** and focuses on the fundamental process of **Data Cleaning and Preparation**.

Before performing any analysis, visualization, or predictive modeling, it is essential to ensure that the dataset is accurate, complete, and consistent. The objective of this project was to evaluate the quality of the provided dataset and apply appropriate data-cleaning techniques to improve its reliability.

The project involved identifying missing values, validating records, checking for duplicates, reviewing date formats, and verifying numerical consistency using Python and Pandas.

---

## Objectives

The main objectives of this project were:

- Identify missing values within the dataset.
- Handle incomplete records appropriately.
- Detect duplicate rows and duplicate identifiers.
- Validate date formats and ensure consistency.
- Verify numerical calculations using business rules.
- Review categorical fields for formatting and spelling consistency.
- Generate a cleaned dataset ready for future analysis.

---

## Technologies Used

- Python
- Pandas
- Google Colab
- Microsoft Excel

---

## Dataset Information

| Attribute     | Value                       |
| ------------- | --------------------------- |
| Total Records | 1200                        |
| Dataset Type  | Transactional Sales Data    |
| Environment   | Google Colab                |
| Main Task     | Data Cleaning & Preparation |

---

## Data Cleaning Process

### 1. Missing Value Analysis

The dataset was inspected for null or missing values using Pandas.

```python
df.isnull().sum()
```

#### Findings

| Column     | Missing Values |
| ---------- | -------------- |
| CouponCode | 309            |

All other columns contained zero missing values.

#### Action Taken

The missing values in the `CouponCode` column were replaced with:

```python
df["CouponCode"] = df["CouponCode"].fillna("No Coupon")
```

This approach clearly indicates that no coupon was used during the transaction.

---

### 2. Duplicate Record Validation

Duplicate rows and duplicate Order IDs were checked using:

```python
df.duplicated().sum()
df["OrderID"].duplicated().sum()
```

#### Findings

- Duplicate Rows: 0
- Duplicate Order IDs: 0

No duplicate records were found in the dataset.

---

### 3. Date Format Validation

The `Date` column was converted and validated using:

```python
df["Date"] = pd.to_datetime(df["Date"], errors="coerce")
```

#### Findings

- Invalid Dates: 0

The dates were standardized to the following format:

```python
df["Date"] = df["Date"].dt.strftime("%Y-%m-%d")
```

Example:

```text
2025-05-08
```

---

### 4. Numeric Data Validation

A business rule validation was performed to verify:

```text
TotalPrice = Quantity × UnitPrice
```

Validation code:

```python
df["CalculatedTotal"] = (
    df["Quantity"] * df["UnitPrice"]
).round(2)

invalid_prices = (
    df["TotalPrice"].round(2) !=
    df["CalculatedTotal"]
).sum()
```

#### Findings

Initially, discrepancies appeared due to floating-point precision differences. After standardizing values to two decimal places, all records were successfully validated.

Results:

- Price Inconsistencies: 0

---

### 5. Categorical Data Review

The following categorical columns were reviewed:

- PaymentMethod
- OrderStatus
- ReferralSource

Validation was performed using:

```python
df["PaymentMethod"].unique()
df["OrderStatus"].unique()
df["ReferralSource"].unique()
```

#### Findings

No spelling mistakes or inconsistent formatting were detected.

Examples of potential issues that were checked:

```text
Shipped
shipped
SHIPPED
```

All categorical values were already standardized.

---

## Results Summary

| Task                    | Result                    |
| ----------------------- | ------------------------- |
| Missing Values          | 309 found in CouponCode   |
| Missing Values Handling | Replaced with "No Coupon" |
| Duplicate Records       | 0                         |
| Duplicate Order IDs     | 0                         |
| Invalid Dates           | 0                         |
| Price Inconsistencies   | 0                         |
| Final Rows              | 1200                      |

---

## Deliverables

### Cleaned Dataset

```text
Cleaned_Dataset_Project1.xlsx
```

### Data Cleaning Notebook

```text
Project1_DataCleaning.ipynb
```

---

## Conclusion

The dataset was successfully cleaned and validated according to the project requirements.

The primary issue identified was the presence of 309 missing values in the `CouponCode` column, which were appropriately handled. No duplicate records, invalid dates, or actual numerical inconsistencies were found after applying proper validation techniques.

This project demonstrates the importance of data cleaning as the foundation of reliable analytics and highlights how systematic validation processes help ensure data quality before further analysis.

---

### Author

**Julian Andres Belmonte Ortiz**

Data Analytics Intern

2026
