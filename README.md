# Movie Revenue Analysis

A data science project investigating how production budget affects box office revenue, with a focus on diminishing marginal returns and the role of audience perception and genre.

---

## Problem Statement

In the film industry, production budgets range from low-cost independent films to high-budget blockbusters. While higher budgets are generally associated with higher revenue, it is unclear whether:

- The relationship between budget and revenue is linear
- Increasing budget always leads to proportional gains
- Other factors (e.g., genre, audience rating) influence this relationship

This project aims to **quantitatively evaluate the impact of production budget on box office revenue**, while controlling for key variables.

---

## Methodology

### Data Sources
This project uses publicly available datasets:

- TMDB 5000 Movie Dataset (metadata, budget, genres)
- Movies Box Office Dataset (2000–2024)
- IMDb Dataset (for validation and ratings)

Datasets are **not included in this repository** due to size and licensing.  
Links to download are provided inside the notebook.

---

### Data Processing

- Merged multiple datasets using **title + release year**
- Cleaned inconsistent entries and removed duplicates
- Converted multi-genre features into **dummy variables**
- Created a final dataset with:
  - Budget
  - Revenue
  - Audience rating
  - Genre indicators

---

### Modeling Approach

- Applied **log-log regression** to:
  - Reduce skewness
  - Enable elasticity interpretation
- Built multiple models for comparison:

| Model | Variables | R² |
|------|----------|----|
| Model 1 | Budget only | ~0.39 |
| Model 2 | + Rating | ~0.46 |
| Model 3 | + Genre dummies | ~0.52 |

- Tested **non-linearity** using a quadratic specification

---

## Key Results (Model-Based Findings)

- **Production budget has a significant positive effect on revenue**
  - Elasticity ≈ 0.60–0.65
  - Indicates **diminishing marginal returns**
  - A 1% increase in budget leads to <1% increase in revenue

- **Model performance improves with control variables**
  - R² increases from ~0.39 → ~0.52
  - Suggests omitted variable bias in simpler models

- **Audience rating is a strong predictor**
  - Reflects perceived quality
  - Significantly improves model explanatory power

- **Genre effects are substantial**
  - Certain genres consistently outperform others
  - Part of the “budget effect” captures genre differences

- **Non-linear relationship detected**
  - Very low-budget films underperform
  - A “threshold effect” (~log budget ≈ 14.4) suggests a minimum effective scale

---

## Business Insights

- Increasing budget alone does not guarantee success
- Returns diminish as budget increases
- Strategic allocation (content quality, genre selection) matters more than scale
- Audience perception plays a critical role in revenue performance
- There exists a **minimum viable budget threshold** for commercial success

These insights are relevant for **film producers and investors** when making budgeting decisions.

---

## 🛠️ Tools & Technologies

- Python (pandas, numpy, matplotlib, seaborn)
- Jupyter Notebook
- Statistical modeling (regression analysis)

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
