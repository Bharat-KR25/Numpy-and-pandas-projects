# NYC Taxi Trips: Cleaning & Visualization

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Bharat-KR25/Numpy-and-pandas-projects/blob/main/assn2.ipynb)
![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?logo=pandas&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-4c72b0)

**Notebook:** `assn2.ipynb`

Handles missing values in the Seaborn **taxis** dataset and explores it with 10 Matplotlib, Pandas and Seaborn visualizations.

## Dataset

Loaded with `sns.load_dataset("taxis")`: **6,433 trips and 14 columns** covering pickup and dropoff times, passengers, distance, fare, tip, tolls, total, payment type and pickup/dropoff zone and borough.

> `load_dataset` downloads the data on first use, so an internet connection is needed.

## Step 1: Load the Data

Loads the dataset and prints its shape, `(6433, 14)`.

## Step 2: Handle Missing Values

| Column | Missing | Strategy |
|--------|---------|----------|
| `payment` | 44 | fill with the mode |
| `dropoff_zone` | 45 | fill with the mode |
| `dropoff_borough` | 45 | fill with the mode |
| `pickup_zone` | 26 | drop the rows (critical column, no reasonable imputation) |
| `pickup_borough` | 26 | drop the rows (critical column, no reasonable imputation) |

Numeric columns would be filled with the median, but none have missing values. The `pickup` and `dropoff` columns are converted to `datetime`.

**Result:** 0 missing values and a final shape of **(6407, 14)**.

## Step 3: Matplotlib / Pandas Plots

| Plot | Shows |
|------|-------|
| Line chart | fare over time |
| Bar chart | total fare by pickup borough |
| Pie chart | share of trips by payment method |
| Histogram | distribution of trip distance (40 bins) |
| Box plot | tip amount by pickup borough |

## Step 4: Seaborn Plots

| Plot | Shows |
|------|-------|
| Count plot | number of trips by pickup borough |
| Scatter plot | distance vs fare, colored by borough |
| Heatmap | correlation between distance, fare, tip, tolls and total |
| Pair plot | `distance`, `fare`, `tip`, `total` for the top 5 pickup zones |
| Violin plot | fare distribution by payment method |

## Concepts Practiced

- Detecting missing values with `isnull().sum()`
- Choosing an imputation strategy by column type and importance
- Converting columns with `pd.to_datetime`
- Plotting with Matplotlib, Pandas `.plot()` and Seaborn
- Reducing clutter by limiting the pair plot to the top 5 zones

## How to Run

```bash
pip install pandas numpy matplotlib seaborn jupyter
jupyter notebook assn2.ipynb
```

Run all cells in order. Each plot appears below the cell that creates it.
