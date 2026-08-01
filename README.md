<div align="center">

# Customer Segmentation Analysis

**An unsupervised machine learning project that segments mall customers based on spending behavior and income, enabling data-driven marketing strategies.**

![Python](https://img.shields.io/badge/Python-3.x-3776AB?style=flat-square&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=flat-square&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-Numerical%20Computing-013243?style=flat-square&logo=numpy&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-Machine%20Learning-F7931E?style=flat-square&logo=scikitlearn&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-11557C?style=flat-square)
![Seaborn](https://img.shields.io/badge/Seaborn-Visualization-4C72B0?style=flat-square)
![Google Colab](https://img.shields.io/badge/Google%20Colab-Notebook-F9AB00?style=flat-square&logo=googlecolab&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-informational?style=flat-square)

</div>

---

## Project Overview

This project applies **K-Means Clustering**, an unsupervised machine learning algorithm, to segment mall customers into different groups based on their **annual income** and **spending score**.

The objective is to discover hidden patterns in customer behavior and create meaningful customer segments that can help businesses understand customer preferences and design targeted marketing strategies.

---

## Objectives

- Analyze customer demographic and behavioral data
- Identify patterns in customer spending behavior
- Determine optimal number of clusters using the Elbow Method
- Apply K-Means clustering algorithm
- Visualize and interpret customer segments
- Generate business-oriented insights

---

## Dataset Description

**Dataset:** Mall Customers Dataset

| Attribute | Description |
|---|---|
| CustomerID | Unique identifier for each customer |
| Gender | Customer gender |
| Age | Customer age |
| Annual Income (k$) | Customer annual income |
| Spending Score (1-100) | Customer spending behavior score |

**Total Records:** 200 customers

---

## Technology Stack

| Category | Tools |
|---|---|
| Programming Language | Python |
| Data Processing | Pandas, NumPy |
| Visualization | Matplotlib, Seaborn |
| Machine Learning | Scikit-learn |
| Environment | Google Colab |

---

## Project Workflow

```
Customer Dataset
        |
        ↓
Dataset Understanding
        |
        ↓
Data Cleaning
        |
        ↓
Exploratory Data Analysis
        |
        ↓
Feature Selection
        |
        ↓
Feature Scaling
        |
        ↓
Elbow Method (Optimal K Selection)
        |
        ↓
K-Means Clustering
        |
        ↓
Customer Segmentation
        |
        ↓
Business Insights
```

---

## Exploratory Data Analysis

The dataset was explored to understand customer characteristics and identify relationships between features.

Analysis performed:

- Customer age distribution
- Income distribution analysis
- Spending score analysis
- Income vs spending behavior visualization
- Customer cluster visualization

---

## Machine Learning Approach

### K-Means Clustering

K-Means is an unsupervised machine learning algorithm that groups similar data points into clusters based on feature similarity.

### Steps Performed

1. Selected relevant features:
   - Annual Income (k$)
   - Spending Score (1-100)

2. Applied feature scaling using `StandardScaler`

3. Used the Elbow Method to determine the optimal number of clusters

4. Applied K-Means clustering algorithm

5. Assigned customers into different segments

6. Visualized cluster patterns

---

## Elbow Method

The Elbow Method is used to determine the optimal number of clusters for K-Means.

It calculates **inertia (Within-Cluster Sum of Squares)** for different values of K. The optimal cluster value is selected where the decrease in inertia starts slowing down.

Implementation:

```python
inertia = []

for k in range(1, 11):

    kmeans = KMeans(
        n_clusters=k,
        random_state=42
    )

    kmeans.fit(X_scaled)

    inertia.append(kmeans.inertia_)
```

The elbow point helps identify the suitable number of customer segments.

---

## Results & Customer Segments

The clustering model identified different customer groups based on income and spending patterns.

### High Value Customers

Characteristics:
- High income
- High spending score

Business Strategy:
- Focus on loyalty programs and premium offers

---

### Potential Customers

Characteristics:
- High income
- Lower spending score

Business Strategy:
- Use targeted campaigns to increase engagement

---

### Budget Customers

Characteristics:
- Lower income
- Lower spending score

Business Strategy:
- Provide affordable offers and discounts

---

## Visualizations

The project includes:

- Customer age distribution
- Income vs Spending Score scatter plot
- Elbow Method curve
- Customer cluster visualization

---

## Project Structure

```
Customer-Segmentation-Analysis/

├── Customer_Segmentation_Analysis_KMeans.ipynb
├── Mall_Customers.csv
├── README.md
└── LICENSE
```

---

## Key Learnings

- Data preprocessing
- Exploratory Data Analysis
- Feature scaling
- Unsupervised machine learning
- K-Means clustering
- Data visualization
- Business insight generation

---

## Future Improvements

- Compare clustering algorithms such as DBSCAN and Hierarchical Clustering
- Add additional customer behavior features
- Create interactive dashboards using Tableau or Power BI
- Deploy the model as a web application

---

## Author

**Isha Patel**

B.Tech Computer Science Engineering  
Specialization: Big Data Analytics

GitHub: https://github.com/Techie192

---

<div align="center">

⭐ Building data-driven solutions using analytics and machine learning.

</div>
