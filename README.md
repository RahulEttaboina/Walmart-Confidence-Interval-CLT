# Walmart Confidence Interval & CLT Analysis

## 📌 Project Overview

This project analyzes customer purchase behavior from Walmart's Black Friday sales data, with a focus on purchase amounts and customer characteristics. The analysis uses Exploratory Data Analysis (EDA), statistical distributions, the Central Limit Theorem (CLT), and confidence intervals to understand purchasing behavior across customer segments.

The project is designed to support data-driven understanding of customer purchase patterns, particularly differences between male and female customers.

---

## 🎯 Business Objective

The objective is to analyze customer purchase behavior, with a specific focus on purchase amounts in relation to customer gender during Walmart's Black Friday sales event.

The analysis explores:

- Customer demographics
- Purchase amount distributions
- Gender-based purchasing behavior
- Age, marital status, and city-category patterns
- Product-category preferences
- Correlation between numerical variables
- Sampling distributions of customer spending
- Confidence intervals for average spending

---

## 📊 Dataset

The dataset contains **550,068 transaction records** and **10 columns**.

| Feature | Description |
|---|---|
| `User_ID` | Unique customer identifier |
| `Product_ID` | Product identifier |
| `Gender` | Customer gender |
| `Age` | Customer age group |
| `Occupation` | Occupation category |
| `City_Category` | City category (A, B, C) |
| `Stay_In_Current_City_Years` | Years the customer has stayed in the current city |
| `Marital_Status` | Customer marital-status indicator |
| `Product_Category` | Product category |
| `Purchase` | Purchase amount |

The analysis found no missing values and no duplicate transaction rows. There are **5,891 unique customers** and **3,631 unique products** in the dataset.

---

## 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- SciPy
- Jupyter Notebook

---

## 🔎 Exploratory Data Analysis

### Dataset Structure

The dataset contains:

- 550,068 transactions
- 5,891 unique customers
- 3,631 unique products
- 2 genders
- 7 age groups
- 3 city categories
- 20 product categories
- 21 occupation categories

The average transaction purchase amount is approximately **9,263.97**, with a median of **8,047**.

The difference between the mean and median, together with the box plot and distribution analysis, indicates that the purchase amount contains outliers and is right-skewed.

### Customer Demographics

The analysis identifies several notable patterns:

- Approximately 72% of unique customers are male and 28% are female.
- The 26–35 age group represents the largest customer segment.
- Approximately 60% of customers are unmarried and 40% are married.
- City Category C has the largest number of unique customers.
- Customers staying around 1 year in their current city form the largest stay-duration group.
- Product Categories 1, 5, and 8 are the most frequently purchased categories.

---

## 📈 Purchase Amount Analysis

The project uses box plots and distribution plots to investigate purchase amounts.

The original purchase distribution contains outliers. The analysis handles these using the **IQR method**:

- Q1 = 5,823
- Q3 = 12,054
- IQR = 6,231

The notebook creates a processed dataset using clipping based on the IQR boundaries.

---

## 👥 Gender-Based Analysis

The analysis compares purchase behavior between male and female customers.

The notebook shows that male customers account for a substantially larger share of transactions, and the transaction-level spending distribution is also higher for male customers.

The project further aggregates purchase amounts by `User_ID` and `Gender` so that customer-level spending can be analyzed before applying sampling and CLT techniques.

---

## 📦 Product & Customer Segment Analysis

The project examines purchasing behavior across:

- Gender
- Age
- Marital Status
- City Category
- Stay in Current City
- Product Category

Some observations from the notebook include:

- Product Categories 5 and 8 are particularly represented among female customers.
- Product Categories 1 and 5 are particularly represented among male customers.
- City Category C shows higher purchase levels in the gender-based comparison.
- Purchase medians across gender, marital status, city category, and age groups are relatively similar in the bivariate box-plot analysis.
- Most customers fall within the 18–45 age range.

---

## 🔗 Correlation Analysis

The numerical correlation analysis shows:

| Variable Pair | Correlation |
|---|---:|
| Occupation ↔ Product Category | -0.0076 |
| Occupation ↔ Purchase | 0.0209 |
| Product Category ↔ Purchase | -0.3474 |

The notebook notes that the dataset is heavily categorical, which limits the usefulness of simple correlation analysis for explaining many customer-behavior relationships.

