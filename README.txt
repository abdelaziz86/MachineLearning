for multiple linear regreesion : 
to check if a variable is useful , P should be < 0.05 , otherwise it's useless	

in ML , the standardized coefficients = weights : 
the closer a weight is to 0 , the smaller its impact 
the bigger the weight, the bigger its impact


Cleaning datasets : 

data = raw_data.drop(columns,axis) 
data = raw_data.drop(['Model'], axis=1) ## 1 : rows / 0 : columns

data.isnull().sum() ## check how much variables are missing
data_no_mv = data.dropna(axis=0) ##remove all missing variables

pd.get_dummies(df[,drop_firs]) : spots all categorical variables and creates dummies automatically


When a car is an 'Audi' all other brand dummies are 0. When a car is not 'Audi', at least one of them will be 1. 
By including all dummies have introduced multicollinearity (perfect multicollinearity)!!!
If we run a regression including all these dummies, the coefficients would be inflated and completely off-mark.
Now you see why we need to drop one of the dummy variables for each feature.

==== Weights(coefs / beta 1 , beta2...) Interpretation =====
- A positive weight : feature increases in value so do the log_price and Price respectively
- A negative weight : feature decreases in value so do the log_price and Price respectively

==== Dummy Variables ======
- A positive weight shows that the respective category is more expensive than the benchmark (dropped variable)
- A negative weight shows that the respective category is less expensive than the benchmark (dropped variable)


How to improve our model : 
1- Use a different set of variables 
2- Remove a bigger part of the outliers 
3- Use different kinds of transformations