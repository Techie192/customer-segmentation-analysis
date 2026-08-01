<div align="center">

# Customer Segmentation Analysis

**An unsupervised machine learning project that segments mall customers based on spending behavior and income, enabling data-driven marketing strategies.**

![Python](https://img.shields.io/badge/Python-3.10-3776AB?style=flat-square&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=flat-square&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-Numerical%20Computing-013243?style=flat-square&logo=numpy&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-Machine%20Learning-F7931E?style=flat-square&logo=scikitlearn&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-11557C?style=flat-square)
![Seaborn](https://img.shields.io/badge/Seaborn-Visualization-4C72B0?style=flat-square)
![Colab](https://img.shields.io/badge/Google%20Colab-Notebook-F9AB00?style=flat-square&logo=googlecolab&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-informational?style=flat-square)

</div>

---

## Project Overview

This project applies **K-Means Clustering**, an unsupervised machine learning algorithm, to segment mall customers into distinct groups based on their **annual income** and **spending score**. The goal is to identify meaningful customer segments that businesses can use to design targeted marketing campaigns, optimize resource allocation, and improve customer retention strategies.

Unlike supervised learning, clustering requires no labeled outcomes — the algorithm discovers natural groupings directly from the data, making it a practical approach for real-world customer analytics where predefined categories rarely exist.

---

## Objectives

- Analyze customer demographic and behavioral data to identify patterns
- Determine the optimal number of customer segments using the Elbow Method
- Apply K-Means clustering to group customers by income and spending behavior
- Visualize and interpret each cluster to derive actionable business insights
- Present findings in a format suitable for business and marketing decision-making

---

## Dataset Description

**Dataset:** Mall Customers Dataset

| Attribute | Description |
|---|---|
| `CustomerID` | Unique identifier for each customer |
| `Gender` | Customer gender (Male / Female) |
| `Age` | Customer age in years |
| `Annual Income (k$)` | Customer's annual income in thousands of dollars |
| `Spending Score (1–100)` | Score assigned based on customer spending behavior and purchasing patterns |

**Records:** 200 customers
**Source:** Publicly available retail customer dataset, commonly used for clustering and segmentation benchmarks.

---

## Technology Stack

| Category | Tools & Libraries |
|---|---|
| Programming Language | Python |
| Data Manipulation | Pandas, NumPy |
| Data Visualization | Matplotlib, Seaborn |
| Machine Learning | Scikit-learn (KMeans, StandardScaler) |
| Development Environment | Google Colab |

---

## Project Workflow

```
Dataset
   │
   ▼
Data Cleaning
   │
   ▼
Exploratory Data Analysis (EDA)
   │
   ▼
Feature Selection
   │
   ▼
Feature Scaling
   │
   ▼
Elbow Method (Optimal K)
   │
   ▼
K-Means Clustering
   │
   ▼
Customer Segmentation
   │
   ▼
Business Insights
```

Each stage feeds directly into the next, forming a reproducible pipeline from raw data to actionable segments.

---

## Exploratory Data Analysis

Key steps performed during EDA:

- Checked for missing values, duplicates, and data type consistency
- Analyzed distribution of `Age`, `Annual Income`, and `Spending Score` using histograms
- Examined gender distribution across the customer base
- Used pair plots and correlation heatmaps to identify relationships between numerical features
- Identified that `Annual Income` and `Spending Score` show the clearest separation for clustering

| Observation | Insight |
|---|---|
| Income vs. Spending Score | Reveals distinct behavioral groups, ideal for clustering |
| Age distribution | Skewed toward younger and middle-aged customers |
| Gender split | Roughly balanced, with a slight female majority |

---

## Machine Learning Approach

**Algorithm:** K-Means Clustering

1. **Feature Selection** — `Annual Income (k$)` and `Spending Score (1–100)` selected as clustering features due to their clear separability
2. **Feature Scaling** — Standardized using `StandardScaler` to ensure equal weight across features
3. **Determining Optimal K** — The Elbow Method was used, plotting Within-Cluster Sum of Squares (WCSS) against different values of K to identify the point of diminishing returns
4. **Model Training** — `KMeans` fitted with the optimal number of clusters and a fixed `random_state` for reproducibility
5. **Cluster Assignment** — Each customer labeled with its corresponding segment

```python
from sklearn.preprocessing import StandardScaler
from sklearn.cluster import KMeans

# Feature scaling
scaler = StandardScaler()
scaled_features = scaler.fit_transform(X)

# Elbow Method
wcss = []
for k in range(1, 11):
    kmeans = KMeans(n_clusters=k, init='k-means++', random_state=42)
    kmeans.fit(scaled_features)
    wcss.append(kmeans.inertia_)

# Final model
kmeans = KMeans(n_clusters=5, init='k-means++', random_state=42)
labels = kmeans.fit_predict(scaled_features)
```

---

## Results & Customer Segments

Based on the Elbow Method, **five clusters** were identified as optimal. Each segment represents a distinct customer profile:

| Cluster | Profile | Income Level | Spending Score | Suggested Strategy |
|---|---|---|---|---|
| 0 | Careful Spenders | Low | Low | Minimal marketing investment |
| 1 | Standard Customers | Medium | Medium | Maintain engagement, loyalty offers |
| 2 | Target Customers | High | High | Priority segment for premium campaigns |
| 3 | Careless Spenders | Low | High | Monitor for credit risk, upsell cautiously |
| 4 | Frugal High Earners | High | Low | Incentivize spending through personalized offers |

*(Cluster labels and values reflect typical patterns from this dataset; update with your exact output values after running the notebook.)*

---

## Visualizations

The notebook includes the following visual outputs:

- Distribution plots for Age, Annual Income, and Spending Score
- Correlation heatmap of numerical features
- Elbow Method plot (WCSS vs. number of clusters)
- 2D scatter plot of clusters (Annual Income vs. Spending Score) with centroids highlighted
- Cluster-wise bar charts comparing average age, income, and spending score

---

## Project Structure

```
customer-segmentation-kmeans/
├── data/
│   └── Mall_Customers.csv
├── notebooks/
│   └── customer_segmentation_kmeans.ipynb
├── images/
│   ├── elbow_method.png
│   ├── cluster_plot.png
│   └── correlation_heatmap.png
├── requirements.txt
└── README.md
```

---

## Key Learnings

- Practical application of unsupervised learning on real-world-style data
- Importance of feature scaling before distance-based algorithms like K-Means
- Using the Elbow Method to make data-driven decisions on hyperparameters
- Translating statistical clusters into interpretable, business-relevant customer personas
- Communicating machine learning results through clear visualizations

---

## Future Improvements

- Incorporate additional features such as purchase frequency and product category
- Compare K-Means results with hierarchical clustering and DBSCAN
- Use Silhouette Score alongside the Elbow Method to validate cluster quality
- Build an interactive dashboard (Streamlit) for real-time segment exploration
- Deploy the model as a simple API for integration with business tools

---

## Author

**Isha Patel**
Final-year B.Tech CSE (Big Data Analytics) | Backend & ML Enthusiast

[GitHub](https://github.com/Techie192) · [LinkedIn](https://linkedin.com/in/isha-patel-ba4365314)

---

<div align="center">

*If you found this project useful, consider starring the repository.*

</div>
