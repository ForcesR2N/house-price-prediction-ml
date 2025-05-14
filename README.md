🏠 House Price Prediction with Feature Engineering

📋 Project Overview
This project demonstrates comprehensive feature engineering techniques for predicting house prices using machine learning. Through careful data preprocessing, feature creation, and model evaluation, we achieve 60.65% accuracy in predicting house prices.
🎯 Objectives

Apply advanced feature engineering techniques to improve model performance
Demonstrate the impact of data preprocessing on prediction accuracy
Create meaningful features using domain knowledge
Build an interpretable linear regression model for house price prediction

📊 Dataset
The dataset contains 538 housing records with 13 original features:
Numerical Features:

area - Total area of the house (sq ft)
bedrooms - Number of bedrooms
bathrooms - Number of bathrooms
stories - Number of stories/floors
parking - Number of parking spaces

Categorical Features:

mainroad - Located on main road (yes/no)
guestroom - Has guestroom (yes/no)
basement - Has basement (yes/no)
hotwaterheating - Has hot water heating (yes/no)
airconditioning - Has air conditioning (yes/no)
prefarea - In preferred area (yes/no)
furnishingstatus - Furnished/Semi-furnished/Unfurnished

🔧 Feature Engineering Techniques
1. Data Cleaning

Outlier Detection: Z-score method (threshold=3)
Outliers Removed: 7 properties with extreme area values
Missing Values: None found (clean dataset)

2. Feature Encoding

Binary Encoding: yes/no → 1/0 for 6 categorical features
One-Hot Encoding: furnishingstatus → 2 binary columns (drop_first=True)

3. Feature Scaling

StandardScaler: Applied to price and area features
Result: Mean ≈ 0, Standard Deviation ≈ 1

4. Feature Creation

total_rooms = bedrooms + bathrooms
price_area_ratio = price / area
luxury_score = airconditioning + (parking≥1) + prefarea
size_category = Binned area into 4 categories (small, medium, large, xlarge)

📈 Model Performance

Algorithm: Linear Regression
Training R²: 69.52%
Testing R²: 60.65%
Training RMSE: 0.5228
Testing RMSE: 0.7396
Overfitting: No (difference < 10%)

🏆 Feature Importance (Top 10)

1. size_xlarge (0.598) - Extra large houses
2. size_large (0.379) - Large houses
3. bathrooms (0.302) - Number of bathrooms
4. airconditioning (0.291) - Has AC
5. guestroom (0.245) - Has guestroom
6. mainroad (0.233) - On main road
7. luxury_score (0.214) - Our engineered feature!
8. furnishingstatus_unfurnished (0.211)
9. stories (0.208) - Number of floors
10. size_medium (0.199) - Medium size houses
