# Ames Housing Prices

*James Drabinsky*

### Problem Statement

Determine which features most influence the sale price of homes in Ames, Iowa and build a model to predict the price of homes in Ames, Iowa.

### Feature Engineering

There was a high correlation between a number of features in the dataset.  This could potentially create an issue multicollinearity.  This included:

- Dropping 'Garage Area' keeping the 'Garage Cars' feature.
- Combining all columns relating to square footage into one column.
- Combining all columns relating to bathrooms into one column.
- Dropping all columns with mostly null values.

### Modeling

I used SKLearn to create and evaluate different regression models based on my final features. 

These models scored as follows:

| Model                   | Train Score | Test Score |
|-------------------------|-------------|------------|
| Linear Regression       |   0.9409    |   -1.1567  |
| GridSearch w/Lasso      |   0.8785    |    0.8884  |
| GridSearch w/Ridge      |   0.8785    |    0.8884  |


# Summary and Conclusion

Linearity regression does not address the problem of multicollinearity in this dataset. Therefore, I used the Ridge and Lasso regularization techniques to deal with this issue. In Ridge regression the weights for attributes cannot exceed a certain constant. Because of this, Ridge regression models have significantly less error than linear regression. This was proven in my modeling as the Ridge regression had a RMSE of 27885.6367 while the OLS regression had a RMSE of 8.979829382409078e+16. 

Lasso also deals with multicollinearity by zeroing out the less effective variables.  Lasso shrinks the poor performing feature’s coefficient to zero thus, removing some features altogether. This works well for feature selection in cases where there is are a lot of features.  Lasso performed the best out of my three models and its RMSE was a bit lower than the Ridge RMSE.

With the GridSearch w/Lasso model I was able to get an explanation about what features are the most influential to a homes sale price in Ames, Iowa.  The most important features in all of my models were 'overall_quality', 'total_area', 'gr_liv_area', garage area', 'year_remodeled/add' and 'year_built'. This suggests that the most important features in determine housing prices in Ames relate to square footage or the year a home was built/renovated.
