# NumPy & Pandas Basics

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Bharat-KR25/Numpy-and-pandas-projects/blob/main/assn_1.ipynb)
![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?logo=numpy&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?logo=pandas&logoColor=white)

**Notebook:** `assn_1.ipynb`

An introductory assignment in three parts: NumPy arrays, Pandas Series and Pandas DataFrames. Each part uses a small, hand-made dataset so the output is easy to check.

## Contents

| Part | Data | Focus |
|------|------|-------|
| A. NumPy arrays | two weeks of daily temperatures | creating, inspecting, slicing and transforming 1D and 2D arrays |
| B. Pandas Series | marks of the top 5 ranks | `.iloc`, `.loc`, boolean filtering, updating and dropping |
| C. Pandas DataFrame | 10 sales transactions | exploration, filtering, grouping and modification |

## Part A: NumPy Arrays

| Step | Task |
|------|------|
| A1 | Create a 1D array of Week 1 temperatures (`float64`) |
| A2 | Inspect `shape`, `dtype` and `size` (`(7,)`, `float64`, 7) |
| A3 | Convert Celsius to Fahrenheit with vectorized math, then get max (26.1), min (20.8) and mean (23.5) |
| A4 | Slice the first three days, the weekend (last 2) and the middle three days |
| A5 | Build a 2D array (rows = weeks) by adding Week 2 |
| A6 | Inspect the 2D array (shape `(2, 7)`, size 14) and slice rows, weekends and both weekends together |

```python
temperatures_w1_fahrenheit = (temperatures_w1 * 9 / 5) + 32
both_weekends = temperatures[:, -2:]
```

## Part B: Pandas Series

A Series of marks `[95, 92, 89, 85, 80]` indexed `Rank1` to `Rank5`.

| Step | Task |
|------|------|
| B1 | Create the Series with a custom index |
| B2 | Select by position (`.iloc`), by label (`.loc`) and by condition (`marks > 90`) |
| B3 | Update `Rank1` to 100, drop `Rank5`, and compute CGPA as `marks / 10` |

## Part C: Pandas DataFrame

A `transactions` table with `TransactionID`, `ProductCategory`, `Region` and `Amount` for 10 sales.

**C2. Exploration**

- `head()`, `tail()`, `shape`, `columns`, `dtypes`, `info()`
- Column selection and `iloc` for the last three columns
- Filtering: `Region == 'North'` and `Amount > 200`
- `value_counts()` and `unique()`
- `groupby('Region')['Amount'].mean()`: East 375.0, North 287.5, South 250.0, West 190.0

**C3. Manipulation**

1. Update the amount for `TransactionID` 102 to 165
2. Add a `Discount` column (10% of `Amount`)
3. Remove the row for `TransactionID` 109 and reset the index
4. Drop the `Discount` column

## Concepts Practiced

- Vectorized array arithmetic and aggregation
- Positive and negative slicing on 1D and 2D arrays
- Label-based (`.loc`) vs position-based (`.iloc`) indexing
- Boolean masks with `&` for combined conditions
- `groupby`, `value_counts` and column creation/deletion

## How to Run

```bash
pip install numpy pandas jupyter
jupyter notebook assn_1.ipynb
```

Run all cells in order. No data files are needed, since all data is created inside the notebook.
