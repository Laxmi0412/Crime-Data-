# 🔍 LA Crime Data Analysis

Exploratory data analysis and unsupervised machine learning on the [Los Angeles Crime Dataset](https://data.lacity.org/api/views/2nrs-mtv8/rows.csv?accessType=DOWNLOAD) (~1 million records, 2020–present).

---

## 📁 Dataset Overview

| Field | Details |
|---|---|
| **Source** | LA City Open Data Portal |
| **Records** | ~1,005,062 |
| **Features** | 28 columns |
| **Key Fields** | Crime type, date/time, area, victim demographics, location (lat/lon) |

---

## 🛠️ Methods

### 1. Exploratory Data Analysis (EDA)
- Descriptive statistics (mean, median, std dev) for all numeric features
- Correlation heatmap across numeric columns
- Histograms of numeric feature distributions
- Bar chart of the **Top 10 most frequent crime types**
- Geographic scatter plot of incident locations (sample of 3,000)

### 2. K-Means Clustering
Applied **K-Means** unsupervised clustering on geographic coordinates (`Lat`, `Lon`) to identify spatial crime hotspots across Los Angeles.

- Features standardized with `StandardScaler`
- Optimal `k` selected using the **Elbow Method** (evaluated k = 1–10)
- Final model: **k = 4 clusters**

---

## 📊 Key Visualizations

- Correlation Heatmap
- Numeric Feature Histograms
- Top 10 Crime Types (bar chart)
- Geographic Distribution of Incidents (scatter plot)
- Elbow Curve for K-Means

---

## 🚀 Getting Started

### Prerequisites
```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

### Run the Analysis
```python
import pandas as pd

url = "https://data.lacity.org/api/views/2nrs-mtv8/rows.csv?accessType=DOWNLOAD"
df = pd.read_csv(url)
```

---

## 📦 Dependencies

| Library | Purpose |
|---|---|
| `pandas` | Data loading & manipulation |
| `numpy` | Numerical operations |
| `matplotlib` | Plotting |
| `seaborn` | Statistical visualizations |
| `scikit-learn` | K-Means clustering, StandardScaler |

---

## 📌 Notes

- Victim age of `0` likely indicates missing/unknown values — consider filtering before modeling
- Columns `Crm Cd 2/3/4` have high null rates and were excluded from clustering
- Coordinate outliers (lat/lon = 0) are present and should be filtered for geographic analysis

---

## 📄 License

Data is publicly available via the [LA City Open Data Portal](https://data.lacity.org/).
