# Melbourne Housing Market Analysis 🏠

An end-to-end data analysis project exploring **34,000+ real property sales** in
Melbourne (2016–2018): cleaning messy real-world data, uncovering what drives house
prices, and building a machine-learning model to predict them.

> Built with Python, pandas, matplotlib and scikit-learn as a portfolio project to
> demonstrate the full data-analyst workflow — from raw data to business insight.

---

## 📌 Overview

| | |
|---|---|
| **Goal** | Understand the drivers of Melbourne house prices and predict sale price from property features |
| **Dataset** | [Melbourne Housing Market](https://www.kaggle.com/datasets/anthonypino/melbourne-housing-market) (Kaggle, by Tony Pino) — scraped from Domain.com.au |
| **Size** | 34,857 records × 21 columns → **27,247 records** after cleaning |
| **Period** | January 2016 – March 2018 |
| **Tools** | Python · pandas · NumPy · matplotlib · scikit-learn |

---

## 🔍 Project Workflow

1. **Data cleaning** — handled missing values (dropped rows missing the target `Price`,
   median-imputed count features, treated impossible zeros as missing), parsed dates,
   and engineered new features (`price_per_room`, `Year`).
2. **Exploratory data analysis (EDA)** — used `groupby` aggregations and correlation
   analysis to answer business questions about location, property type and price drivers.
3. **Data visualisation** — built charts to communicate the findings clearly.
4. **Machine learning** — trained and compared regression models to predict price.

---

## 💡 Key Findings

- **Typical price:** the median sale price was **A$870,000**; the mean (A$1.05M) is
  higher because a tail of luxury sales skews the average — so the median better
  represents a "typical" home.
- **Location is king:** for every **1 km further from the CBD**, price dropped by
  roughly **A$42,000** on average.
- **Most expensive suburb:** Canterbury (median **A$2.3M**), followed by Malvern and
  Middle Park.
- **Property type matters:** Houses (A$1.02M median) sold for nearly **double** the
  price of Units (A$580k).
- **Surprising result:** land size had almost **no correlation** with price (r = 0.02)
  — in a city, location dominates raw land area.
- **Strongest price driver:** number of rooms (each extra room added ~A$213k in the
  linear model).

---

## 🤖 Model Results

Several regression models were trained and compared on held-out test data:

| Model | R² | Mean Absolute Error |
|---|---|---|
| Linear Regression | 0.57 | A$284k |
| K-Nearest Neighbours | 0.67 | A$218k |
| Gradient Boosting | 0.70 | A$217k |
| **Random Forest** | **0.70** | **A$208k** |

The **Random Forest** performed best, explaining ~70% of price variation — a clear
improvement over the linear baseline, showing the value of trying multiple algorithms.

---

## 📁 Project Structure

```
melbourne-housing-analysis/
├── README.md
├── melbourne_housing_analysis.ipynb   # main notebook (cleaning → EDA → viz → model)
├── requirements.txt                   # Python dependencies
└── data/
    └── Melbourne_housing_FULL.csv     # dataset (or download from the Kaggle link above)
```

---

## ▶️ How to Run

1. Clone this repository:
   ```bash
   git clone https://github.com/YOUR_USERNAME/melbourne-housing-analysis.git
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Open the notebook in Jupyter or [Google Colab](https://colab.research.google.com/)
   and run the cells top to bottom.

---

## 🧠 Skills Demonstrated

Data cleaning · handling missing data · feature engineering · exploratory data analysis ·
`groupby` aggregation · correlation analysis · data visualisation · supervised machine
learning (regression) · model evaluation (R², MAE) · model comparison.

---

## 🚀 Possible Next Steps

- Add `BuildingArea` and `YearBuilt` as features (on the subset where they exist)
- Hyperparameter tuning and cross-validation for the Random Forest
- Try gradient-boosting libraries (XGBoost / LightGBM)
- Add a K-Means clustering analysis to segment the market (unsupervised learning)

---

*Dataset credit: Tony Pino, "Melbourne Housing Market", Kaggle. This project is for
educational and portfolio purposes.*
# melbourne-housing-analysis
