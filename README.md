# NumPy & Pandas Projects

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?logo=numpy&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?logo=pandas&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557c)
![Seaborn](https://img.shields.io/badge/Seaborn-4c72b0)
![Plotly](https://img.shields.io/badge/Plotly-3F4F75?logo=plotly&logoColor=white)

Three Jupyter notebooks that take me from NumPy and Pandas fundamentals to a full data analysis project: data cleaning, wrangling, statistics and visualization.

## Projects

| # | Project | What it covers | Open | 
|---|---------|----------------|------|
| 1 | **NumPy & Pandas Basics** | arrays, Series, DataFrames, indexing, filtering, grouping | [![Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Bharat-KR25/Numpy-and-pandas-projects/blob/main/assn_1.ipynb) |
| 2 | **NYC Taxi Trips** | missing-value handling and 10 visualizations on the Seaborn `taxis` dataset | [![Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Bharat-KR25/Numpy-and-pandas-projects/blob/main/assn2.ipynb) | 
| 3 | **Social Media Engagement Analysis** | cleaning, feature engineering, statistics and 16 visualizations on 5,000 posts | [![Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Bharat-KR25/Numpy-and-pandas-projects/blob/main/PANDAS__FINAL_MODULE_AS.ipynb) | 

## Learning Path

1. **Basics (`assn_1.ipynb`):** create and slice NumPy arrays, work with Series and DataFrames, and learn `.loc` vs `.iloc`.
2. **Cleaning and plotting (`assn2.ipynb`):** deal with missing values in a real dataset and visualize it with Matplotlib and Seaborn.
3. **Full analysis (`PANDAS__FINAL_MODULE_AS.ipynb`):** the capstone, with a complete workflow from import to written insights.

## Skills Demonstrated

| Area | Details |
|------|---------|
| **NumPy** | array creation, inspection, slicing, vectorized math, `np.log1p` |
| **Pandas** | indexing (`loc`, `iloc`), filtering, `groupby`, `agg`, `merge`, `pd.cut`, datetime handling |
| **Data cleaning** | missing-value imputation, duplicate checks, text standardization, outlier capping |
| **Feature engineering** | derived scores, log transforms, date parts, age bins |
| **Statistics** | mean, median, mode, variance, percentiles, skewness, kurtosis, correlation |
| **Visualization** | Matplotlib, Seaborn and interactive Plotly charts |

## Datasets

| Project | Source |
|---------|--------|
| 1 | Created inside the notebook |
| 2 | Seaborn built-in `taxis` dataset, downloaded with `sns.load_dataset("taxis")` |
| 3 | `social_media_engagement_5000.csv` (included in this repository, read from its GitHub URL) |

Projects 2 and 3 need an internet connection to load their data.

## Getting Started

**Prerequisites:** Python 3.x and Jupyter Notebook, JupyterLab, or VS Code with the Jupyter extension.

```bash
git clone https://github.com/Bharat-KR25/Numpy-and-pandas-projects.git
cd Numpy-and-pandas-projects
pip install numpy pandas matplotlib seaborn plotly jupyter
jupyter notebook
```

Open a notebook and run the cells in order. Or click an **Open in Colab** badge above to run it in the browser with nothing to install.

## Repository Structure

```text
.
├── assn_1.ipynb                       # NumPy & Pandas basics
├── assn2.ipynb                        # NYC taxi cleaning & visualization
├── PANDAS__FINAL_MODULE_AS.ipynb      # Social media engagement analysis
├── social_media_engagement_5000.csv   # Dataset for project 3
├── docs/
│   ├── assn_1.md
│   ├── assn2.md
│   └── pandas_final_module.md
└── README.md
```
