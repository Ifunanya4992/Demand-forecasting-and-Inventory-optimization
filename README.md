## Demand-forecasting-and-Inventory-optimization
<img width="300" height="168" alt="image" src="https://github.com/user-attachments/assets/40e20fd7-91cb-4381-b791-fe0c12604998" />

##PROJECT OVERVIEW
I addressed  the critical challenge of medical waste and stockouts in hospital pharmacies. By integrating Machine Learning (Python) with Business Intelligence (Power BI), I developed a predictive system that forecasts drug demand and automates inventory alerts. This tool helps hospital administrators transition from reactive ordering to a proactive, data-driven supply chain.

## Objectives
#Predict future drug demand using machine learning 
#Identify drugs at risk of stockout and expiry 
#Optimize inventory planning and reduce waste 
#Support proactive decision-making using data insights

## DATA SOURCE: The dataset used in this project was gotten from Hospital pharmacy inventory containing:
# Drug_Name 
# Category 
# Supplier 
# Transaction_Date 
# Quantity_Sold 
# Stock_On_Hand 
# Unit_Cost 
# Expiry_Date


## Tools & Technologies
#Python (Pandas, NumPy, Scikit-learn)
#Data Visualization (Matplotlib, Seaborn, ploty)
#Power BI (for dashboard visualization)

## Data Preprocessing
# Imported the necessary libraries
# Converted date columns to datetime format 
# Checked and handled missing values 
# Ensured numeric columns (sales and stock) are valid 
# Removed inconsistencies and invalid entries


## Feature Engineering
#I created New features were created to improve model performance:
#days_to_expiry:  Remaining days before drug expiry 
#avg_daily_sales:  Average demand per drug 
#days_of_stock_left: Estimated stock duration 
#expiry_risk:  Flag for drugs close to expiry 
#stockout_risk: Flag for low stock levels 
#month, year:  For seasonality analysis

##Machine Learning Models
#I trained three separate Random Forest models, each targeting a different business problem:
#Model 1:  Demand Forecasting (Regression)
#Algorithm: RandomForestRegressor
#Target:  Quantity_Sold (continuous) 
#Split: 80% train / 20% test
#I chose Random Forest because it handles mixed data types, non-linear relationships, and #produces feature importance scores that I could present to stakeholders as explainable #insights.
#Model 2:  Stockout Risk (Classification)
#Algorithm : RandomForestClassifier
#Target: stockout_risk 
#I used classification here because the business question is binary: "Will this drug run out?" This lets pharmacy managers get a simple Yes/No alert they can act on immediately.
#Model 3:  Expiry Risk (Classification)
#Algorithm : RandomForestClassifier
#Target    : expiry_risk (binary: 0 = True, 1 = False)
#Expiry risk is also a binary question, "Will this drug expire before it sells?" The near perfect #accuracy here reflects the fact that days_to_expiry and Stock_On_Hand together are very #strong predictors of this outcome.

##Evaluation Metrics
#For Regression Model, I used
#Mean Absolute Error (MAE) 
#Root Mean Square Error (RMSE) 
#For Classification Models, I used
#Accuracy, Precision, Recall

##Results & Key Insights
#The demand forecasting model achieved moderate accuracy, providing useful predictions for inventory planning when combined with safety buffers. 
#The stockout risk model achieved 91% accuracy, effectively identifying drugs likely to run out of stock. 
#The expiry risk model achieved 99% accuracy, showing strong capability in detecting drugs close to expiry. 
#Powerbi Dashboard which visualizes stock alert system, Expiry risk detection, and High-demand drugs with low stock were successfully flagged for urgent restocking. 

##Conclusions
#This project showed me that machine learning can genuinely solve real, costly problems in pharmacy inventory management, problems that currently get managed with spreadsheets and intuition.

