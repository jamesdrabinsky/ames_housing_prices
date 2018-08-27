For this project I build a model to predict the prices of homes in Ames, Iowa.  I was given a dataset of properties in Ames which were sold from 2006 to 2010. I used a number of tools to build the models, including the Python modules Pandas and Seaborn for visualizing the data, and SKLearn to create regression models.  My work on this project was done in three stages:

1. Data Cleaning and EDA - filling in null values with zeros or strings and removing redundant and inaccurate data.

2. Feature Engineering and Selection = deskewing the target variable with a log transformation.  Converting all data into the correct python format.  Dropping certain columns due to the potential for multicollinearity.  Removing outliers from the dataset and creating dummy variables.

3. Modeling - creating a basic linear regression model and also using Lasso, Ridge and Elastic Net regularization techniques.