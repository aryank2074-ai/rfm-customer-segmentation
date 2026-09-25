# rfm-customer-segmentation
📌 Overview

This project performs RFM (Recency, Frequency, Monetary) analysis on an online retail transaction dataset to segment customers based on their purchasing behavior. Using K-Means clustering, customers are grouped into distinct segments to help the business identify its most valuable customers, potential customers, and least profitable ones — enabling targeted marketing and retention strategies.

📊 Dataset

The dataset (Online Retail.xlsx) contains e-commerce transaction records including:

InvoiceNo, InvoiceDate – transaction identifiers and timestamps
CustomerID – unique customer identifier
Quantity, UnitPrice – purchase details used to compute total spend
🛠️ Project Workflow
1. Data Cleaning
Parsed InvoiceDate into a proper datetime format
Removed records with missing CustomerID
Removed transactions with negative Quantity (returns/cancellations)
Created a Total_Price feature (Quantity × UnitPrice)
2. RFM Feature Engineering

For each customer, calculated:

Recency (R): Days since the customer's last purchase (relative to a fixed reference date)
Frequency (F): Total number of transactions
Monetary Value (M): Total amount spent
3. Exploratory Analysis
Identified the top 10 customers ranked by frequency and monetary value
Visualized customer similarity using a cluster heatmap (clustermap)
4. Customer Segmentation
Scaled RFM features using StandardScaler
Applied K-Means clustering to group customers into segments
Validated the optimal number of clusters (k=3) using the Elbow Method
5. Segment Profiling

Identified three customer segments based on cluster-wise RFM averages:

Segment	Characteristics	Business Interpretation
Cluster 0	High recency, low frequency, low monetary value	Least profitable / at-risk customers
Cluster 1	Decent frequency and monetary value	Potential customers — worth nurturing
Cluster 2	Low recency, high frequency, high monetary value	Most profitable / loyal customers
🧰 Tech Stack
Python
Pandas, NumPy – data manipulation
Matplotlib, Seaborn – visualization
Scikit-learn – StandardScaler, KMeans clustering
🚀 How to Run
Clone the repository
Install dependencies: pip install pandas numpy seaborn matplotlib scikit-learn openpyxl
Place Online Retail.xlsx in the project directory
Run the notebook RFM_model.ipynb
📈 Key Insights
Customers naturally group into three meaningful behavioral segments
The Elbow Method confirmed k=3 as the optimal cluster count
RFM segmentation provides a simple, interpretable framework to prioritize marketing spend toward high-value and potential-value customers
