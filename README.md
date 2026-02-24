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

# Comprehensive Report: Customer Behavior Analysis

## Executive Summary

This report presents a comprehensive statistical analysis of customer behavior based on a dataset containing 5,000 customer records. The analysis examines purchase patterns, demographic influences, churn relationships, and marketing campaign effectiveness using various statistical methods and visualizations.

---

## 1. Data Overview

**Dataset Characteristics:**
- **Total Records:** 5,000 customers
- **Features:** CustomerID, Gender, Region, PurchaseAmount, ProductCategory, Churn, CampaignGroup
- **Missing Data:** Present in all categorical columns, handled appropriately during analysis
- **Valid Purchase Records:** 4,850 observations

---

## 2. Purchase Amount Analysis

### 2.1 Central Tendency Measures
- **Mean (Average):** $1,003.95
- **Median:** $998.08
- **Mode:** $0.00 (notable due to zero-value purchases)

**Interpretation:** The mean is slightly higher than the median, indicating a mild rightward skew in the distribution. The mode of $0.00 represents customers who made purchases but had zero recorded amounts (possibly returns or promotional items).

### 2.2 Distribution Shape
- **Skewness:** 0.106 (approximately symmetric)
- **Kurtosis:** -0.262 (platykurtic - lighter tails, flatter peak than normal distribution)

**Interpretation:** The purchase amount distribution is roughly symmetric with slightly lighter tails than a normal distribution, suggesting fewer extreme values than expected in a normal distribution.

### 2.3 Outlier Analysis
- **IQR Method:** 15 outliers identified (0.31% of data)
- **Z-Score Method:** 9 outliers identified (0.19% of data)
- **Upper Bound for Outliers:** $2,307.23

**Key Outliers (Top 10 values):**
- $2,318.33, $2,496.41, $2,688.69, $2,349.16, $2,578.89
- $2,384.19, $2,457.05, $2,316.19, $2,400.69, $2,357.41

**Interpretation:** A small percentage of customers (approximately 0.3%) have exceptionally high purchase amounts exceeding $2,300, representing a potential high-value customer segment.

---

## 3. Demographic Analysis

### 3.1 Gender-Based Spending Analysis

| Gender | Sample Size | Average Spending | Standard Deviation  |
|--------|-------------|------------------|---------------------|
| Male   | 2,386       | $1,019.18        | $480.23             |
| Female | 2,370       | $987.87          | $485.76             |

**Statistical Test:** Independent t-test
- **T-statistic:** 2.2348
- **P-value:** 0.0255
- **Conclusion:** **Reject null hypothesis** - There is a significant difference in spending between male and female customers (p < 0.05)

**Insight:** Male customers spend approximately $31 more on average than female customers, with both groups showing similar variability in spending patterns.

### 3.2 Regional Spending Analysis

| Region | Sample Size | Average Spending | Standard Deviation |
|--------|-------------|------------------|--------------------|
| South  | 1,202       | $997.60          | $484.10            |
| West   | 1,115       | $995.25          | $485.80            |
| North  | 1,167       | $1,013.02        | $467.90            |
| East   | 1,195       | $1,009.95        | $490.36            |

**Statistical Test:** One-way ANOVA
- **F-statistic:** 0.3897
- **P-value:** 0.7605
- **Conclusion:** **Fail to reject null hypothesis** - Purchase amounts do not vary significantly across regions (p ≥ 0.05)

**Insight:** Despite minor numerical differences, regional spending patterns are statistically similar, suggesting that geographic location is not a strong predictor of purchase amount.

---

## 4. Product Category and Churn Analysis

### 4.1 Churn Rates by Product Category

| Product Category | No Churn | Yes Churn | Total | Churn Rate |
|------------------|----------|-----------|-------|------------|
| Electronics      | 785      | 541       | 1,326 | 40.80%     |
| Fashion          | 839      | 607       | 1,446 | 41.98%     |
| Grocery          | 855      | 604       | 1,459 | 41.40%     |

**Statistical Test:** Chi-square Test of Independence
- **Chi-square statistic:** 0.3960
- **Degrees of Freedom:** 2
- **P-value:** 0.8204
- **Conclusion:** **Fail to reject null hypothesis** - No significant relationship exists between product category and customer churn

**Insight:** All product categories have similar churn rates (approximately 40-42%), indicating that product type does not meaningfully influence customer retention.

---

## 5. Marketing Campaign Performance

### 5.1 Campaign Comparison

| Campaign | Sample Size | Average Spending | Standard Deviation  |
|----------|-------------|------------------|---------------------|
| A        | 2,350       | $1,011.95        | $480.16             |
| B        | 2,318       | $994.34          | $487.38             |

