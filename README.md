--------------------------
📊 Daily Sales Data Analysis: My First Data Science Project

Introduction

This project is an introductory data analysis workflow using Python. The goal was to take a raw dataset of daily sales and identify meaningful trends through data cleaning, analysis, and visualization.
--------------------------
Tools and Technologies 🛠️

Python: The programming language used for the entire analysis.
Pandas: Used for all data manipulation, including loading the data and performing aggregations.
Matplotlib: Employed to create the final visualization of the sales trends.
Jupyter Notebook: The environment where the code was written and executed, combining code, text, and output into a single document.
--------------------------
Data Analysis and Visualization

To prepare the data, I first converted the datum column to a datetime format. Next, I grouped the data by month to calculate the total sales for each of the eight product categories. A line plot was then generated to visualize these monthly trends.

import pandas as pd
import matplotlib.pyplot as plt

# Load and prepare the data
df = pd.read_csv('salesdaily.csv')
df['datum'] = pd.to_datetime(df['datum'])
df['Month'] = df['datum'].dt.strftime('%B')

# Group data by month and sum sales
monthly_sales = df.groupby('Month')[['M01AB', 'M01AE', 'N02BA', 'N02BE', 'N05B', 'N05C', 'R03', 'R06']].sum()

# Create and save the plot
plt.figure(figsize=(12,6))
monthly_sales.plot(kind='line')
plt.title('Monthly Sales Trend for Product Category', fontsize=16)
plt.xlabel("Month", fontsize=12)
plt.ylabel("Total Sales", fontsize=12)
plt.xticks(rotation=45)
plt.grid(True)
plt.tight_layout()
plt.savefig('monthly_sales_trend.png')
plt.show()
---------------------------
Interactive Dashboard

To take this analysis one step further, I created a professional, interactive dashboard using Tableau Public. You can explore the data and see the trends for yourself by clicking the link below.

View the Live Dashboard on Tableau Public
---------------------------

Key Findings 📈

The analysis revealed distinct seasonal patterns in sales across all product categories. This suggests that factors such as time of year, holidays, or specific marketing efforts likely influence the sales of these products.

Visualizations

The chart below provides a clear and immediate understanding of the sales trends.
---------------------------
Next Steps 🚀

I plan to expand on this project by:

Conducting a more detailed analysis to identify and confirm specific seasonal cycles.
Creating an interactive dashboard with tools like Power BI or Tableau.
Applying machine learning models for sales forecasting to predict future trends.
