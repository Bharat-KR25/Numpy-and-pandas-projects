# Social Media Engagement Analysis

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Bharat-KR25/Numpy-and-pandas-projects/blob/main/PANDAS__FINAL_MODULE_AS.ipynb)
![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?logo=pandas&logoColor=white)
![Plotly](https://img.shields.io/badge/Plotly-3F4F75?logo=plotly&logoColor=white)

**Notebook:** `PANDAS__FINAL_MODULE_AS.ipynb`

A full data analysis workflow on a dataset of **5,000 social media posts**, from import and cleaning through wrangling, statistics, 16 visualizations and written insights.

## Dataset

`social_media_engagement_5000.csv` has **5,000 rows and 19 columns**, with posts dated **2022-01-01 to 2023-12-31**.

| Group | Columns |
|-------|---------|
| User | `user_id`, `age`, `gender`, `country`, `follower_count`, `is_verified` |
| Post | `post_id`, `post_type`, `post_category`, `hashtags`, `posted_at`, `device_type` |
| Engagement | `likes`, `comments`, `shares`, `watch_time_sec`, `impression_count`, `engagement_rate`, `sentiment` |

The notebook reads the CSV directly from this repository's GitHub URL, so an internet connection is needed (or place the CSV next to the notebook and change the path).

## Workflow

### Task 1: Data Import & Setup
Loads the CSV, converts `posted_at` (dd-mm-yyyy text) to `datetime` and `is_verified` to `bool`.

### Task 2: Data Cleaning

| Issue | Finding | Action |
|-------|---------|--------|
| Missing values | 150 rows (3%) each in `age`, `gender`, `likes`, `comments`, `shares`, `sentiment` | median for numeric, mode for categorical |
| Duplicates | 0 duplicate rows; 9 repeated `post_id` values with different content | none removed (rows are distinct posts) |
| Inconsistent text | mixed case and spacing | stripped and lowercased; genders mapped to `Male` / `Female` / `Other` |
| Data types | numeric columns stored as floats after imputation | converted to `int` |
| Unrealistic values | 0 negatives; 464 rows with likes above impressions; 600 with total interactions above impressions; 603 with `engagement_rate` above 1 (max 191.5) | likes, comments and shares clipped to `[0, impressions]`; new `engagement_rate_clean` capped to `[0, 1]` |
| Hashtags | free-text string | `hashtag_count` created (1, 2 or 3 per post) |

### Task 3: Exploration
`head`, `tail`, `info`, `describe`, unique counts and value counts for categorical columns, a correlation matrix, group averages (likes by post type, impressions by country, engagement by category), and `.loc` / `.iloc` selection.

### Task 4: Data Wrangling

New features:

- `total_interactions` = likes + comments + shares
- `engagement_score` = likes × 1 + comments × 2 + shares × 3
- `log_likes`, `log_impressions`, `log_followers` (via `np.log1p`)
- `year`, `month`, `day_of_week`
- `age_group` bins: 13-17, 18-24, 25-34, 35-44, 45-54, 55-64
- Country-level average engagement rate and impressions, merged back into the data

Also lists the top 5 and bottom 5 posts by `engagement_score`, and summary tables by `post_type`, `country` and `sentiment`.

### Task 5: Statistical Analysis
For `likes`, `comments`, `shares`, `watch_time_sec`, `engagement_rate_clean` and `follower_count`: mean, median, mode, standard deviation, variance, min, max, the 25th / 50th / 75th / 90th / 95th percentiles, skewness and kurtosis.

### Task 6: Visualization (16 plots)

| Library | Plots |
|---------|-------|
| **Matplotlib** (6) | likes vs impressions scatter, daily engagement rate with 30-day rolling average, posts per category bar, gender pie, age histogram, engagement by post type box plot |
| **Seaborn** (6) | post type count plot, average likes by category bar plot, follower count by sentiment violin plot, pair plot (500-row sample), correlation heatmap, device type swarm plot (300-row sample) |
| **Plotly** (4, interactive) | monthly engagement line, engagement by country bar, category bubble chart (impressions vs likes, sized by followers), likes vs impressions scatter (1,000-row sample) |

## Selected Findings

Average `engagement_rate_clean` from the notebook output:

| Dimension | Highest | Lowest |
|-----------|---------|--------|
| Post type | text (0.376) | reel (0.360) |
| Category | fitness (0.384) | food (0.357) |
| Country | Australia (0.395) | India (0.340) |
| Age group | 13-17 (0.398) | 55-64 (0.355) |

- Verified accounts had a slightly lower average engagement rate (0.349) than unverified ones (0.374).
- Age and engagement rate are almost uncorrelated (r = -0.024).
- Average impressions are fairly flat across days of the week (about 48,100 to 51,300).

Most differences are small, so treat them as hints and not strong conclusions. About 12% of rows (603 of 5,000) had an engagement rate above 1 and were capped, which affects every rate-based figure.

## Concepts Practiced

- End-to-end cleaning: imputation, standardization, type conversion and outlier capping
- Feature engineering with `np.log1p`, `pd.cut`, date parts and `merge`
- Grouped analysis with `groupby` and `agg`
- Descriptive statistics including skewness and kurtosis
- Static (Matplotlib, Seaborn) and interactive (Plotly) visualization

## How to Run

```bash
pip install pandas numpy matplotlib seaborn plotly jupyter
jupyter notebook PANDAS__FINAL_MODULE_AS.ipynb
```

Run all cells in order. The Plotly charts are interactive: hover, zoom and pan.
