# <b style="color: #8A2BE2;">Customer Segmentation Analysis Using RFM & K-Means</b>



---

## 📌 <b style="color: #8A2BE2;">Project Overview</b>
This project focuses on segmenting an e-commerce company's customer base into distinct groups based on their purchasing behavior using <b style="color: #8A2BE2;">RFM (Recency, Frequency, Monetary) Analysis</b> and the <b style="color: #8A2BE2;">K-Means Clustering</b> machine learning algorithm. 

By identifying these behavioral segments, businesses can design targeted marketing strategies, optimize customer retention programs, and maximize overall customer lifetime value.

---

## 🛠️ <b style="color: #8A2BE2;">Technologies & Libraries Used</b>
* **Programming Language:** Python
* **Data Manipulation:** <b style="color: #8A2BE2;">Pandas</b>, <b style="color: #8A2BE2;">NumPy</b>
* **Data Visualization:** <b style="color: #8A2BE2;">Matplotlib</b>, <b style="color: #8A2BE2;">Seaborn</b>
* **Machine Learning:** <b style="color: #8A2BE2;">Scikit-Learn</b> (K-Means Clustering, StandardScaler)
* **Excel File Engine:** <b style="color: #8A2BE2;">OpenPyXL</b>

---

## 📊 <b style="color: #8A2BE2;">Dataset Structure</b>
The analysis was performed on the **Online Retail II** dataset, which contains real transactional records across two major periods:
* <b style="color: #8A2BE2;">Year 2009-2010</b> (Sheet 1)
* <b style="color: #8A2BE2;">Year 2010-2011</b> (Sheet 2)

📥 **[Download Raw Dataset (Online Retail II)](https://archive.ics.uci.edu/ml/datasets/Online+Retail+II)** *(Note: Due to GitHub's file size limitations on direct web uploads, the raw Excel dataset is hosted externally. You can download it directly from the official UCI Machine Learning Repository link above).*

**Combined Raw Dataset Shape:** Over 1 million rows and 8 transactional features.

---

## 🚀 <b style="color: #8A2BE2;">Step-by-Step Implementation</b>

### Step 1: <b style="color: #8A2BE2;">Libraries & Data Loading</b>
Essential tools for data processing and machine learning are imported. Since the dataset is split into multiple sheets, both years are directly read from the Excel file using the openpyxl engine and concatenated into a single master DataFrame.

### Step 2: <b style="color: #8A2BE2;">Data Cleaning & Preprocessing</b>
* Dropped records with missing Customer ID values.
* Handled transaction inconsistencies by filtering out cancellations (Invoices starting with 'C' and negative/zero quantities or prices).

### Step 3: <b style="color: #8A2BE2;">RFM Feature Engineering</b>
Three custom behavioral metrics were calculated per unique customer:
1. <b style="color: #8A2BE2;">Recency:</b> Days since the customer's absolute last purchase.
2. <b style="color: #8A2BE2;">Frequency:</b> The total count of unique invoices or orders placed.
3. <b style="color: #8A2BE2;">Monetary:</b> Total amount of revenue contributed (Quantity * Price).

### Step 4: <b style="color: #8A2BE2;">Data Transformation & Scaling</b>
* Applied a Log Transformation to eliminate extreme right-skewness across RFM distributions.
* Standardized features using StandardScaler to ensure equal feature weight distribution during K-Means clustering.

### Step 5: <b style="color: #8A2BE2;">Finding Optimal Clusters (Elbow Method)</b>
Using the Within-Cluster Sum of Squares (WCSS) plot across a range of 1 to 10 clusters, the ideal number of customer segments was determined to be k=3.

---

## 📈 <b style="color: #8A2BE2;">Final Business Insights & Actionable Strategies</b>

Based on the clustering characteristics, the e-commerce customer base is grouped into three distinct behavioral segments:

### 🟣 <b style="color: #8A2BE2;">Cluster 0 — "Churned / At-Risk Customers" (Low Value)</b>
* **Characteristics:** High Recency (haven't bought in a long time), very low Frequency, and low Monetary spend.
* <b style="color: #8A2BE2;">Strategic Actions:</b>
  * Launch automated Win-Back email campaigns with deep, exclusive discounts.
  * Send feedback surveys to understand customer departure reasons.
  * Reduce high-cost paid ad targeting for this segment to save budget.

### 🟣 <b style="color: #8A2BE2;">Cluster 1 — "Loyal & High-Value Champions" (VIP Customers)</b>
* **Characteristics:** Active recently, exceptionally high purchase frequency, and massive revenue contribution.
* <b style="color: #8A2BE2;">Strategic Actions:</b>
  * Enroll them in a Premium Loyalty / VIP Reward Program giving early access to product launches.
  * Implement personalized cross-selling engines recommending high-end complementary items.
  * Assign priority or dedicated customer support channels to guarantee near-100% retention.

### 🟣 <b style="color: #8A2BE2;">Cluster 2 — "Average / Promising Customers" (Mid-Tier)</b>
* **Characteristics:** Moderate recency, moderate frequency, and steady average spend.
* <b style="color: #8A2BE2;">Strategic Actions:</b>
  * Introduce upselling basket thresholds (e.g., "Spend $50 more to unlock free shipping").
  * Keep them engaged through regular product newsletters and seasonal trending updates.
  * Introduce subscription models or recurring delivery cycles to convert casual buying habits into predictable loyal behavior.

---

## 💻 <b style="color: #8A2BE2;">How to Run This Project</b>
1. Clone the repository and place the downloaded dataset in the root folder.
2. Ensure required dependencies are installed:
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn openpyxl
