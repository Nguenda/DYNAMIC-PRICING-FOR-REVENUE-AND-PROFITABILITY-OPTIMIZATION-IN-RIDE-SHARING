# DYNAMIC PRICING FOR REVENUE AND PROFITABILITY OPTIMIZATION IN RIDE SHARING

## About the Dataset

A ride-sharing company wants to implement a dynamic pricing strategy to optimize fares based on real-time market conditions. The company currently uses only ride duration to decide ride fares. The company aims to leverage data-driven techniques to analyze historical data and develop a predictive model that can dynamically adjust prices in response to changing factors.

The dataset containing historical ride data has been provided. It includes features such as the number of riders, number of drivers, location category, customer loyalty status, number of past rides, average ratings, time of booking, vehicle type, expected ride duration, and historical cost of the rides.

Your goal is to build a dynamic pricing model that incorporates the provided features to predict optimal fares for rides in real time. The model must consider factors such as demand patterns and supply availability. The dataset includes the following features:

- **`Number_of_Riders`**: Number of people requesting the ride.
- **`Number_of_Drivers`**: Number of available drivers at the time.
- **`Location_Category`**: The location where the ride is requested (e.g., urban or suburban).
- **`Customer_Loyalty_Status`**: Whether the customer is a loyal user (could be categorical: Yes/No or 0/1).
- **`Number_of_Past_Rides`**: How many previous rides the customer has taken.
- **`Average_Ratings`**: Ratings given by customers to the driver.
- **`Time_of_Booking`**: The time at which the ride was booked (can be converted to hour, day, week, or part of the day for better analysis).
- **`Vehicle_Type`**: The type of vehicle requested (e.g., sedan, SUV).
- **`Expected_Ride_Duration`**: Estimated time of the ride in minutes.
- **`Historical_Cost_of_Ride`**: The previous fare for a similar ride (dependent variable we want to predict).

## Overview

The problem addressed in this report is the need for a dynamic pricing strategy in the ride-sharing industry to optimize fares based on real-time market conditions. Currently, the company relies solely on ride duration to determine fares, which may not account for the varying factors influencing demand and supply. 

To overcome this limitation, the company aims to develop a data-driven predictive model using historical ride data. The model will dynamically adjust prices by considering critical factors such as the number of riders, number of available drivers, customer loyalty, location category, time of booking, and other relevant attributes. 

This solution will enable the company to enhance its pricing strategy, improving competitiveness and ensuring fair fares for both riders and drivers while maximizing operational efficiency.

## Methodology

The data is public data sourced from Kaggle. The collected datasets were cleaned and preprocessed to ensure data quality and consistency. The preprocessing steps included:

1. **Handling Missing Values**: Missing values were identified and addressed through appropriate techniques, such as imputation or removal, depending on the context.
2. **Feature Engineering**: New features were derived from the existing data to improve the model's predictive power. For example, the `Time_of_Booking` feature was transformed into time-based categories (e.g., hour, part of the day) to capture temporal patterns.
3. **Categorical Encoding**: Categorical variables, such as `Location_Category` and `Customer_Loyalty_Status`, were encoded using techniques like one-hot encoding or label encoding to make them suitable for machine learning models.
4. **Outlier Detection and Treatment**: Outliers were identified in numerical features and treated to avoid skewing the model results.
5. **Normalization and Scaling**: Numerical features, such as `Expected_Ride_Duration` and `Number_of_Past_Rides`, were normalized or scaled to ensure consistent ranges for all variables.

### Strategies Implemented

To address the problem, the following strategies were employed:

1. **Driver Allocation Strategy**: Optimized the allocation of drivers to high-demand areas based on historical and real-time data to improve availability and reduce wait times.

2. **Customer Segmentation Strategy**: Used customer data to segment users into different categories (e.g., loyalty status, ride frequency) to tailor services and pricing more effectively.

3. **Dynamic Pricing Strategy**: Developed a dynamic pricing model using machine learning algorithms to predict optimal fares based on factors such as demand, supply, location, and booking time.

### Simulation for Pricing and Promotions

Pricing and promotional strategies were developed and simulated at various levels, including market and booking channels. For example:

- **Simulation of `Booking_Channel`**: Analyzed and simulated booking patterns based on `Time_of_Booking` and `Location_Category` to identify optimal pricing and promotional opportunities.
- **Market-Specific Adjustments**: Tailored pricing and promotions for different markets to maximize revenue and customer satisfaction.

### Machine Learning Model Development

For the development of the dynamic pricing model, the following steps were performed:

1. **Dataset Splitting**: The dataset was split into training and testing sets using the `train_test_split` function from `sklearn.model_selection` to ensure robust model evaluation.
2. **Baseline Model**: Linear Regression was used as a baseline model for predicting ride fares.

### Model Evaluation

The final model was evaluated using standard regression metrics, including:

- **Mean Absolute Error (MAE)**
- **Mean Squared Error (MSE)**
- **R-squared**

These metrics ensured the model's reliability and accuracy in predicting optimal ride fares. This comprehensive approach allowed for the successful implementation of a dynamic pricing strategy to enhance revenue and operational performance.

