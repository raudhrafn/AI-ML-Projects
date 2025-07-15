# **Car Price Analysis**

## **Project Overview**

This project aims to predict the pricing for used cars using machine learning models. The goal is not only to estimate prices accurately but also to identify which vehicle features have the greatest impact on value. This analysis will help used car dealerships understand what drives pricing in the market, enabling them to make data-driven decisions about inventory acquisition, pricing strategies, and identifying undervalued vehicles. The dataset is from Kaggle and contains data on over 400K cars. 

## **Key Features**

* **Year** - Vehicle model year
* **Odometer** - Odometer reading
* **Manufacturer** (e.g., Tesla, Toyota, Ford, Chevy)
* **Condition** (e.g., excellent, good, fair, like new)
* **Fuel Type** (e.g., gas, electric, hybrid)
* **Transmission** (e.g., automatic, manual)
* **Vehicle Type** (e.g., sedan, SUV, pickup, hatchback)

### **EDA and Prep**
- Explored dataset
- Handled missing values and data quality issues
- Removed extreme outliers
- Applied feature engineering and categorical encoding

### **Modeling**
- Compared multiple regression techniques:
  - Linear Regression (baseline)
  - Ridge Regression (L2 regularization)
  - Lasso Regression (L1 regularization)
- Used 5-fold cross-validation for robust performance evaluation
- Applied GridSearchCV for hyperparameter optimization
- Standardized numerical features while preserving categorical variables

### **Model Performance**
- **Best Model**: Ridge Regression
- **R² Score**: 0.56
- **RMSE**: 8476.426
- **Cross-validation**: Consistent performance across folds

## **Key Price Factors**
The coefficients from the Ridge Regression model indicate the impact of each feature on the predicted price. A positive coefficient suggests that as the feature increases (or is present, in the case of one-hot encoded categorical features), the price tends to increase. A negative coefficient suggests the opposite.

### **Positive Price Factors**
- **Manufacturer**: Certain manufacturers command higher prices. As seen in the feature importance, Tesla and Porsche have the largest positive coefficients, indicating a significant positive impact on price. Other manufacturers with notable positive coefficients include alfa-romeo and aston-martin.
- **Year**: Newer cars tend to be more expensive. The positive coefficient for year confirms this expected relationship. Car Type: Certain car types are associated with higher prices. Trucks and pickups have significant positive coefficients, suggesting they are generally more expensive. Offroad vehicles also show a positive price factor.

### **Negative Price Factors**
- **Odometer**: Higher mileage leads to lower prices. The negative coefficient for odometer aligns with this expectation.
- **Manufacturer**: Some manufacturers are associated with lower prices compared to the baseline. Fiat, Kia, Hyundai, Mitsubishi, Volkswagen, Mazda, Chrysler, and Harley-Davidson show notable negative coefficients.
- **Car Type**: Hatchbacks have a notable negative coefficient.

### **Other Factors**
- **Car Type**: As mentioned above, trucks, pickups, and offroad vehicles tend to have higher prices, while hatchbacks tend to have lower prices. The model considers other types as well, with varying impacts.
- **Condition**: Similarly, the coefficients for the conditions 'excellent' and 'like new' have positive impacts, while 'fair' and 'salvage' have negative impacts.

## **Dealer Recommendations**
Based on these findings, here are some recommendations for your used car dealership:

- **Prioritize Newer, Lower-Mileage Inventory**: The strong positive correlation between year and price, and the strong negative correlation between odometer and price, highlight the importance of stocking newer cars with lower mileage to maximize potential profit.
- **Focus on High-Value Manufacturers and Types**: Given the positive coefficients for manufacturers like Tesla and Porsche, and vehicle types like trucks, pickups, and offroad vehicles, consider prioritizing the acquisition and stocking of these vehicles if they align with your market and customer base.
- **Be Strategic with Lower-Value Inventory**: For manufacturers and types with negative price factors (e.g., Fiat, Kia, hatchbacks), strategize on competitive pricing or consider stocking fewer of these models unless there is high local demand.
- **Highlight Condition**: Emphasize the condition of the vehicles, as better conditions are likely to command higher prices. Ensure your descriptions accurately reflect the vehicle's condition and consider detailing or reconditioning cars to improve their perceived condition.
- **Consider Market Demand for Specific Models**: While manufacturers and types are strong indicators, the model feature also had a large number of unique values, suggesting that specific models within a manufacturer or type can significantly influence price. Further analysis into popular and high-value specific models in your region could be beneficial.

These insights can help you make more informed decisions about purchasing inventory, pricing cars, and highlighting features that are most valued by customers in your market.
