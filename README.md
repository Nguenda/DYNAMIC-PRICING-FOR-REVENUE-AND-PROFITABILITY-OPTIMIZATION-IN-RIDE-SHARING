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

To ensure a clear understanding of the project and its limitations, the following assumptions are made based on the data and project requirements:
 
- The dataset includes all necessary features to predict optimal fares, with no critical feature missing.  
- The dataset values (e.g., `Number_of_Riders`, `Number_of_Drivers`, `Historical_Cost_of_Ride`) are accurate and reflect real-world scenarios.   
- Rows in the dataset represent events in chronological order, and the rows are sequential.  
- Each ride request is unique, with no overlapping rides for the same driver or rider.  
- `Number_of_Riders` and `Number_of_Drivers` accurately represent real-time demand and supply at the time of booking.  
- The `Time_of_Booking` feature effectively captures temporal demand patterns (e.g., peak and off-peak times) without requiring detailed timestamps.  
- The `Location_Category` feature reflects geographical cost differences (e.g., urban areas generally have higher fares than suburban ones).  
- Different `Vehicle_Type` categories have unique base fare structures, with Premium vehicles costing more than Economy vehicles.  
- Each ride instance is independent of others, with no dependency on previous or future rides.  
- The model predicts fares based solely on the provided features, excluding external factors like fuel prices, weather, or traffic conditions.  
- Fares can be adjusted dynamically without significantly affecting demand; small price increases are unlikely to drastically reduce ride requests.  
- The relationships between features (e.g., demand-supply ratio and `Historical_Cost_of_Ride`) are stable and consistent across the dataset.  
- Real-time data for `Number_of_Riders`, `Number_of_Drivers`, and `Time_of_Booking` will be available during deployment.  
- The model will be periodically updated to incorporate changes in demand patterns, customer behavior, or operational dynamics.  
- The company is willing to implement and adjust fares dynamically based on the model's recommendations.  
- There are no regulatory or operational constraints preventing dynamic pricing adjustments.  
- Customers are likely to accept dynamically priced fares based on market conditions.  


## Methodology

The data is public data sourced from Kaggle. The collected datasets were cleaned and preprocessed to ensure data quality and consistency. The preprocessing steps included:

1. **Handling Missing Values**: Missing values were identified and addressed through appropriate techniques, such as imputation or removal, depending on the context.
2. **Feature Engineering**: New features were derived from the existing data to improve the model's predictive power. For example, the `Time_of_Booking` feature was transformed into time-based categories (e.g., hour, part of the day) to capture temporal patterns.
3. **Categorical Encoding**: Categorical variables, such as `Location_Category` and `Customer_Loyalty_Status`, were encoded using techniques like one-hot encoding or label encoding to make them suitable for machine learning models.
4. **Outlier Detection and Treatment**: Outliers were identified in numerical features and treated to avoid skewing the model results.
5. **Normalization and Scaling**: Numerical features, such as `Expected_Ride_Duration` and `Number_of_Past_Rides`, were normalized or scaled to ensure consistent ranges for all variables.

##### Key Observations About The Data
1. The dataset lacks a datetime column but includes features like Time_of_Booking, which indicates temporal aspects of ride requests (e.g., Night and Evening).
2. The rows may or may not be sequentially ordered in time. 



#### Strategies Implemented

To address the problem, the following strategies were employed:

1. **Driver Allocation Strategy**: Optimized the allocation of drivers to high-demand areas based on historical and real-time data to improve availability and reduce wait times.

2. **Customer Segmentation Strategy**: Used customer data to segment users into different categories (e.g., loyalty status, ride frequency) to tailor services and pricing more effectively.

3. **Dynamic Pricing Strategy**: Developed a dynamic pricing model using machine learning algorithms to predict optimal fares based on factors such as demand, supply, location, and booking time.

#### Simulation for Pricing and Promotions

Pricing and promotional strategies were developed and simulated at various levels, including market and booking channels. For example:

- **Simulation of `Booking_Channel`**: Analyzed and simulated booking patterns based on `Time_of_Booking` and `Location_Category` to identify optimal pricing and promotional opportunities.
- **Market-Specific Adjustments**: Tailored pricing and promotions for different markets to maximize revenue and customer satisfaction.

