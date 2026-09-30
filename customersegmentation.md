## Customer Segmentation - Online Retail K-Means Clustering

<img class="project-shot" src="/images/customer-segments.png" alt="3D scatter plot of customer clusters"/>

**Project Description**

Customer segmentation is crucial for businesses to understand their customer base and tailor marketing strategies effectively. This data science project applies unsupervised learning techniques to segment customers of an online retail store based on their purchasing behavior patterns using the MRF (Monetary Value, Recency, and Frequency) framework.

**GitHub Repository:** [CustomerSegmentation-OnlineRetail-KMeans](https://github.com/alexkimrow/CustomerSegmentation-OnlineRetail-KMeans)

---

### Problem Statement

Online retailers face challenges in understanding diverse customer behaviors and optimizing marketing spend. Without proper segmentation, businesses risk:

- Inefficient marketing campaigns targeting wrong customer groups
- Lost revenue from unrecognized high-value customers
- Wasted resources on customers unlikely to convert

This project addresses these challenges by identifying distinct customer segments to enable targeted business strategies.

---

### Methodology

#### Data Preprocessing

- **Dataset:** Online Retail II dataset from Kaggle containing transactional data
- **Cleaning Steps:**
  - Removed null values and duplicate transactions
  - Filtered out negative quantities (returns) and prices
  - Handled outliers using IQR (Interquartile Range) method
  - Created customer-level aggregations from transaction-level data

#### Feature Engineering - MRF Framework

Engineered three key features to capture customer value:

1. **Monetary Value (M):** Total spending per customer

```python
monetary = df.groupby('CustomerID')['TotalPrice'].sum()
```

2. **Recency (R):** Days since last purchase (inverted for clustering)

```python
recency = (reference_date - df.groupby('CustomerID')['InvoiceDate'].max()).dt.days
```

3. **Frequency (F):** Number of unique purchases

```python
frequency = df.groupby('CustomerID')['InvoiceNo'].nunique()
```

#### Model Selection & Optimization

- **Algorithm:** K-Means Clustering
- **Optimization Approach:**
  - Elbow Method to identify optimal number of clusters
  - Silhouette Score analysis for cluster quality validation
  - Tested k values ranging from 2 to 10
- **Feature Scaling:** StandardScaler to normalize MRF features
- **Optimal Clusters:** 4 clusters identified based on inertia and silhouette metrics

---

### Technical Implementation

```python
from sklearn.cluster import KMeans
from sklearn.preprocessing import StandardScaler
import pandas as pd
import numpy as np

# Feature scaling
scaler = StandardScaler()
rfm_scaled = scaler.fit_transform(rfm_df[['Monetary', 'Frequency', 'Recency']])

# K-Means clustering
kmeans = KMeans(n_clusters=4, random_state=42, n_init=10)
rfm_df['Cluster'] = kmeans.fit_predict(rfm_scaled)

# Analyze cluster characteristics
cluster_summary = rfm_df.groupby('Cluster').agg({
    'Monetary': ['mean', 'median'],
    'Frequency': ['mean', 'median'],
    'Recency': ['mean', 'median'],
    'CustomerID': 'count'
}).round(2)
```

---

### Results & Business Insights

#### Cluster Profiles

**Cluster 0 - Champions (High Value, High Engagement)**

- Highest monetary value and purchase frequency
- Recent purchases (low recency)
- **Business Strategy:** VIP treatment, exclusive offers, early access to new products
- **Marketing Focus:** Retention programs, loyalty rewards

**Cluster 1 - Loyal Customers (Moderate Value, Consistent)**

- Moderate spending with regular purchase patterns
- Consistent engagement over time
- **Business Strategy:** Upselling opportunities, referral programs
- **Marketing Focus:** Cross-selling campaigns, engagement emails

**Cluster 2 - At-Risk Customers (Declining Activity)**

- Previously active but high recency (not purchased recently)
- Moderate to low frequency
- **Business Strategy:** Re-engagement campaigns, win-back offers
- **Marketing Focus:** Personalized discounts, feedback surveys

**Cluster 3 - New/Low-Value Customers**

- Low monetary value and frequency
- Recent first-time or infrequent buyers
- **Business Strategy:** Onboarding programs, incentives for second purchase
- **Marketing Focus:** Welcome series, introductory discounts

#### Performance Metrics

- **Silhouette Score:** 0.42 (indicating reasonable cluster separation)
- **Inertia Reduction:** 73% from k=2 to k=4
- **Cluster Distribution:** Relatively balanced with slight concentration in loyal customer segment

---

### Visualizations

The project includes comprehensive visualizations:

- 3D scatter plots of customer clusters in MRF space
- Distribution plots showing feature characteristics by cluster
- Box plots identifying outliers and spread within clusters
- Elbow curve and silhouette analysis plots

---

### Technologies Used

- **Python:** Core programming language
- **Pandas:** Data manipulation and aggregation
- **Scikit-learn:** K-Means clustering, StandardScaler, metrics
- **Matplotlib & Seaborn:** Data visualization
- **NumPy:** Numerical computations
- **Jupyter Notebook:** Interactive development environment

---

### Impact & Recommendations

**Quantifiable Business Value:**

- Enables targeted marketing with 25-40% improved conversion rates (industry benchmark)
- Reduces marketing waste by focusing on appropriate customer segments
- Identifies at-risk customers early for retention efforts
- Optimizes resource allocation across customer lifecycle stages

**Next Steps:**

1. Implement time-series analysis to track cluster migration
2. Develop predictive models for customer lifetime value (CLV)
3. A/B test segment-specific campaigns to validate strategies
4. Integrate results with CRM system for automated personalization

---

### Technical Learnings

- Importance of outlier treatment in clustering algorithms
- Feature scaling significantly impacts K-Means performance
- Domain knowledge (MRF framework) crucial for interpretable segmentation
- Multiple evaluation metrics needed for comprehensive model assessment
