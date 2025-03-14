# DSA210-Project

This project explores how weather conditions influence the sales trends of different product categories in coffee shops. The dataset contains transaction data from three coffee shop brands operating in different areas of New York City. The sales data is categorized into:
* Coffee (Drip coffee, espresso, brewed coffee)
* Tea (Chai, herbal, and specialty teas)
* Bakery (Pastries, muffins, sandwiches)
* Drinking Chocolate  (Hot chocolate and other cocoa-based drinks)

By combining this transactional data with historical weather records, we aim to uncover whether daily temperature, rainfall, or seasonal changes impact customer preferences for different product types. The insights generated could help coffee shop owners adjust their menu offerings, pricing strategies, and marketing campaigns based on expected weather patterns.

Motivation:

Consumer preferences for coffee shop products vary based on multiple factors, including location, pricing, and seasonality. However, one key external factor that could influence purchasing decisions is weather conditions. This project aims to analyze whether temperature, rainfall, and other weather factors affect the sales of different coffee shop product categories—such as coffee, tea, bakery items, and drinking chocolate—across different locations in New York City.


Objectives:

* Analyze the correlation between weather conditions and sales trends for each product category.
* Identify seasonal preferences—for example, does tea sell more in winter while iced coffee dominates in summer?
* Compare sales performance across different store locations under varying weather conditions.
* Provide data-driven recommendations to help coffee shop businesses optimize inventory and marketing strategies.

Hypothesis Testing:

* Null Hypothesis (H0): Weather does not affect the type of selling (product category) in coffee shops.
* Alternative Hypothesis (H1): Weather does affect the type of selling (product category) in coffee shops.

We will perform statistical tests (e.g., Chi-square tests) to determine if weather conditions significantly influence sales trends for the different product categories offered by the coffee shops.

Machine Learning (Classification):

For the ML part, this project will involve multiclass classification to predict the product category (Coffee, Tea, Bakery, or Drinking Chocolate) based on weather and other relevant factors. This classification model can help us identify the most likely product category to sell based on specific weather conditions and other inputs.

ML Steps are: 

* Data Preprocessing: Clean the data, handle missing values, encode categorical variables, and normalize numerical features if necessary.
* Feature Engineering: Incorporate weather data, time of year, exzplanation of sold products, location and other inputs as features to train the model.
* Model Selection: Try classification algorithms such as Random Forest and Decision Trees
* Model Evaluation: Evaluate models using metrics like accuracy, confusion matrix and cross-validation.

Data:

* Coffee Shop Sales Data: Sourced from Kaggle, containing sales records from three different coffee shop brands in New York City.
* Coffee Shop data Kaggle link: https://www.kaggle.com/datasets/ahmedabbas757/coffee-sales
* Weather Data: Will be collected later from official weather sources such as the Bureau of Meteorology (BoM), Weather Underground, or Kaggle weather datasets.
