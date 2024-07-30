# TECH_analysis

## Table of contents

1. [Project overview](#Project-overview)
2. [Data sources](#Data-sources)
3. [Tools used](#Tools-used)
4. [Data cleaning / preparation](#Data-cleaning-/-preparation)
5. [Exploratory Data Analysis](#Exploratory-Data-Analysis)
6. [Data analysis](#Data-analysis)
7. [Results / Findings](#Results-/-Findings)
8. [Recommendations](#Recommendations)
9. [References](#References)

### Project overview

This data analysis project aims to provide insights into weather data (2012), Uber data (2016) & Inventory data. By analyzing various aspects of the weather data, Uber data & Inventory seperately, we seek to identify trends, make data-driven recommendations, and gain a deeper understanding of these factors.

### Data sources

The primary dataset used for this analysis are
 - Weather data: [kaggle weather](https://www.kaggle.com/datasets/bhanupratapbiswas/weather-data)
 - Uber data: [kaggle Uber](https://www.kaggle.com/datasets/bhanupratapbiswas/uber-data-analysis)
 - Inventory data: [kaggle inventory](https://www.kaggle.com/datasets/bhanupratapbiswas/inventory-analysis-case-study/data)


### Tools used

- EXCEL - For data cleaning. [Download here](https//:microsoft.com)
- SQL - For data analysing.
- Python - Exploratory data analysis.

### Data cleaning / preparation

In the initial data preparation phase, we performed the following tasks:
1. Data loading and inspection.
2. Handling missing values.
3. Data cleaning and formatting.

### Exploratory Data Analysis

EDA involves exploring the datas to answer key questions, such as:

1. **Weather data**
- What is the overall temperature trend?
- How often does it rains?
- What is the wind speed trend?
2. **Uber data (2016)**
- what is the most opted trip category and purpose?
- what are top 10 routes?
- which is the most opted route?
- which is the longest travelled route?
- which month has the most number of trips?
3. **Inventory data**


### Data analysis

Include some interesting codes or features worked with

**Weather data analysis**

- Temperature trend analysis


``` SQL
SELECT DATE(Date_Time)AS date,ROUND(AVG(Temp_C ),0)AS temp_in_degree_celcius
FROM `weather_datas.weather`
GROUP BY date
ORDER BY date ASC;
```

- precipitation pattern analysis

 ```SQL
SELECT weather,COUNT (Weather)AS weather_count
FROM `weather_datas.weather`
GROUP BY Weather
HAVING COUNT (Weather) >100
ORDER BY weather_count DESC;
```

- Windspeed analysis
  
```SQL
SELECT DATE(Date_Time)AS date,ROUND (AVG (Wind_Speed_km_h),0)AS windspeed_km_hr, ROUND(AVG(temp_C),0)AS temp_in_degree_celcius
FROM `weather_datas.weather`
GROUP BY date
ORDER BY date ASC;
```

**Uber data analysis**

```SQL
SELECT START_MONTH AS MONTH,ROUND (SUM(SUM_of_MILES),0)AS MILES_COVERED
FROM `braided-topic-402311.Babynames.uberr` 
GROUP BY START_MONTH
ORDER BY START_MONTH ASC;
```

```SQL
SELECT month,SUM(count)AS count
FROM `braided-topic-402311.Babynames.ube`
GROUP BY month;
```

**Inventory data analysis**

### Results / Findings

**Weather Data** analysis results are summarized as follows:
1. Coldest month is January and Hottest month is July.
2. 3.7% of the days in 2012 are rainy.
3. Average windspeed of 15 Km/hr with a maximum value of 42km/hr is observed.
   
**Uber Data** analysis results are summarized as follows:
1. The most opted trip category and purpose are Business and Meeting.
2. The most opted route is Morrisville - Cary.
3. The longest travelled route is Latta - Jacksonville.
4. December has the most number of trips.


### References

1. [kaggle.com](https//:kaggle.com)
   
