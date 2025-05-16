# Predicting Surface Pressure Using Time Series Techniques

## Table of Contents
- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Tools](#tools)
- [Data Cleaning/Preparation](#data-cleaningpreparation)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Data Analysis](#data-analysis)
- [Results/Findings](#resultsfindings)
- [Recommendations](#recommendations)
- [Limitations](#limitations)
- [References](#references)
  
### Project Overview
---
The UK Meteorological Office require a model to predict surface pressure of North Atlantic Ocean. To make such a prediction, time series techniques was implemented. Surface pressure of the North Atlantic Ocean has been collected over time from 1st May, 2018 to 31st May, 2018, for three hour interval each day, making it a time series data. Accurate surface pressure forecast contribute to more reliable weather forecasts. The aim of this project was to predict the surface pressure.  

![rmse1](https://github.com/user-attachments/assets/c51a8c78-e156-4d69-8dee-4239d156f727)


### Data Sources
WRF(Weather Research and Forecasting) Data: The dataset was provided as part of ongoing studies. 

### Tools
- RStudio – Data cleaning and analysis  
  [Download here](https://posit.co/products/open-source/rstudio/)

- Power BI – Report creation and data visualization  
  [Download here](https://www.microsoft.com/en-us/download/details.aspx?id=58494)

- Excel – Data cleaning, transformation, and visualization  
  [Download here](https://www.microsoft.com/en-us/microsoft-365/excel)

#### Data Cleaning/Preparation
In the initial data preparation please, I performed the following tasks:
1.	Data loading and inspection.
2.	Handling missing values.
3.	Data cleaning and formatting.
4. 	Building the model
5.	Choosing the best model for prediction
   
### Exploratory Data Analysis
EDA involved exploring the WRF data to answer key questions, such as: 
-	What machine learning models can be performed using the provided dataset 
-	What is the best model among the other machine learning models  

  ![tsplot2](https://github.com/user-attachments/assets/24894701-8b7e-4b30-a124-1f0837d06c16)


### Data Analysis 
```r 
# Preprocess dataset for time series analysis
data <- data %>%
  select(DATETIME, PSFC)

# Time series plot before performing lag
ggplot(data, aes(x = DATETIME, y = PSFC)) +
  geom_line(color = "blue") +
  labs(title = "Surface pressure Over Time",
       x = "Date and Time",
       y = "Surface pressure") +
  theme_minimal()

# Create a variable to represent time
data <- data %>%
  mutate(TIME = as.numeric(difftime(DATETIME, min(DATETIME), units = "hours")))
```

### Results/Findings
The analysis results are summarized as follows:
1.	The Auto Regressive Integrated Moving Average (ARIMA) model, a statistical time series forecasting technique, was implemented. Additionally, machine learning algorithms such as Decision Tree Regression, Support Vector Regression, Random Forest, and Linear Regression were used to build predictive models. The model with the lowest Root Mean Square Error (RMSE) was selected as the best for predicting surface pressure in the North Atlantic Ocean.
2.	ARIMA had the smallest RMSE of 85.91735 Pa.

### Recommendations
I recommend adopting ARIMA as the predictive model for housing prices, based on the performance illustrated in the bar chart below.

![rmse](https://github.com/user-attachments/assets/c3077595-db71-4c6a-9788-622258de2e67)

### Limitations
The dataset was provided as part of ongoing studies, so its authenticity cannot be fully guaranteed.

### References
1.	Auhl, M. (2021) What is an ARIMA Model? [Online] Available from: https://towardsdatascience.com/what-is-an-arima-model-9e200f06f9eb. [Accessed 10 May 2024].
2.	Deng, H. (2021) An Introduction to Random Forest [Online] Available from: https://towardsdatascience.com/random-forest-3a55c3aca46d. [Accessed 10 May 2024].
3.	DSA. (2023) Univariate Time Series Analysis and Forecasting [Online] Available from: https://www.geeksforgeeks.org/univariate-time-series-analysis-and-forecasting/. [Accessed 10 May 2024].
4.	IBM. (2024) What is a Decision Tree? [Online] Available from: https://www.ibm.com/topics/decision-trees. [Accessed 10 May 2024].
5.	Itl. (2024) Univariate Time Series Models [Online] Available from: https://itl.nist.gov/div898/handbook/pmc/section4/pmc44.htm. [Accessed 10 May 2024].
6.	Kibet, M. (2023) A Guide to Regression Analysis with Time Series Data [Online] Available from: https://www.influxdata.com/blog/guide-regression-analysis-time-series-data/. [Accessed 10 May 2024].
7.	Metoffice. (2024) Surface Pressure Charts [Online] Available from: https://www.metoffice.gov.uk/weather/maps-and-charts/surface-pressure. [Accessed 10 May 2024].
8.	Polamuri, S. (2023) What Is Univariate Time Series Analysis [Online] Available from: https://dataaspirant.com/univariate-time-series-analysis/. [Accessed 10 May 2024].
9.	Psu. (2024) Overview of Time Series Characteristics [Online] Available from: https://online.stat.psu.edu/stat510/lesson/1/1.1. [Accessed 10 May 2024].
10.	Sethi, A. (2020) Support Vector Regression Tutorial for Machine Learning [Online] Available from: https://www.analyticsvidhya.com/blog/2020/03/support-vector-regression-tutorial-for-machine-learning/. [Accessed 10 May 2024].
11.	Wwa. (2024) Who we are [Online] Available from: https://www.metoffice.gov.uk/about-us/who-we-are. [Accessed 10 May 2024].


## 📬 Contact
Feel free to reach out!  
📧 Email: [oduroprince08@gmail.com](mailto:oduroprince08@gmail.com) &nbsp;|&nbsp; 🔗 LinkedIn: [linkedin.com/in/oduroprince24](https://linkedin.com/in/oduroprince24)


🚀
📊
📈
🧠

Thanks for visiting! 😄
