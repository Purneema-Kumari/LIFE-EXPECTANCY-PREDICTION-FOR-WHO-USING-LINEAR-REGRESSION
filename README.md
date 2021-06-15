# LIFE-EXPECTANCY-PREDICTION-FOR-WHO-USING-LINEAR-REGRESSION
In this project WHO wanted a data driven approach which would help countries suggesting in which area they should work upon to increase the life expectancy of their population. The objective of the project was to build a prediction engine which can predict the life expectancy based on various features like status of country, GDP, alcohol consumption, adult mortality rate etc.  

**Loading and Understanding data: **

For data loading and data manipulation I have imported packages like numpy and pandas from python libraries. 
I have used functions like info() and describe() to get the information rows, columns, central tendencies, measure of dispersion, different features in the data.
The data has numerical as well as some categorical variables. Before treating them I have separated them using select_dtype() to make the calculation easier.

**Data Pre-processing:**

For data pre-processing I have used packages from sklearn and statsmodel.  
I have noticed certain discrepancies in the data like missing values, extra spaces in the column. In this step I have tried to fix them.
Extra spaces: To remove it I have used function called rename().
Treatment of categorical variable: Since ML algorithm does not understand categorical features so to convert categorical into numerical I have used LabelEncoder().
Treatment of missing values: There were some missing values in the data. To treat these NA values I have replaced it using mean values.

**Exploratory Data Analysis:** 

For EDA I have used data visualization technique. I have imported packages like seaborn and matplotlib. 
Outliers: To check outliers in the data I have drawn boxplot. This infer that the data does not had significant outliers.
Distribution of Y(i.e life expectancy): To check the distribution I have drawn distplot from seaborn library. The graph reflects that Y variable was linearly distributed. So the assumption for linear regression holds true.
Check for multicollinearity: I have drawn heatmap from seaborn library to check multicollinearity of features. 
From the graph: “Life expectancy” was positively correlated with “schooling” and “income composition” and it was negatively correlated with “adult mortality rate”.
Also “thinness 5-9 years” and “thinness 1-19 years” were highly correlated. So to maintain assumption of linear regression I have excluded “thinness 5-9 years” from the data.
To know the relationship between different features I have drawn pairplot() from seaborn library. The graphs shows that “Income composition” feature has strong correlation with “Life expectancy”.
This is how I got the starting point of my model building.

**Model building: **

I have started this step with dividing data into train and test. To built the model I have used recursive feature elimination(RFE) method. After passing the arbitrary selected columns by RFE I have manually evaluated each models p-value and VIF value. I kept dropping the variables unless I found the acceptable range for p-value and VIF. The values of R^2 and adj R^2 were 0.76 and 0.75 respectively. 
Finally I have sorted some variables for final model building i.e. “Income composition”, “BMI”, “Total expenditure”, ”Status”, ”Adult mortality rate”, “thinness 1-19 years”, “HIV/AIDS”, “Infant deaths”.  


