# Diwali Sales Analysis

Exploratory data analysis of Diwali sales data using Python (pandas, matplotlib).

> 🚧 Work in progress. Updated step by step.

## Business Questions

1. **Product:** Which Product_Category generates the most revenue, and what share of total revenue does each category contribute?
2. **Location:** Which States and Zones generate the highest and lowest revenue?
3. **Customer segments:** Which segment (Gender + Age Group + Marital_Status) spends the most, and which spends the least?
4. **Customer concentration:** What percentage of total revenue comes from the top 10% of customers?
5. **Recommendation:** Which categories, States and segments should receive more marketing budget, and why?

## Dataset

Source: [Diwali Sales Dataset on Kaggle](https://www.kaggle.com/datasets/bharathid8/diwali-sales-dataset) (by bharathid8).

- **Rows:** 11,251
- **Columns:** 15
- **File encoding:** not UTF-8, load with `encoding="latin-1"`

### Columns (raw file)

| Column | Description |
|---|---|
| User_ID | Customer identifier |
| Cust_name | Customer name |
| Product_ID | Product identifier |
| Gender | Customer gender |
| Age Group | Age bracket |
| Age | Customer age |
| Marital_Status | 0/1 flag |
| State | Customer state |
| Zone | Region |
| Occupation | Customer occupation |
| Product_Category | Category of the product |
| Orders | Number of orders |
| Amount | Purchase amount |
| Status | Empty column |
| unnamed1 | Empty column |

## Data Understanding

- `Amount` has **12 missing values**.
- `Status` and `unnamed1` are **completely empty**.
- There are **8 fully duplicated rows**.
- 11,251 rows but only 3,755 unique `User_ID`s, so customers appear in multiple rows (repeat purchases).
- `Age` goes up to 92, to be checked against `Age Group` before deciding.
- Some columns need to be renamed.
- Some columns have incorrect data types.

## Project Structure

```
data/
  raw/        original dataset (never edited)
  cleaned/    cleaned dataset
notebooks/
  01_data_understanding.ipynb
  02_data_cleaning.ipynb
  03_eda_and_visualization.ipynb
images/
```

## Cleaning Steps

Cleaning is done in `notebooks/02_data_cleaning.ipynb` on a copy of the raw data (the raw file stays untouched).

- [x] Dropped the empty columns `Status` and `unnamed1` (13 columns remain)
- [x] Renamed `Cust_name` to `Customer_Name` and `Age Group` to `Age_Group`
- [ ] Remove rows with missing `Amount`
- [ ] Fix data types (`Amount`, `Age_Group`)
- [ ] Decide what to do with duplicate rows
- [ ] Check unusual characters in `State`
- [ ] Check `Age` against `Age_Group`
- [ ] Save cleaned dataset to `data/cleaned/`

## Key Findings

*To be added after the analysis.*

## Limitations

- The dataset has no date column, so time-based trends cannot be analyzed.
- Data covers the Diwali period only, so findings should not be generalized to the whole year.
