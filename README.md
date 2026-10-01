# Diamonds Price Analysis

A real-world dataset analysis project exploring what drives the price of a diamond, built with Python, Pandas, NumPy, Matplotlib and Seaborn.

## Project Overview

This project analyses the Diamonds dataset (53,940 records) from the [seaborn-data repository](https://github.com/mwaskom/seaborn-data). The goal is to understand how carat, cut, colour, clarity and physical dimensions affect price, and to turn the findings into practical pricing and inventory recommendations for a diamond retailer.

## Dataset

| Variable | Description |
|---|---|
| carat | Weight of the diamond |
| cut | Fair, Good, Very Good, Premium, Ideal |
| color | D (best) to J (worst) |
| clarity | I1 (worst) to IF (best) |
| depth, table | Proportions of the stone (%) |
| x, y, z | Length, width and depth in mm |
| price | Price in US dollars |

## Methodology

1. **Data exploration:** structure, data types, distributions, missing values and duplicates.
2. **Cleaning and preprocessing:**
   - Removed 146 duplicate rows
   - Treated 20 impossible zero dimensions as missing and imputed them with the median of similar-sized stones
   - Removed 4 records with physically impossible measurements
   - Kept genuine high-value outliers
   - Converted cut, colour and clarity to ordered categories
   - Added a `price_per_carat` feature
3. **Exploratory data analysis:** correlations, group comparisons and skewness checks using Pandas and NumPy.
4. **Visualisation:** histograms, box plots, scatter plot, correlation heatmap and line chart.
5. **Statistical modelling:** log-log regression of price on carat, cut, colour and clarity.

## Key Findings

- Price is strongly right-skewed; a log transform makes it close to symmetric.
- Carat is the dominant driver of price (correlation 0.92). A 1% increase in carat is associated with about a 1.9% increase in price.
- Ideal-cut diamonds have the lowest average price (about $3,463) because they are smaller (0.70 ct on average, versus 1.04 ct for Fair cut).
- After controlling for size, better cut, colour and clarity all raise price, with clarity having the largest effect. The model explains about 98% of the variation in log price.
- Depth has almost no relationship with price (correlation -0.01).

## Recommendations

- Price and benchmark inventory by carat band first, then adjust for clarity and colour.
- Avoid judging value from raw average price per grade; use size-adjusted comparisons.
- Add validation at data entry to prevent zero or impossible dimensions.

## Files

- `Diamonds_Price_Analysis.ipynb`: full analysis with code, charts and interpretations
- `Diamonds_Analysis_Report.docx`: written report (if uploaded)

## How to Run

```bash
pip install pandas numpy matplotlib seaborn jupyter
jupyter notebook Diamonds_Price_Analysis.ipynb
```

The notebook loads the dataset directly from a public URL, so no separate download is needed.

## Tools Used

Python, Pandas, NumPy, Matplotlib, Seaborn, Jupyter Notebook
