# SMARTCART E-Commerce Customer Segmentation Project

## Project Overview

SMARTCART is a Data Science and Machine Learning project focused on **Customer Segmentation for E-Commerce Businesses** using clustering techniques.

The main objective of this project is to analyze customer purchasing behavior, preprocess customer data, engineer meaningful features, and group customers into different clusters based on similarities in spending habits, demographics, and engagement.

This project demonstrates an end-to-end **Data Science Workflow**, including:

- Data Cleaning
- Feature Engineering
- Exploratory Data Analysis (EDA)
- Data Preprocessing
- Dimensionality Reduction
- Unsupervised Machine Learning
- Customer Segmentation
- Cluster Visualization
- Business Insights

---

# Project Goals

The major goals of this project are:

- Understand customer behavior patterns
- Identify high-value customers
- Segment customers based on purchasing habits
- Help businesses create targeted marketing strategies
- Improve customer retention and personalization
- Demonstrate practical machine learning skills for real-world applications

---

# Problem Statement

E-commerce companies collect massive amounts of customer data, but raw data alone cannot generate business value.

This project solves the problem by:

- Cleaning customer datasets
- Extracting meaningful customer features
- Applying clustering algorithms
- Finding hidden customer groups
- Visualizing customer segments for business decision-making

---

# Dataset Information

The dataset contains customer-related information such as:

| Feature Category | Description |
|---|---|
| Demographics | Age, Education, Marital Status |
| Income | Annual Income of customers |
| Purchase Data | Spending on different products |
| Customer Engagement | Recency, Customer tenure |
| Household Information | Kids and Teen information |
| Campaign Response | Customer response to campaigns |

### Important Dataset Columns

- `Income`
- `Year_Birth`
- `Dt_Customer`
- `Education`
- `Marital_Status`
- `Recency`
- `MntWines`
- `MntFruits`
- `MntMeatProducts`
- `MntFishProducts`
- `MntSweetProducts`
- `MntGoldProds`
- `Kidhome`
- `Teenhome`
- `Response`

---

# Technologies Used

## Programming Language

- Python

## Libraries Used

### Data Manipulation

- pandas
- numpy

### Data Visualization

- matplotlib
- seaborn

### Machine Learning

- scikit-learn
- kneed

### Clustering Algorithms

- KMeans
- Agglomerative Clustering

### Dimensionality Reduction

- PCA (Principal Component Analysis)

---

# Project Workflow

## 1️⃣ Data Loading

The dataset is loaded using Pandas:

```python
import pandas as pd

df = pd.read_csv("smartcart_customers.csv")
```

---

## 2️⃣ Data Preprocessing

### Missing Value Handling

The missing values in the `Income` column are filled using the median value.

```python
df["Income"] = df["Income"].fillna(df["Income"].median())
```

### Data Inspection

- Dataset shape
- Null values
- Data types
- Statistical summary

---

# Feature Engineering

Feature Engineering plays a major role in improving clustering quality.

## 🔹 Age Feature

The `Year_Birth` feature is converted into customer age.

```python
df["Age"] = 2026 - df["Year_Birth"]
```

---

## 🔹 Customer Tenure

The customer joining date is converted into customer tenure in days.

```python
df["Dt_Customer"] = pd.to_datetime(df["Dt_Customer"])
```

---

## 🔹 Total Spending

A new feature called `Total_Spending` is created by summing spending across product categories.

```python
df["Total_Spending"] = (
    df["MntWines"] +
    df["MntFruits"] +
    df["MntMeatProducts"] +
    df["MntFishProducts"] +
    df["MntGoldProds"] +
    df["MntSweetProducts"]
)
```

---

## 🔹 Total Children

```python
df["Total_Children"] = df["Teenhome"] + df["Kidhome"]
```

---

## 🔹 Education Categorization

Education levels are grouped into:

- Undergraduate
- Graduate
- Postgraduate

---

## 🔹 Living Status

Marital status is transformed into simplified categories:

- Partner
- Alone

---

# Data Cleaning

## Columns Removed

The following unnecessary columns are dropped:

```python
cols = [
    "ID",
    "Year_Birth",
    "Marital_Status",
    "Kidhome",
    "Teenhome",
    "Dt_Customer"
]
```

---

## Outlier Handling

Outliers are removed to improve clustering performance.

Conditions used:

```python
Income < 600000
Age <= 90
```

---

# Encoding

Categorical variables are transformed using **One Hot Encoding**.

```python
from sklearn.preprocessing import OneHotEncoder
```

Features encoded:

- Education
- Living_with

---

# Feature Scaling

Data is standardized using `StandardScaler`.

```python
from sklearn.preprocessing import StandardScaler
```

This ensures all features contribute equally during clustering.

---

# Dimensionality Reduction using PCA

Principal Component Analysis (PCA) is applied to reduce dimensionality and visualize customer groups.

## 2D Visualization

```python
from sklearn.decomposition import PCA
```

## 3D Visualization

The project also visualizes customer clusters in 3D space.

---

# Cluster Analysis

## 🔹 Elbow Method

Used to identify the optimal number of clusters.

The Within Cluster Sum of Squares (WCSS) is analyzed.

---

## 🔹 Silhouette Score

Used to evaluate cluster quality.

Higher silhouette score indicates better clustering performance.

---

# Clustering Algorithms Used

## 1️⃣ KMeans Clustering

```python
from sklearn.cluster import KMeans
```

KMeans is used to divide customers into distinct segments.

---

## 2️⃣ Agglomerative Clustering

```python
from sklearn.cluster import AgglomerativeClustering
```

Hierarchical clustering is used for comparison and deeper cluster analysis.

---

# Cluster Visualization

The project visualizes customer groups using:

- Scatter plots
- PCA plots
- Count plots
- 3D cluster visualizations
- Heatmaps

---

# Cluster Characterization

The clusters are analyzed based on:

- Income
- Spending behavior
- Age
- Customer response
- Household composition

This helps identify:

- High-value customers
- Low-engagement customers
- Premium buyers
- Potential target audiences

---

# Key Insights

Some important business insights generated from this project:

- Customers with higher income generally spend more.
- Certain customer groups respond better to campaigns.
- Customer segmentation helps create personalized marketing.
- PCA improves visualization and cluster understanding.
- Clustering reveals hidden customer behavior patterns.

---

# Future Improvements

Possible future enhancements:

- Deploy as a web application
- Build customer recommendation systems
- Add dashboard visualizations using Power BI or Tableau
- Integrate real-time customer analytics
- Compare more clustering algorithms
- Hyperparameter optimization
- Automate pipeline using MLflow

---

# Real-World Applications

This project can be used in:

- E-Commerce Platforms
- Retail Analytics
- Marketing Analytics
- Customer Relationship Management (CRM)
- Personalized Recommendation Systems
- Business Intelligence

---

# Skills Demonstrated

This project demonstrates:

## Data Science Skills

- Data Cleaning
- Data Preprocessing
- Feature Engineering
- Exploratory Data Analysis
- Statistical Understanding
- Data Visualization

## Machine Learning Skills

- Unsupervised Learning
- Clustering
- PCA
- Model Evaluation

## Business Understanding

- Customer Segmentation
- Consumer Behavior Analysis
- Business Insight Generation
- Marketing Analytics

---

# Learning Outcomes

After completing this project, you will understand:

- How real-world customer data is processed
- How clustering works in Machine Learning
- How PCA helps in visualization
- How businesses use customer segmentation
- How to generate actionable business insights from data

---

# Author

## Diksha Patel

Aspiring Data Scientist | Machine Learning Enthusiast | Analytics Learner

---



