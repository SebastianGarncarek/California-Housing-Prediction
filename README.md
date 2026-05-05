# California Housing Price Prediction

## Project Overview
This project presents an end-to-end Machine Learning regression pipeline aimed at predicting the median house values in California districts based on the 1990 census data.

Rather than just running algorithms out-of-the-box, a significant portion of this project focuses on conducting **Exploratory Data Analysis**, identifying data anomalies, and applying thoughtful **Feature Engineering** to ensure the models learn from robust, unbiased data.

## Key Higlights
During the initial EDA phase, a significant anomaly was identified in the target variable distribution. A massive, artificial spike was present exactly at the **$500,001** mark.

<img width="1019" height="553" alt="artificialSpike" src="https://github.com/user-attachments/assets/f37a76ce-04bd-47fe-a407-8e2fc2194aa6" />

It became evident that the data was artificially capped at this value. Leaving these records in the dataset would severely distort the regression models, creating an invisible "ceiling" that the algorithms couldn't bypass. Consequently, these capped outliers were removed to maintain data integrity and improve the predictive power for properties below the half-million threshold.

Beyond handling data anomalies, understanding spatial distribution is crucial for real estate predictions. The visualization below maps out the districts using longitude and latitude, with the color representing the median house value and the circle size indicating population density. 

<img width="834" height="624" alt="caliMap" src="https://github.com/user-attachments/assets/7d22307c-636d-48f1-8f49-d40fdc1e82d4" />

As expected, there is a strong spatial correlation: properties clustered around high-density coastal hubs (such as the Bay Area and Los Angeles) command significantly higher prices compared to inland areas. This insight confirms that geographical coordinates and population density are pivotal features for the regression models.

## Methodology
The project follows a standard Data Science lifecycle:
1. **Data Collection & Cleaning:** Handling missing values (e.g., imputing `total_bedrooms`)
2. **Feature Engineering:** Transforming block-level data into actionable household-level metrics (e.g., calculating rooms and bedrooms per household).
3. **Modeling:** Establishing a baseline model and evaluating a diverse set of algorithms to find the optimal architecture.

## Model Evaluation & Results
To objectively measure performance, **Linear Regression** was used as the baseline model. Several algorithms were then trained and evaluated using the **Root Mean Squared Error (RMSE)** metric, including:
* k-Nearest Neighbors (k-NN)
* Optimized Decision Trees
* Random Forest
* Neural Networks (MLP)
* XGBoost

**XGBoost** emerged as the undisputed winner, yielding a final RMSE of **$40,787.26**. This represents a massive **~38% improvement** over the baseline Linear Regression model.

<img width="1189" height="590" alt="caliResults" src="https://github.com/user-attachments/assets/0d7bce34-5268-4156-8436-fc07dfac45f7" />

## Technologies Used
* **Language:** Python
* **Data Manipulation:** Pandas, NumPy
* **Machine Learning:** Scikit-Learn, XGBoost
* **Data Visualization:** Matplotlib, Seaborn

## Author
**Sebastian Garncarek** 
* M.Sc. Student in Computational Mathematics
* [Connect with me on LinkedIn](https://www.linkedin.com/in/sebastian-garncarek-a0376a405)
