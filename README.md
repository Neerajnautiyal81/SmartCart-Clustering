# 🛒 SmartCart Customer Segmentation (Clustering Project)

## 📌 Project Overview
This project focuses on **customer segmentation using unsupervised machine learning techniques**. The objective is to group customers based on their demographics, purchasing behavior, and engagement patterns.

By applying clustering algorithms, we identify different customer groups that can help businesses improve **marketing strategies, personalization, and decision-making**.

---

## 📂 Dataset
- File: `smartcart_customers.csv`
- Total Records: **2240**
- Key Features:
  - Customer demographics (Age, Income, Education)
  - Purchase behavior (product spending)
  - Activity metrics (web visits, purchases, recency)

---

## ⚙️ Data Preprocessing

### ✔️ Missing Values
- Filled missing values in `Income` using **median**

### ✔️ Feature Engineering
- **Age** = 2026 − Year_Birth  
- **Customer Tenure** = Days since customer joined  
- **Total Spending** = Sum of all product categories  
- **Total Children** = Kidhome + Teenhome  

### ✔️ Categorical Transformation
- Education:
  - Undergraduate, Graduate, Postgraduate  
- Marital Status → Living_With:
  - Alone, Partner  

### ✔️ Dropped Columns
- Removed irrelevant columns:
  - `ID`, `Year_Birth`, `Dt_Customer`
  - Individual product spending columns  

---

## 📊 Exploratory Data Analysis (EDA)
- Pairplot visualization for feature relationships  
- Correlation heatmap  
- Outlier removal:
  - Age < 90  
  - Income < 600,000  

---

## 🔄 Data Transformation

### ✔️ Encoding
- Applied **One-Hot Encoding** on:
  - `Education`
  - `Living_With`

### ✔️ Scaling
- Used **StandardScaler** for normalization  

---

## 📉 Dimensionality Reduction
- Applied **PCA (Principal Component Analysis)**
- Reduced features to **3 components**
- Explained variance:
  - PC1: 23%
  - PC2: 11%
  - PC3: 10%

---

## 📌 Finding Optimal Clusters

### 🔹 Elbow Method
- Used WCSS to determine optimal clusters  
- Optimal value: **K = 4**

### 🔹 Silhouette Score
- Validated clustering performance  
- Confirms **K = 4**

---

## 🤖 Clustering Algorithms Used

### 1️⃣ K-Means Clustering
- Efficient centroid-based clustering  
- Used for initial segmentation  

### 2️⃣ Agglomerative Clustering
- Hierarchical clustering approach  
- Used for final cluster labeling  

---

## 📊 Cluster Insights

| Cluster | Description |
|--------|------------|
| **0** | Low income, moderate spending, mostly partnered |
| **1** | High income, high spending, active customers |
| **2** | Low income, low spending, mostly alone |
| **3** | High income, high response rate (target customers) |

---

## 📈 Key Insights
- Income strongly influences customer spending  
- Customers with fewer children spend more  
- High-income groups respond better to campaigns  
- Living status affects purchasing behavior  

---

## 🛠️ Tech Stack
- Python  
- Pandas, NumPy  
- Matplotlib, Seaborn  
- Scikit-learn  

---

## 🚀 How to Run

```bash
git clone https://github.com/Neerajnautiyal81/SmartCart-Clustering.git
cd SmartCart-Clustering
pip install -r requirements.txt
jupyter notebook
