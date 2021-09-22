# Explore Ford GoBike Dataset 
## by Ahmed M. Hassan

## Introduction

This project is a part of Udacity Data Analyst Nano-Degree. It was required in this project to perform an exploratory data analysis for a given dataset using python visualization libraries, e.g. `pandas` and `seaborn`. Then, it was required to provide at least two explanatory visuals of the ingsights found during the exploratory data analysis step.

## Dataset

The dataset represents entries of 175147 ride for GoBike bike sharing company in the great San Francisco Bay area. Nearly, all the rides were recorded in the same month (Feburary, 2019). The city has 329 unique stations with 4646 unique bikes. The dataset has the duration, start station, end station, bike id, user type, user age, user gender for every ride. 

## Project Walkthrough

- The data was provided in the form of a CSV flat file. The data was loaded into a dataframe using `pandas`
- The dataset was explored manually and programmatically to located data quality and tidiness issues. The summary of noted issues is provided
    - `start_time` is a string data type not a datetime object
    - `end_time` is a string data type not a datetime object
    - `start_station_id` has null values
    - `start_station_name` has null values
    - `end_station_id` has null values
    - `end_station_name` has null values
    - `member_birth_year` has null values
    - `member_gender` has null values
    - `start_station_id` should be a string
    - `end_station_id` should be a string
    - `bike_id` should be a string
- Then, a data cleaning process is performed to remove the above noted issues
    - The null values in the `member_gender` and `member_birth_year` will be dropped
    - The null entries in start and end station will be filled with the id and name of nearest station based on the latitude and   longtiude of station `303`
    - Correct the data types as per the above cell - After that, the main parameter to be explored was determined to be the trip duration in second and the number of trips
- The indepemdent varaibles considered were
    - `user_type`
    - `member_gender`
    - Trip time of the day (using `start_time` column)
    - Trip day of the week (using `start_time` column)
    - Round trip or not (if the start station is the same as end station)
    - Trip distance (using start and end station latitude and longitude)
    - Age (using `member_birth_day`)
- The last five features are new variables introduced  by feature engineering to provide a better understanding of the factors affecting the dependent variables, their distribution in the database and their inter-correlation.
- After that, the defined variables were explored using univariate visualization. The numerical variables were explored as histograms, while other categorical variables were explored as bar charts
- The next exploratory analysis was performed in form of bivariate plots where the dependent variable `duration_sec` will be investigated will all other independent variables. The relation with numerical variables will be investigated will scatter plots where a violin plot will be used with categorical variables.
- Multivariate visualization were used to investigate the relationship between the distribution of average trip duration and distance between start and end stations with week day and day time will be investigated. The `seaborn` heatmap was used. A function to plot the required heatmap was created to allow investigating the effect of user type and gender on this distribution
 

