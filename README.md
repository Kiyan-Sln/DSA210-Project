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
* Identify short-term seasonal trends—for example, do certain products like hot drinks (tea, coffee) see higher sales on colder days, while iced beverages or bakery items peak on warmer days?
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
* Model Evaluation and Hyperparameter Tuning: Evaluate models using metrics like accuracy, confusion matrix, and cross-validation, while optimizing performance through hyperparameter tuning techniques such as Grid Search.

Data:

* Coffee Shop Sales Data: Sourced from Kaggle, containing sales records from three different coffee shop brands in New York City.
* Coffee Shop data Kaggle link: https://www.kaggle.com/datasets/ahmedabbas757/coffee-sales
* Weather Data: Will be collected later from official weather sources such as the Bureau of Meteorology (BoM), Weather Underground, VisualCrossing or Kaggle weather datasets to enrich the data.


Exploratory Data Analysis Methods:

1) To enrich the coffee shop sales data, I integrated hourly weather data for New York City from VisualCrossing.com, covering the first six months of 2023—which matches the time span of the coffee shop dataset.

2) Data Merging Strategy:
Since the coffee sales data includes timestamps down to the minute, and the weather dataset is hourly, I matched weather data to each transaction based on the hour. That is, for every sale between 7:00–7:59 AM, the weather conditions recorded at 7:00 AM were assigned.

3) Feature Selection & Engineering:
To focus the analysis on weather impact on product sales, certain columns—like unit_price—were dropped, as price is not useful when attempting to predict product category based on weather.
In addition to the raw columns, I created new derived features by combining existing ones. For example:
* humidity_prec_percentage: A combined feature representing the average of humidity and precipitation probability.
* cloud_rain_percentage: An engineered metric showing the relationship between cloud cover and chance of rain.
This kind of feature engineering allows us to capture more nuanced patterns than the raw data alone.

4) Handling Missing Values:
The only column with missing data was preciptype (rain, snow, etc.). Instead of dropping those rows, I filled NaN with 'None', indicating that there was no precipitation during those periods.

5) Visualizations:
Several visualizations were used to uncover insights from the data:
* Most frequently sold product types.
* Distribution of product categories.
* Peak sales times by hour.
* Temperature distribution across product categories.
* Correlation matrix of weather features.
* Differences between actual temperature and "feels like" temperature.
These helped shape our hypotheses and understand the context behind the sales trends.

Hypothesis Testing
Hypotheses:
* Null Hypothesis (H₀): Weather variables do not affect product_category (i.e., their means are the same across categories).
* Alternative Hypothesis (H₁): At least one weather variable’s mean differs between product categories (weather does affect product_category).

Method: One-Way ANOVA->
We performed one-way ANOVA tests for each weather-related column, comparing the average values across different product categories (e.g., coffee vs. tea). This allows us to detect if, for example, coffee tends to be sold more often in colder or cloudier conditions than tea.

Results Summary:
Weather features that had p-values below 0.05 are considered statistically significant, meaning they likely affect the product category:
snowdepth, precipprob, cloud_rain_percentage, cloudcover, solarradiation, solarenergy, visibility, humidity_prec_percentage, precip, windgust, temp, feelslike, humidity

On the other hand, variables like snow, dew, and windspeed had p-values above 0.05, so we fail to reject the null hypothesis for them—no significant evidence that they affect product category.
