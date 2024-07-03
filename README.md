#Berkeley Machine Learning and AI Professional Certification

This is 2nd Practical Application Assignment as part of Module 11.1

This practical application assignment focuses on explore a used car dataset from kaggle, in an effort to develop car price prediction model to help used car dealers interested in fine-tuning their inventory.

The original dataset contained information on 3 million used cars. The used dataset contains information on 426K cars to ensure speed of processing. The goal is to understand all factors that make a car more or less expensive. As a result of  analysis, dealer should provide clear recommendations to client as to what consumers value in a used car.

All aspect of data visualization has been done using Jupyter Notebook. The link of Notebook is 
https://github.com/vikashsinha72/UCBMLAI_PA2/



To frame the task, throughout these practical applications we will follow  standard process in industry for data AI/ML projects CRISP-DM.


## Data Used: 
The dataset used in this analysis is sourced from Kaggle and contains information on 426,880 used cars, including attributes such as price, year, manufacturer, model, condition, mileage, and more. 
 
## Data Preparation 
- **Missing Values:** Handled missing values by imputing or removing records where necessary. 
- **Feature Engineering:** Created new features such as `age` and `mileage_per_year`. 
- **Log Transformation:** Applied log transformation to skewed variables (`price` and `odometer`). 
- **Outliers:** Removed outliers in `price` and `odometer`. 
- **Categorical Variables:** Reduced the number of categories for high cardinality features. 

Data Summary"
- There is a total of 18 columns and 426K rows. 3 Columns are integer/floats.
- Other columns have data type as 'object' and some of them requires to transform as float/integer before analysis/train and prediction.
- There is a extremely high number of missing values, so we to correct than dropping the rows. This requires imputation to address this data issue.
- Most of the used cars were registered during 2010 and 2020. This gives ample time sequence for a decade to evolve prediction model.
- Some of the columns are insignificant and should be dropped. i.e. VIN
Column like size, has most of the value(75%) missing. Such column may influence the AI/ML model adversely and may reason of high amount of prediction error. Such column should also be dropped.

## Exploratory Data Analysis (EDA) 

- Visualized distributions of key variables. 
- Explored relationships between features and target variable. 
- Identified important correlations using a heatmap. 

  

## Modeling 
A linear regression model was built and evaluated. Feature importance was assessed using 5 selected features model. 
- Top five faetures used in linear regration were ['year', 'model', 'title_status', 'paint_color', 'state'] with variance ratio [0.3369985 , 0.26604357, 0.16648778, 0.13500991, 0.09546024]


### Model Performance 

- **Mean Squared Error (MSE, using Linear Regression):** 26968384.189089756
- **Mean Squared Error (MSE, using Polynomial Features):** 4.2345346107181177e-14
- **CV Mean Squared Error: 1.5057555271126403e-20 
- **R-squared:** 1.0


### Model coorelation between features 
The model coorelation between features help us understand the impact of each feature on car prices. Some key coefficients include: 

- **Year:** 0.27 (newer cars are priced higher) 
- **Odometer:** -0.39 (higher mileage cars are priced lower) 
- **Condition_good:** 0.25 (cars in good condition are priced higher) 
- **Model:** 0.73 (Some model cars are priced higher) 

  

## Recommendations 
Based on the analysis, the following recommendations are made for the used car dealership: 
- **Stock Newer Cars:** Newer cars tend to be priced higher. 
- **Prefer Low Mileage Cars:** Cars with lower mileage are valued more. 
- **Improve Car Condition:** Investing in repairs and detailing can increase car prices. 
- **Focus on Popular Brands:** Stocking popular brands can attract more customers. 

  

## Files 
- `vehicles.csv`: The dataset used for analysis. 
- `prompt_II.ipynb`: Jupyter notebook containing the complete analysis. 
- `README.md`: This file, summarizing the project. 


## Dependencies 
- `pandas` 
- `numpy` 
- `scikit-learn` 
- `matplotlib` 
- `seaborn` 

  

## How to Run 
1. Clone the repository. 
2. Ensure all dependencies are installed. 
3. Run the Jupyter notebook `prompt_II.ipynb` to see the complete analysis. 


## Conclusion 

This analysis provides insights into the factors that influence used car prices and offers actionable recommendations for a used car dealership. The linear regression model and feature importance analysis highlight the key attributes that affect car pricing. 



## Next Step

To improve the model's performance, we'll perform additional feature engineering. Here are the steps we may take: 

- Feature Engineering and Selection: Explore more advanced feature engineering and selection techniques to improve model performance. 
- Modeling with More Advanced Techniques: Consider using more advanced regression techniques 


Create new features: 
1. age: Calculate the age of the vehicle from the year. 
2. mileage_per_year: Calculate the average mileage per year. 

Transform skewed features: 
1. Apply log transformation to the price and odometer variables to reduce skewness. 

Remove outliers: 
Identify and remove outliers in the price and odometer columns. 

Re-encode categorical variables: 
Simplify categorical variables and re-encode them as before. 