---

## 📐 Central Limit Theorem (CLT)

A major part of the project demonstrates the **Central Limit Theorem** using customer-level purchase totals.

The analysis:

1. Aggregates purchase amounts by customer and gender.
2. Creates separate male and female customer datasets.
3. Draws repeated bootstrap samples.
4. Uses:
   - Male sample size = 3,000
   - Female sample size = 1,500
   - Number of repetitions = 1,000
5. Calculates the mean purchase amount for every sample.
6. Visualizes the resulting sampling distributions.

The sampling-distribution plots demonstrate that the distributions of sample means become approximately bell-shaped.

---

## 📊 Confidence Interval Analysis

The notebook calculates 95% confidence intervals for the mean customer-level purchase amount using:

**Confidence Interval = Sample Mean ± 1.96 × (Sample Standard Deviation / √n)**

### Gender-based results from the calculated confidence-interval section

| Segment | Sample Mean | 95% Confidence Interval |
|---|---:|---:|
| Male | 663,653.05 | 639,825.01 – 687,481.08 |
| Female | 201,363.54 | 187,680.36 – 215,046.73 |

These values are based on the customer-level purchase totals created in the notebook rather than individual transaction rows.

> **Note:** The notebook contains a separate later observation with different average-spending values from the directly calculated sample means and confidence intervals. This README uses the values printed alongside the actual confidence-interval calculations to keep the project documentation internally consistent.

---

## 💡 Key Business Insights

Based on the analysis performed in the notebook:

1. Male customers represent the majority of customers and transactions in the dataset.
2. The 26–35 age group is the largest customer segment.
3. Customers aged 18–45 account for the majority of purchases.
4. City Category C has the largest customer base and shows higher purchase levels in the gender-based comparison.
5. Product Categories 1, 5, and 8 are among the most frequently purchased categories.
6. Purchase distributions contain outliers and are right-skewed.
7. Customer-level purchase totals show a substantial difference between male and female groups.
8. The CLT sampling distributions provide a statistical framework for estimating population mean spending.
9. Confidence intervals quantify the uncertainty around estimated average customer spending.

---

## 📁 Project Structure

```text
Walmart-Confidence-Interval-CLT/
│
├── Walmart_Confidence_Interval_and_CLT.ipynb
├── Walmart_Confidence_Interval_and_CLT.pdf
└── README.md
```

---

## ▶️ How to Run the Project

### 1. Clone the repository

```bash
git clone https://github.com/RahulEttaboina/Walmart-Confidence-Interval-CLT.git
```

### 2. Navigate to the project

```bash
cd Walmart-Confidence-Interval-CLT
```

### 3. Install the required libraries

```bash
pip install numpy pandas matplotlib seaborn scipy jupyter
```

### 4. Open the notebook

```bash
jupyter notebook Walmart_Confidence_Interval_and_CLT.ipynb
```

### Dataset Note

The original `walmart_data.txt` dataset is intentionally **not included in this repository**. The notebook references the local dataset file:

```text
walmart_data.txt
```

Place the dataset in the appropriate working directory before executing the notebook from scratch.

---

## 📄 Project Files

### Jupyter Notebook

`Walmart_Confidence_Interval_and_CLT.ipynb`

Contains the complete Python analysis, visualizations, statistical calculations, CLT demonstration, and confidence-interval calculations.

### PDF Report

`Walmart_Confidence_Interval_and_CLT.pdf`

Provides a rendered version of the analysis and visualizations for easy review.

---

## 🎓 Skills Demonstrated

- Exploratory Data Analysis
- Data Cleaning
- Data Aggregation
- Statistical Analysis
- Central Limit Theorem
- Sampling Distributions
- Confidence Intervals
- Outlier Detection
- IQR-based Outlier Handling
- Distribution Analysis
- Correlation Analysis
- Data Visualization
- Python Programming
- Pandas & NumPy
- Matplotlib & Seaborn
- SciPy

---

## 📌 Portfolio Takeaway

This project demonstrates how Python and statistical techniques can be used to move from raw retail transaction data to customer-segment insights and statistical estimates.

It combines **EDA + visualization + statistical inference**, with particular emphasis on the **Central Limit Theorem and confidence intervals**.
