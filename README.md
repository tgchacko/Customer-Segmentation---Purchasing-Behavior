# Customer Segmentation Based on Purchasing Behavior

## Table of Contents

[Project Overview](#project-overview)

[Data Sources](#data-sources)

[Data Description](#data-description)

[Tools](#tools)

[EDA Steps](#eda-steps)

[Data Preprocessing Steps and Inspiration](#data-preprocessing-steps-and-inspiration)

[Graphs/Visualizations](#graphs-visualizations)

[Choosing the Algorithm for the Project](#choosing-the-algorithm-for-the-best-project)

[Assumptions](#assumptions)

[Model Evaluation Metrics](#model-evaluation-metrics)

[Results](#results)

[Recommendations](#recommendations)

[Limitations](#limitations)

[Future Possibilities of the Project](#future-possibilities-of-the-project)

[References](#references)

### Project Overview

The objective of this project is to analyze customer purchasing behavior to enhance strategic decision-making and operational efficiency for an online retail store. By segmenting customers based on their purchasing patterns, the project aims to provide insights for targeted marketing, personalized customer interactions, and optimized business strategies.

### Data Sources
The primary dataset used for this analysis is the OnlineRetail.csv file, containing transactional data from an online retail store.

[OnlineRetail.csv Dataset](https://www.kaggle.com/code/kikomiko/online-retail-data-analysis-k-means/input)

### Data Description

The dataset OnlineRetail.csv consists of 5,41,909 entries and includes the following columns:
1) **InvoiceNo**: Unique identifier for each transaction.
2) **StockCode**: Product identifier.
3) **Description**: Name or description of the product.
4) **Quantity**: Number of products purchased per transaction.
5) **InvoiceDate**: Date and time of the transaction.
6) **UnitPrice**: Price per unit of the product.
7) **CustomerID**: Unique identifier for each customer.
8) **Country**: Country or region where the customer resides.

![Data Description1](https://github.com/tgchacko/Customer-Segmentation---Purchasing-Behavior/assets/169921893/7d0897ad-d320-4250-9a0f-67d0975b3c2c)

![Data Description2](https://github.com/tgchacko/Customer-Segmentation---Purchasing-Behavior/assets/169921893/9a8f2e39-4e56-4f4a-836c-4524c0770e95)

### Tools

**Python: Data cleaning and analysis**
        [Download Python](https://www.python.org/downloads/)
    
**Jupyter Notebook: For interactive data analysis and visualization**
        [Install Jupyter](https://jupyter.org/install)

#### Libraries

Below are the links for details and commands (if required) to install the necessary Python packages:
- **pandas**: Go to [Pandas Installation](https://pypi.org/project/pandas/) or use command: `pip install pandas`
- **numpy**: Go to [NumPy Installation](https://pypi.org/project/numpy/) or use command: `pip install numpy`
- **matplotlib**: Go to [Matplotlib Installation](https://pypi.org/project/matplotlib/) or use command: `pip install matplotlib`
- **seaborn**: Go to [Seaborn Installation](https://pypi.org/project/seaborn/) or use command: `pip install seaborn`
- **scikit-learn**: Go to [Scikit-Learn Installation](https://pypi.org/project/scikit-learn/) or use command: `pip install scikit-learn`
- **yellowbrick**: Go to [Yellowbrick Installation](https://pypi.org/project/yellowbrick/) or use command: pip install yellowbrick`

### EDA Steps

Exploratory Data Analysis (EDA) involved exploring the transactional data to answer key questions, such as:

1) What are the overall sales trends?
2) How do sales vary by country and product?
3) What are the peak sales periods?

### Data Preprocessing Steps and Inspiration
1. ### Data Cleaning

a. **Handling Missing Values**: Removed records with missing CustomerID or Description.
b. **Removing Duplicates**: Eliminated duplicate entries to ensure unique transactions.
c. **Standardizing Text Data**: Converted product descriptions to lowercase and removed whitespace.
d. **Removing Outliers**: Used the Interquartile Range (IQR) method to identify and remove outliers in fields like Quantity, UnitPrice, and TotalPrice.

2. ### Data Transformation

a. **Standardization of Product Descriptions and Stock Codes**: Mapped unique stock codes and descriptions to ensure consistency.
b. **Feature Engineering**: Created a TotalPrice feature by multiplying Quantity by UnitPrice.

3. ### Date Handling

a. Invoice Date Conversion: Converted InvoiceDate to datetime format.
b. Filtering Data by Date: Excluded transactions from incomplete periods for accurate analysis.


### Graphs/Visualizations

![Total Monthly Sales Trends](https://github.com/tgchacko/Customer-Segmentation---Purchasing-Behavior/assets/169921893/f5873828-3e20-4554-aaa0-08a7b85ae50b)

![Countrywise Average Values](https://github.com/tgchacko/Customer-Segmentation---Purchasing-Behavior/assets/169921893/503c2e5d-deea-4d49-ab31-a98fd8031190)

![Average Cart Value by Country](https://github.com/tgchacko/Customer-Segmentation---Purchasing-Behavior/assets/169921893/3e197004-31eb-4ef6-acad-4df4b962a94d)

### Top 5 Countries By Sales

![Top 5 countries by Sales](https://github.com/tgchacko/Customer-Segmentation---Purchasing-Behavior/assets/169921893/62127efb-0e29-4fff-9fc0-756089c3abaf)

![Monthly Sales Trends - UK](https://github.com/tgchacko/Customer-Segmentation---Purchasing-Behavior/assets/169921893/f49bbc08-dfcc-44d5-80c4-adde87bddac2)

![Monthly Sales Trends for Countries other than UK](https://github.com/tgchacko/Customer-Segmentation---Purchasing-Behavior/assets/169921893/6a1a45e5-9dbd-4365-8671-4f0122ee76c6)

![Total Sales For Each Country Except UK](https://github.com/tgchacko/Customer-Segmentation---Purchasing-Behavior/assets/169921893/89b609e4-3904-4cd6-9f0c-2ee617d70396)

![Customers per Month](https://github.com/tgchacko/Customer-Segmentation---Purchasing-Behavior/assets/169921893/d48aedd8-6054-445c-a7ee-e7767475631f)

![Number of Customers by Country](https://github.com/tgchacko/Customer-Segmentation---Purchasing-Behavior/assets/169921893/3ad45b77-b1b5-4222-a73b-04880221bd76)

![Number of Transactions per Hour](https://github.com/tgchacko/Customer-Segmentation---Purchasing-Behavior/assets/169921893/d083155f-0f8f-4fd5-bcb6-053ac955c3d6)

![Number of Transactions by Time of Day](https://github.com/tgchacko/Customer-Segmentation---Purchasing-Behavior/assets/169921893/e6ec9d3d-9e67-4bfd-bf2f-75b664f84672)

### Reasons for Choosing the Algorithm for the Project
#### K-Means Clustering

1) **Suitability for Customer Segmentation**:  
a. **Simplicity and Efficiency**: Effective for large datasets with numerical attributes.
b. **Scalability**: Handles extensive transactional data efficiently.

2) **Data Characteristics**: 
a. **Numerical Data Handling**: Ideal for metrics like TotalPrice, Frequency, and Recency.
b. **Standardization Ready**: Prepared data for optimal performance.

3) **Analytical Goals**:
a. **Customer Insights**: Identifies actionable customer segments.
b. **RFM Analysis**: Utilizes Recency, Frequency, and Monetary metrics for segmentation.

### Assumptions

1) **Data Distribution and Scale**: Assumes normalized numerical data with equal variance across features.
2) **Cluster Assumptions**: Assumes spherical clusters with similar density.
3) **Independence of Observations**: Treats each transaction or customer record independently.
4) **Algorithm-Specific Assumptions**: Relies on multiple initializations for robust clustering.

### Model Evaluation Metrics

1) **Silhouette Score**: Assesses cluster separation and cohesion.
2) **Davies-Bouldin Index**: Measures average similarity between clusters.
3) **Calinski-Harabasz Index**: Evaluates variance ratio between clusters.

### Results

**Customer Segment Distribution Analysis based on RFM**:

![RFM Customer Segment Distribution](https://github.com/tgchacko/Customer-Segmentation---Purchasing-Behavior/assets/169921893/c660ea83-d7fa-4718-b1f2-73dd1808e3e4)

**Notable Segments**:

1) 24% in the **Dormant** segment.
2) 14.90% in the **Top Customers** segment.
3) 18.20% in the **Faithful Customers** segment.

#### K-means Clustering Results:

1) **Silhouette Score**: 0.565 (indicating moderate cluster separation).
2) **Davies-Bouldin Index**: 0.639 (indicating good cluster distinction).
3)**Calinski-Harabasz Index**: 3333.416 (indicating well-defined clusters).

![Distortion Score Elbow Method for KMeans Clustering](https://github.com/tgchacko/Customer-Segmentation---Purchasing-Behavior/assets/169921893/f2271ffa-700f-43b5-a7ba-1b332e869bdb)

![Silhouette Score for Different Numbers of Clusters](https://github.com/tgchacko/Customer-Segmentation---Purchasing-Behavior/assets/169921893/a155de08-0c34-4358-a642-c6a814a79fe8)

![3D View of Customer Clusters](https://github.com/tgchacko/Customer-Segmentation---Purchasing-Behavior/assets/169921893/1fd363c8-dbf2-4b2f-b90f-feaa310459d3)

![KMeans Customer Clusters Distribution](https://github.com/tgchacko/Customer-Segmentation---Purchasing-Behavior/assets/169921893/1e719954-99f4-4a6b-9c11-6a40cb9f493e)

### Recommendations

1) **Targeted Marketing**: Use segmentation insights to tailor marketing campaigns.
2) **Inventory Management**: Optimize inventory based on purchasing trends.
3) **Customer Engagement**: Enhance engagement strategies for different segments.

### Limitations

1) **Data Quality**: Potential inaccuracies due to missing or incorrect data.
2) **Cluster Assumptions**: Real-world data may not adhere to spherical clusters.
3) **Model Sensitivity**: Initial centroid placement can affect clustering results.

### Future Possibilities of the Project

1) **Integration with Predictive Analytics**: Forecast future purchasing behaviors.
2) **Dynamic Clustering**: Implement real-time segmentation.
3) **Enhanced Personalization**: Develop personalized engagement strategies.

### References

1) James, Gareth, et al. "An Introduction to Statistical Learning." Springer Texts in Statistics, 2013.
2) Scikit-Learn Documentation: KMeans, Silhouette Score, Davies-Bouldin Index, Calinski-Harabasz Index.
3) "Python Data Science Handbook" by Jake VanderPlas; O’Reilly Media, 2016.
