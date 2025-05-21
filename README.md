# Supermarket Sales Data Analysis

## Project Overview
This project analyzes **supermarket transactions** from a chain in Myanmar, aiming to uncover trends in customer behavior, product preferences, and purchasing patterns. The dataset consists of **1,000 individual transactions**, each containing detailed attributes related to the sale.

## Dataset
The dataset includes **17 attributes** capturing customer demographics, purchasing details, and transaction summaries.

### Attributes:
- **Invoice ID** – Unique identifier for each transaction.
- **Branch** – Supermarket branch location (**Yangon, Naypyitaw, Mandalay**).
- **City** – City corresponding to the branch.
- **Customer Type** – Indicates whether the customer is a **Member** or **Normal**.
- **Gender** – Gender of the customer.
- **Product Line** – Category of the product sold (**Health & Beauty, Electronic Accessories, Home & Lifestyle, etc.**).
- **Unit Price** – Price per unit of the product.
- **Quantity** – Number of items purchased.
- **Tax 5%** – Tax amount (5% rate).
- **Total** – Total transaction amount including tax.
- **Date** – Date of the transaction.
- **Time** – Time of the transaction.
- **Payment** – Payment method (**Cash, Ewallet, Credit card**).
- **COGS (Cost of Goods Sold)** – Represents the raw cost of the products.
- **Gross Margin Percentage** – Fixed profit percentage (**4.7619%**).
- **Gross Income** – Profit earned from the transaction.
- **Rating** – Customer satisfaction rating (out of 10).

## Data Processing Steps
### 1. Data Cleaning
- Checked for missing values (none found).
- Converted **Date** and **Time** into datetime format for analysis.
- Removed **Invoice ID** (irrelevant for analysis).
- Dropped **Gross Margin Percentage**, as it has only one unique value.

### 2. Exploratory Data Analysis (EDA)
- Generated **summary statistics** for numerical attributes.
- Created **boxplots** to visualize distributions and identify outliers.
- Conducted **histograms** to analyze purchasing trends based on Customer Type and Product Line.
- Examined **correlations** between key variables.

### 3. Feature Engineering
- One-hot encoded **Branch, Payment Method, and Product Line** for modeling.
- Extracted **year, month, day, hour, and minute** from the Date & Time columns.
- Scaled numerical features using **StandardScaler**.

## Model Training & Segmentation
### 1. Customer Segmentation Using K-Means Clustering
- Used the **Elbow Method** to determine optimal clusters.
- Applied **Principal Component Analysis (PCA)** for dimensionality reduction.
- Trained K-Means on normalized data, yielding **2 customer groups**:
  - **Cluster 0** – Lower spending customers with smaller transaction amounts.
  - **Cluster 1** – Higher spending customers who purchase more products.

### 2. Hierarchical Clustering
- Implemented **Agglomerative Clustering** to compare segmentations.
- Generated **dendrograms** to visualize hierarchical customer grouping.
- Found **two distinct customer groups** aligning with K-Means clustering results.

## Key Findings
- **Higher spending customers** tend to buy products in bulk with higher unit prices.
- **Payment method preferences** vary across clusters—members use **Ewallet more frequently**, while normal customers rely on **Cash**.
- **Branch distributions** show regional differences in customer purchasing behavior.
- **Customer satisfaction ratings** correlate with higher transaction values.

## Conclusion
This analysis helps supermarkets understand **customer segmentation**, optimize marketing strategies, and improve inventory planning. Future work could explore **predictive modeling** to enhance customer retention and personalized promotions.

---
