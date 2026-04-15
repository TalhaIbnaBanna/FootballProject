 # Business Analytics Project on Football Dataset ⚽
Final project for Business Analytics 

## Overview
This repository contains a comprehensive data analytics and machine learning project based on historical club football match data spanning the past 25 years (2000-2025). The project encompasses data cleaning, feature engineering, exploratory data analysis (EDA), and the implementation of multiple predictive machine learning models to forecast match outcomes.

## Dataset
The dataset used in this project includes detailed match statistics across various divisions, encompassing ELO ratings, match events (shots, corners, fouls, cards), team forms, and betting odds. 
* **Data Source & Dictionary:** [Club Football Match Data 2000-2025](https://github.com/xgabora/Club-Football-Match-Data-2000-2025/blob/main/README.md)

## Project Workflow

### 1. Data Cleaning & Preprocessing
* Identified and handled missing data by removing technical columns and betting odds (e.g., `Over25`, `HandiSize`) with excessive null values.
* Cleaned the dataset to focus on primary leagues to maintain data integrity and consistency.
* Converted `MatchDate` strings into standard Python `datetime` objects.

### 2. Feature Engineering
Created new predictive features to better capture team momentum and strength disparities:
* `EloDiff`: The difference between the Home Team's ELO and the Away Team's ELO.
* `Form3Diff` & `Form5Diff`: The difference in points accumulated over the last 3 and 5 matches between the home and away teams.
* `TotalGoals`: The sum of full-time home and away goals.
* `HomeWin`: A binary target variable created for correlation analysis, mapping 'H' (Home Win) to 1, and 'D'/'A' to 0.

### 3. Exploratory Data Analysis (EDA)
The EDA section visualizes historical trends and extracts insights, answering key questions such as:
* **League Competitiveness:** Analyzing and comparing the average total goals scored across different global divisions.
* **League Dominance:** Tracking the ELO ratings of major leagues over the last 25 years.
* **Manchester United Deep-Dive:** A specific look into Manchester United's performance, tracking their ELO rating evolution, goal-scoring trends compared to the overall English Premier League, and identifying their highest-scoring games.
* **Correlation Analysis:** Utilizing Seaborn heatmaps to identify strong linear relationships between home wins, half-time results, ELO differences, and team form.

### 4. Predictive Modeling
To predict the Full-Time Result (`FTResult`), the dataset was scaled using `MinMaxScaler` and split into training and testing sets (80/20). The following machine learning classifiers were trained and evaluated:
* **Support Vector Machine (SVM)**
* **Logistic Regression** (using `newton-cholesky` solver)
* **Decision Tree Classifier**
* **Random Forest Classifier**

Model performances were thoroughly evaluated using **Accuracy, Precision, and Recall**, and visualized using **Confusion Matrix Heatmaps** and **Decision Tree plots**.

## Technologies & Libraries Used
* **Language:** Python 3
* **Data Manipulation:** `pandas`, `numpy`
* **Data Visualization:** `matplotlib.pyplot`, `seaborn`
* **Machine Learning:** `scikit-learn`
