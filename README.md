Customer Purchase Patterns Analysis
Problem Statement

An online retail store is trying to understand the various customer purchase patterns to gain insights that could benefit their business strategies. This project uses K-Means clustering to analyze the customer purchasing history and segment the customers based on their purchasing behavior.
Dataset Information

The dataset online_retail.csv contains 541,909 rows and 8 columns:

    Invoice: Invoice number
    StockCode: Product ID
    Description: Product Description
    Quantity: Quantity of the product
    InvoiceDate: Date of the invoice
    Price: Price of the product per unit
    CustomerID: Customer ID
    Country: Region of Purchase

Objectives

    Derive useful insights from the customer purchasing history that can provide an added advantage to the online retailer.
    Segment the customers based on their purchasing behavior using K-Means clustering.

Installation Instructions
Python Installation

To install Python, follow the instructions on the official Python website: Install Python.
Required Libraries

Ensure you have the following libraries installed. You can install them using pip:

sh

pip install datetime matplotlib numpy pandas plotly seaborn scikit-learn yellowbrick scipy

Additional Resources

    Installing Python Packages using pip
    Introduction to Python

Usage

Clone the repository and navigate to the project directory:

sh

git clone <repository_url>
cd <repository_directory>

Run the script to perform the analysis:

sh

python customer_segmentation.py

Insights and Analysis

The script performs the following steps:

    Data Preprocessing: Cleans the data and handles missing values.
    Feature Engineering: Creates new features to aid in clustering.
    Exploratory Data Analysis (EDA): Visualizes data distributions and relationships.
    Customer Segmentation: Uses K-Means clustering to segment customers based on their purchasing behavior.
    Cluster Evaluation: Evaluates the clustering performance using metrics like Calinski-Harabasz Score, Davies-Bouldin Score, and Silhouette Score.

Conclusion

This project provides a comprehensive analysis of customer purchasing patterns and segments customers effectively to help the online retail store make data-driven decisions.
Contact

For any questions or suggestions, please contact:

Tharakh George Chacko
Email: [your_email@example.com]
LinkedIn: [your_linkedin_profile]

This README file serves as a guide to understanding the project's objectives, installation requirements, and usage instructions. By following the steps outlined, users can replicate the analysis and gain insights into customer purchasing patterns.