#### Machine Learning Model Development

For the development of the dynamic pricing model, the following steps were performed:

1. **Dataset Splitting**: The dataset was split into training and testing sets using the `train_test_split` function from `sklearn.model_selection` to ensure robust model evaluation.
2. **Baseline Model**: Linear Regression was used as a baseline model for predicting ride fares.

#### Model Evaluation

The final model was evaluated using standard regression metrics, including:

- **Mean Absolute Error (MAE)**
- **Mean Squared Error (MSE)**
- **R-squared**

These metrics ensured the model's reliability and accuracy in predicting optimal ride fares. This comprehensive approach allowed for the successful implementation of a dynamic pricing strategy to enhance revenue and operational performance.

# EDA
![Alt Text](images/timesseriesplot.png)

The data reveals periods of both upward and downward trends, indicating fluctuations in ride costs over time. Notable peaks and troughs suggest variability in pricing influenced by factors such as demand, location, or ride type. The minimum cost of $25.99 represents a point of low pricing, possibly due to off-peak times or discounts. The maximum cost of $836.12 highlights a significant fare, likely influenced by factors such as long ride duration, premium vehicle type, or peak demand.

**Insights and Implications:** The observed trends emphasize the potential for dynamic pricing strategies to capture and respond to market demand variability effectively.

![Alt Text](images/ride_duration.png)

The data indicates a mix of short and long rides, demonstrating the service's versatility for different trip purposes. The variety in ride duration shows usage for both quick errands and lengthy commutes. Short durations reflect urban commutes or errands. Long durations suggest intercity or long-distance rides, often associated with premium services.

**Insights and Implications:** The variability in ride duration indicates a need for pricing segmentation based on trip type and distance. Tailoring pricing strategies can better cater to diverse customer needs.

![Alt Text](images/past_ride.png)

The distribution highlights periods of high engagement with frequent riders, interspersed with newer or less active customers. These patterns may reflect the impact of loyalty programs or targeted marketing strategies to encourage repeat rides. The minimum value represents new customers with no prior rides. The maximum value signifies highly engaged customers, likely benefiting from loyalty incentives or frequent usage.

**Insights and Implications:** Patterns in customer ride history reveal opportunities to target specific customer segments with promotions or incentives. For example, occasional riders could be encouraged to ride more frequently through loyalty rewards or tailored offers.

![Alt Text](images/demand-supply.png)

Frequent fluctuations in the demand-supply ratio indicate periods of high demand with insufficient driver availability. Extreme spikes suggest unusual ride demand, potentially caused by events, adverse weather, or city-wide activities. A low ratio reflects a balanced or oversupplied market. A high ratio signifies a severe demand-supply imbalance, likely leading to surge pricing.

**Insights and Implications:** Spikes in the ratio suggest opportunities to optimize driver allocation in areas or times of high demand. This could help mitigate extreme surges, improve service quality, and reduce fare volatility.

![Alt Text](images/rides_by_location.png)

The data reveals that:
- Urban areas dominate the distribution with consistent contributions across all rider counts, reflecting the primary demand for the service originating from cities.  
- The suburban layer displays variability with spikes around specific Number_of_Riders values, potentially indicating preferences for family or small group travel.  
- Rural contributions are intermittent, with peaks likely representing occasional larger group requirements or isolated high-demand scenarios.

**Business Implications:**

- **Resource Allocation:**  
  - **Urban Areas:** Continuous driver availability is essential to meet steady demand.  
  - **Suburban Areas:** Strategies should target evening or weekend peaks when group rides are more frequent.  
  - **Rural Areas:** Promotions or specialized services could cater to larger group rides or specific events.  

- **Marketing Focus:**  
  - **Urban:** Highlight everyday convenience and efficiency to attract regular riders.  
  - **Suburban:** Emphasize family-friendly services or rideshare options to appeal to group travelers.  
  - **Rural:** Promote availability for long-distance travel or group events to meet unique local needs.  

  
  

  

  
