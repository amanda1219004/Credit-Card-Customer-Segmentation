# Credit-Card-Customer-Segmentation
Credit card customer segmentation using K-Means Clustering and PCA to identify spending patterns, analyze customer behavior, and develop targeted marketing strategies.


# Credit Card Customer Segmentation Using K-Means Clustering

## Project Overview

This project focuses on **customer segmentation using K-Means Clustering**, an unsupervised machine learning algorithm, to analyze credit card usage behavior at Bank Berlian.

The dataset contains credit card transaction information over a six-month period. The objective is to identify distinct customer segments based on spending patterns, credit limits, payment behavior, and cash advance usage.

By understanding the characteristics of each customer segment, the marketing team can develop **targeted marketing campaigns, improve customer engagement, and optimize customer retention strategies**.

## Project Objectives

1. Analyze customer credit card usage patterns through Exploratory Data Analysis (EDA).
2. Identify relationships between customer tenure, spending behavior, credit limits, and purchase frequency.
3. Perform customer segmentation using K-Means Clustering.
4. Determine the optimal number of clusters using the Elbow Method and Silhouette Score.
5. Develop business recommendations based on the characteristics of each customer segment.

## Dataset

The dataset consists of **4,474 customer records and 18 columns**, representing individual credit card usage behavior.


### Data Quality

- Missing values were identified in `CREDIT_LIMIT` and `MINIMUM_PAYMENTS`.
- Missing values were handled using median imputation.
- No duplicate records were identified.
- Several numerical features showed skewed distributions and outliers.

## Tech Stack

**Programming Language:**
- Python

**Libraries:**
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Feature-engine
- SciPy

**Machine Learning Techniques:**
- K-Means Clustering
- Principal Component Analysis (PCA)
- Elbow Method
- Silhouette Score

## Project Workflow

### 1. Data Understanding and EDA

Exploratory Data Analysis was conducted to understand customer behavior and identify relationships between important variables.

**Key Findings:**

- `TENURE` has a weak positive correlation with `PURCHASES`, `BALANCE`, and `PAYMENTS`.
- The strongest Spearman correlation among these relationships is between `TENURE` and `PAYMENTS`.
- `CREDIT_LIMIT` and `PURCHASES_FREQUENCY` also show a weak positive correlation.
- Customers with higher credit limits tend to make purchases slightly more frequently, but credit limit alone does not strongly explain purchasing behavior.

### 2. Data Preprocessing

Several preprocessing techniques were applied before clustering.

| Step | Method | Purpose |
|------|--------|---------|
| Missing Value Handling | SimpleImputer (Median) | Handle missing numerical values |
| Outlier Handling | Winsorizer (Quantiles) | Reduce the influence of extreme values |
| Feature Scaling | StandardScaler | Standardize numerical features |
| Dimensionality Reduction | PCA | Reduce feature dimensionality |

**Principal Component Analysis (PCA)** reduced the dataset from 17 original features to **4 principal components**, which were used for clustering.

### 3. Model Development

The **K-Means Clustering algorithm** was implemented to group customers based on similarities in their credit card usage behavior.

The optimal number of clusters was determined using:

- **Elbow Method:** Evaluates changes in inertia as the number of clusters increases.
- **Silhouette Score:** Measures how well observations fit within their assigned clusters compared to other clusters.

### 4. Model Evaluation

The highest Silhouette Score was achieved with **K=3**, with a score of approximately **0.55**.

The Elbow Method also supported selecting three clusters, as the reduction in inertia became less significant beyond this point.

**Final Model: K-Means Clustering (K=3)**

This configuration was selected because it provides relatively good cluster separation while maintaining a manageable number of customer segments.

## Customer Segmentation Results

The final model identified three customer segments with different financial behaviors and transaction patterns.

### Cluster 0 - Medium Purchase / Medium Limit

**Approximately 77% of customers (3,436 users)**

Characteristics:
- Largest customer segment.
- Relatively low purchase activity.
- Medium credit limits.
- Relatively long customer tenure.

**Business Recommendations:**
1. Launch targeted campaigns to encourage more frequent credit card purchases.
2. Provide cashback and reward programs for retail transactions.

### Cluster 1 - High Purchase / High Limit

**Approximately 15% of customers (656 users)**

Characteristics:
- Highest purchase activity.
- High credit card usage.
- Average balance approximately four times higher than other clusters.
- Longest customer tenure.

**Business Recommendations:**
1. Implement loyalty programs to improve customer retention.
2. Offer premium benefits and exclusive rewards.
3. Strengthen customer relationship management to maintain customer satisfaction.

### Cluster 2 - Low Purchase / Cash Oriented

**Approximately 9% of customers (383 users)**

Characteristics:
- Smallest customer segment.
- Lowest purchase activity.
- Relatively high cash advance usage.
- Shortest customer tenure.

**Business Recommendations:**
1. Encourage credit card purchases through targeted marketing campaigns.
2. Provide cashback and rewards for selected transactions.
3. Increase awareness of the benefits of direct credit card purchases to reduce dependence on cash advances.

## Model Advantages and Limitations

### Advantages

- K-Means is simple and easy to interpret.
- The clustering process is computationally efficient.
- PCA helps reduce dimensionality and feature complexity.
- The resulting customer segments can support targeted marketing strategies.

### Limitations

- The number of clusters must be specified beforehand.
- K-Means is sensitive to outliers.
- Feature scaling is required because K-Means is distance-based.
- Customer segments may change as transaction behavior evolves.

## Future Improvements

Several improvements could enhance the quality and business value of the segmentation model:

1. **Algorithm Comparison:** Compare K-Means with Hierarchical Clustering and DBSCAN.
2. **Hyperparameter Tuning:** Experiment with different `random_state` and `n_init` values to evaluate clustering stability.
3. **Business Data Integration:** Combine segmentation results with marketing campaign responses and other customer information.
4. **Model Monitoring:** Periodically update customer segments to reflect changes in transaction behavior.

## Conclusion

This project successfully implemented **K-Means Clustering with PCA** to identify three distinct customer segments based on credit card usage behavior.

The final model achieved a **Silhouette Score of approximately 0.55**, indicating relatively good cluster separation.

The segmentation results provide valuable insights into customer spending patterns, allowing the marketing team to develop more targeted strategies for customer engagement, retention, and transaction growth.
