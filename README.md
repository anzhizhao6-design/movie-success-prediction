# Movie Revenue Analysis

A data analysis project investigating how production budget affects box office revenue, with a focus on diminishing returns.

Key Insight: Increasing budget improves revenue, but with diminishing returns—suggesting that optimal budget allocation is more important than simply spending more.
---

##  Problem Statement

In the film industry, production budgets range from low-cost independent films to high-budget blockbusters.
This project investigates:

* Does a higher budget lead to higher box office revenue?
* Is the relationship linear or are there diminishing returns?
* How do genre and audience ratings influence this relationship?

---

## Data Sources

This project uses publicly available datasets:

* TMDB 5000 Movies Dataset (Kaggle)
* Movies Box Office Dataset (2000–2024)（Kaggle)
* IMDb Dataset (for validation)

Raw datasets are not included in this repository due to size constraints.

Detailed dataset links and selection justification are provided inside the notebook.

---

## Methodology

### Data Processing

* Cleaned and merged multiple datasets using movie title and release year
* Handled missing values and inconsistencies
* Converted multi-genre fields into dummy variables

### Feature Engineering

* Created genre indicators
* Included audience rating as a control variable
* Applied log transformation to reduce skewness

### Modeling Approach

* Log-log regression to interpret elasticity
* Multiple model comparison:

  * Model 1: Budget only
  * Model 2: Budget + Rating
  * Model 3: Budget + Rating + Genre
* Quadratic term to test non-linearity

Overall, the analysis combines data cleaning, feature engineering, and regression modeling to isolate the effect of budget on revenue.

---

## Key Results

* **Budget has a positive but diminishing effect on revenue**

  * Elasticity < 1 → increasing budget yields proportionally smaller returns

* **Audience rating significantly improves model performance**

  * Suggests perceived quality influences revenue

* **Genre effects are substantial**

  * Some genres systematically outperform others

* **Non-linear relationship detected**

  * Very low budgets underperform
  * A “sweet spot” exists where spending becomes effective

---

## Insights

* Simply increasing budget does not guarantee success
* Strategic allocation of budget matters more than scale
* Genre and audience perception are critical drivers of performance

This has practical implications for film producers making investment decisions.

---

## Tools & Technologies

* Python (pandas, numpy, matplotlib, seaborn)
* Jupyter Notebook
* Statistical modeling (regression analysis)

---

## Project Structure

```
movie-success-prediction/
│
├── movie-revenue-analysis.ipynb   # Main analysis notebook
├── README.md                     # Project overview
├── .gitignore
└── data/
    ├── raw/                      # Raw datasets (not included)
    └── processed/                # Processed data (optional)
```

---

## How to Run

```bash
pip install -r requirements.txt
jupyter notebook
```

Then open:

```
movie-revenue-analysis.ipynb
```

---

## Author

Anzhi Zhao
NTU Data Science & Artificial Intelligence

---