**Statistical Test:** Independent t-test
- **T-statistic:** 1.2431
- **P-value:** 0.2139
- **Conclusion:** **Fail to reject null hypothesis** - No significant difference in purchase amounts between Campaign A and B

**Insight:** Although Campaign A shows a slightly higher average purchase amount ($17.61 more), this difference is not statistically significant at the 95% confidence level.

---

## 6. Normality Assessment

### 6.1 Statistical Tests for Normality

| Test               | Statistic | P-value | Conclusion |
|--------------------|-----------|---------|------------|
| Shapiro-Wilk       | 0.9950    | < 0.001 | Not Normal |
| D'Agostino's K²    | 27.2516   | < 0.001 | Not Normal |
| Kolmogorov-Smirnov | 0.0187    | 0.0676  | Borderline |

**Interpretation:** Two of three tests reject normality, indicating that purchase amounts do **not** follow a normal distribution. This has implications for the choice of statistical tests and confidence interval calculations.

### 6.2 Central Limit Theorem Application

| Metric                          | Value     |
|---------------------------------|-----------|
| Population Mean                 | $1,003.95 |
| Population Std Dev              | $482.11   |
| Sample Mean Distribution (n=30) | $1,002.79 |
| Sample Std Error                | $87.30    |
| Theoretical Std Error           | $88.02    |
| Difference                      | $0.72     |

**Key Insight:** Despite non-normal population distribution, the sampling distribution of means approximates normality (as demonstrated by CLT), validating the use of parametric methods for group comparisons with sufficient sample sizes.

---

## 7. Confidence Interval Estimation

### 7.1 95% Confidence Intervals for Population Mean

| Method     | Lower Bound | Upper Bound | Width  |
|------------|-------------|-------------|--------|
| Z-interval | $990.38     | $1,017.52   | $27.14 |
| T-interval | $990.38     | $1,017.52   | $27.14 |
| Bootstrap  | $990.35     | $1,017.23   | $26.88 |

**Interpretation:** We can be 95% confident that the true population mean purchase amount falls between $990.38 and $1,017.52. The close agreement between methods validates the robustness of this estimate.

---

## 8. Key Findings Summary

| # | Analysis                  | Finding                   | Statistical Significance   | 
|---|---------------------------|---------------------------|----------------------------|
| 1 | Average Purchase          | $1,003.95                 | N/A                        |
| 2 | Outliers                  | 0.3% of data              | N/A                        |
| 3 | Distribution Shape        | Positively skewed (0.106) | N/A                        |
| 4 | Gender Difference         | Male spend ~$31 more      | **Significant** (p=0.0255) |
| 5 | Product Category vs Churn | Churn rates 40-42%        | Not Significant (p=0.8204) |
| 6 | Regional Differences      | East highest ($1,010)     | Not Significant (p=0.7605) |
| 7 | Campaign Performance      | Campaign A higher         | Not Significant (p=0.2139) |
| 8 | Normal Distribution       | Not normal                | p < 0.001                  |            
| 9 | CLT Application           | Sample means normal       | Demonstrated               |
| 10 | 95% CI                   | ($990.38, $1,017.52)      | N/A                        |

---

## 9. Business Recommendations

### 9.1 Targeting Strategies
1. **Gender-Based Marketing:** Develop targeted campaigns for male customers who demonstrate higher average spending
2. **High-Value Segment:** Create VIP programs for the top 0.3% of customers with purchases > $2,300

### 9.2 Campaign Optimization
1. **Campaign Refinement:** Investigate why Campaign A shows slightly better (though not significant) performance; consider A/B testing with larger samples
2. **Channel Strategy:** Allocate marketing budget efficiently across both campaigns since no significant performance difference exists

### 9.3 Product and Retention
1. **Churn Analysis:** Since churn is consistent across categories, implement company-wide retention programs rather than category-specific interventions
2. **Regional Strategy:** While regional differences aren't statistically significant, consider East region as a potential test market due to its highest average spending

### 9.4 Statistical Considerations
1. **Future Analysis:** Use non-parametric tests or transformations when analyzing purchase amounts due to non-normal distribution
2. **Sample Size Planning:** Current sample sizes are adequate; maintain similar sizes for future comparative studies

---

## 10. Limitations and Future Directions

### 10.1 Limitations
1. Missing data in several variables may introduce bias
2. Cross-sectional data prevents causal inference
3. Zero purchase values need investigation (possible data quality issues)

### 10.2 Future Research
1. Longitudinal analysis to track customer behavior over time
2. Machine learning models to predict churn probability
3. Deeper analysis of high-value customer characteristics
4. Investigation of interaction effects between demographic variables

---

