# Customer Behavior Analysis – Statistics Project

## 📌 Project Objective
This project analyzes customer purchasing behavior using statistical and mathematical tools in Python. The objective is to identify patterns in customer spending, understand churn behavior, and evaluate the effectiveness of marketing campaigns.

---

## 📂 Dataset Description
The dataset contains the following columns:

- **CustomerID** – Unique identifier for each customer  
- **Gender** – Male or Female  
- **Region** – Customer’s geographical region  
- **PurchaseAmount** – Amount spent by the customer  
- **ProductCategory** – Category of product purchased  
- **Churn** – Customer churn status (Yes / No)  
- **CampaignGroup** – Email campaign group (A or B)

---

## 🧹 Data Preprocessing
- Verified data types
- Checked for missing values
- Ensured numerical consistency in `PurchaseAmount`
- Prepared categorical variables for statistical analysis

---

## 📊 Statistical Analysis Performed
- Descriptive statistics (mean, median, mode)
- Outlier detection using IQR method
- Skewness and kurtosis analysis
- Hypothesis testing:
  - Independent t-test (Gender vs PurchaseAmount)
  - Chi-square test (ProductCategory vs Churn)
  - ANOVA (Region vs PurchaseAmount)
- Normality testing
- Central Limit Theorem demonstration
- 95% Confidence Interval estimation
- Campaign performance comparison (A vs B)

---

## 📈 Visualizations Included
- Histogram of PurchaseAmount
- Boxplot for outlier detection
- Bar chart comparing Campaign A and B
- Sampling distribution of the mean (CLT)

---

## 🔍 Key Insights
- PurchaseAmount is approximately normally distributed
- No significant difference in spending based on gender or region
- Product category does not significantly impact churn
- Campaign A performs better than Campaign B
- A small number of outliers represent extreme spending behavior

---

## 🛠️ Tools & Libraries Used
- Python
- Pandas
- NumPy
- SciPy
- Matplotlib
- Jupyter Notebook

---

## 📁 Repository Structure
