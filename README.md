# Prophet Challenge

## Overview
As a growth analyst at Mercado Libre the task is to analyze the company's user data and stock price to determine if it can be used to sucessfully trade stock.

## Description
Mercado Libre is a popular e-commerce site in Latin America. The company would like to understand if there is a correlation or relationship between search traffic and the stock price. This code seeks to identify and understand any unusual and seasonal Google search patterns and then compare to stock price patterns. Additionally, Prophet is utilized to create a time series model.

## Analysis and Findings

### Step 1: Find Unusual Patterns in Hourly Google Search Traffic
In order to identify any unusual patterns in hourly Google search traffic, the search traffiv csv file is read into a DataFrame and then filtered for the month of May 2020. In May 2020 Mercado Libre released its quarterly financial results and it is important to understand if it had any impact to search traffic. Total search traffic in May 2020 is compared to median search traffic to understand the impact. May 2020 search traffic was higher than the median indicating an impact of the quarterly financial results release.

### Step 2: Mine the Search Traffic Data for Seasonality
Marketing has identified value in looking deeper at the search traffic to identify the best hour of day, day of week, and week of year to focus marketing efforts. This is accomplished by creating graphs utilizing groupby and the index datetime to understand volumes. Search volume is highest at midnight and on Tuesdays. Weekly volume did not show a pattern.

### Step 3: Relate the Search Traffic to Stock Price Patterns
In this step, the hourly stock price is read into a DataFrame and visualized in a graph. Then the stock price DataFrame and the Google search volume DataFrame are concatenated together and graphed together utilizing subplots. Additional columns are added to the concatenated DataFrame to understand stock volatility and if lagging the stock price impact the patterns and trends. A correlation grid is put together and shows very little correlation between the new columns.

### Step 4: Create a Time Series Model with Prophet
A time series model focused on Google search volume is put together by first putting the DataFrame in the format needed for Prophet. The model is created and fit into a new DataFrame and then populated with predictions. The results show similar patterns in the hourly Google search traffic - midnight and Tuesday the highest volume times and days, respectively.