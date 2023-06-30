# Food Sales Predictions & Insights
## Analyzing the Sales of Food Across Different Types of Outlets 

**Author**: Hannah Ploutz

### Business problem:

We are trying to figure out how well food sales do based on multiple different categories such as item visibilty, type of grocery store and more.


### Data:

There are 8523 rows, and 12 columns.

### Data Dictionary:

<p align = "center"> 
  <img src = "https://github.com/hgploutz/food-sales-predictions/blob/main/data_dictionary%20(1).png">
</p>

## During the initial cleaning portion for this project the following actions were taken:
- Categorical columns were cleaned up to establish consistency in the data
- Duplicate and Missing Values were taken care of
- Bar chart visualizations were used to determine how to handle some "missing" data in the Outlet_Size column

<p align = "center"> 
  <img src = "https://github.com/hgploutz/food-sales-predictions/blob/main/bar_chart_viz1.png">
</p>

<p align = "center"> 
  <img src = "https://github.com/hgploutz/food-sales-predictions/blob/main/bar_chart_viz2.png">
</p>


### Exploratory Data Analysis
During the Exploratory Data Analysis phase the following were used to visualize the data 
- Histogram
- Boxplot
- Heatmap

<p align = "center"> 
  <img src = "https://github.com/hgploutz/food-sales-predictions/blob/main/exploratory1.png">
</p>

In the above Histogram, I used the Item_Outlet_Sales column from the dataframe to create a histogram that looks at <br>
the distribution of the Sales of the products in the particular stores. The y column 'Number of Products in Sales Range' <br> 
is the frequency of sales amounts that are bucketed at each of the sales intervals <br>


<p align = "center"> 
  <img src = "https://github.com/hgploutz/food-sales-predictions/blob/main/exploratoryviz2.png">
</p>

Here I look at boxplots where the x-axis is "Outlet Type" and the y-axis is the "Item Visibilty" and I am wanting to compare the Outlet Type 
next to the Item Visibilty in the store. <br>

Supermarket 1,2 and 3 have a similar distribution of data while the Grocery store seems to have a higher degree <br> 
of item visibilty of their products compared to the other types. <br>

### Explanatory Data Analysis
During the Explanatory Data Analysis phase, I answered the following questions:

1. Which Outlet Type has the most and least amount of sales?
> It was found that the Grocery Store has the least, with an average of $500 in sales
2. What is the distribution of Item Visibility?
> Using a histogram, after viewing the distribution of Item Visibility for the producet, 
> that there is a higher amount of visibile items were bucketed in the 0.07
3. Which of the Item Types has the heaviest and lowest average weight?
> It was found that Starchy Foods have the highest weights, while Breads and Hard Drinks have the lowest average weights

## Model Analysis

 ### Maching Learning Using the Following Models:
    - Baseline Model 
    - Linear Regression Model
    - Decision Tree Regressor Model 
    - Tuned Decision Tree Regressor Model

## Models Evaluated & Results
(Training & Testing Set):

<p align = "left"> 
  <img src = "https://github.com/hgploutz/food-sales-predictions/blob/main/model_analysis.png">
</p>



- The Final Model Chosen was a `Tuned Decision Tree Model` with the max depth tuned to 5.
- For the testing set on the model, `59.71%` of the variance in y was explained by x. 
- The Mean Absolute Error was off by about `$743.53`.
- The Root Mean Squared Error had a calculation of `$1062.25`.

## Model Analysis Revisited 

### LinearRegression Coefficients Plot
<p align = "center"> 
  <img src = "https://github.com/hgploutz/food-sales-predictions/blob/main/LinearRegressionAnalysis.png">
</p>

- Outlet_identifier_OUT027, Outlet Type Supermarket Type3 and Outlet Size Medium all had the greatest impact
- Outlet_identifier_OUT027 has the coefficient of 581.879 which means that type of store had a great impact on food sales
- Supermarket Type 3 had 581.879 has a coefficient of 581.879 which also means this has a great impact on higher food sales
- Outlet Size Medium has a coefficient of 409.869 which means that if the outlet is categorized as a size medium, it has a high impact as well

### Tree-Based Models Feature Importances Plot
<p align = "center"> 
  <img src = "https://github.com/hgploutz/food-sales-predictions/blob/main/RandomForestFeatureAnalysis.png">
</p>

- The higher the MRP the more it was used to split the samples and predict the final grade
- The Type of grocery store was predominantly the 0.0 value that was used to predict the final grade
- The lower end of the Item_Visibility had a greater impact on predicting the final grade
- Item weight was fairly evenly distributed, with a spike right in the middle around 12.5
- This indicates that if the year of the Outlet was established was 195, that had the greatest impact on sales

### Summary Plot - Bar Version
<p align = "center"> 
  <img src = "https://github.com/hgploutz/food-sales-predictions/blob/main/ShapImageBar.png">
</p>

- Both SHAP and the Feature Importance visualizations display MRP as the most important feature
- They both also share the similarity for the Grocery Store, and start to differ right after that
- Shap shows the third most important being Supermarket Type 3 while the feature importance shows Item Visbility

### Summary plot - Dot Version
<p align = "center"> 
  <img src = "https://github.com/hgploutz/food-sales-predictions/blob/main/ShapImageDot.png">
</p>

- The most important feature with this Shap dot chart is definitely Item_MRP
- The Higher the value of the Item_MRP the higher in importance it is
- The Grocery store type coming in second, with the lower value of the the Outlet Type being more impactful
- The third most impactful feature would be Supermarket Type 3, where the higher values had a higher impact



### High MRP Insight
**Shap Force Plot**
<p align = "center"> 
  <img src = "https://github.com/hgploutz/food-sales-predictions/blob/main/HighMRPShap.png">
</p>

- The base value is 2,145
- The SHAP value is 3,424.20
- The features that are pushing the greatest and winning the prediction are:
> - Outlet Type 0 and Item MRP = 266.2
- The features that lost in making the prediction are:
> - Item visibility of 0.005 and Outlet establishment year 

**Lime Tabular Explanation** 
<p align = "center"> 
  <img src = "https://github.com/hgploutz/food-sales-predictions/blob/main/HighMRPlime.png">
</p>

- The predicted value was closer to the min of 58.46
- The most impactful features was Outlet Type Grocery Store and Item MRP

### High Visibility Insight
**Shap Force Plot**
<p align = "center"> 
  <img src = "https://github.com/hgploutz/food-sales-predictions/blob/main/HighVisShap.png">
</p>

- The base value is 2,145
- The SHAP value is 361.28
- The features that are pushing the greatest and winning the prediction are:
> - Outlet Type Grocery Store 1
- The features that lost in making the prediction are:
> - Outlet Establishment Year 1985


**Lime Tabular Explanation** 
<p align = "center"> 
  <img src = "https://github.com/hgploutz/food-sales-predictions/blob/main/HighVisLime.png">
</p>

- The predicted value was closer to the min of 48.25
- The most impactful features to the positive raiting was:
> - Item MRP, Year of 1985, Item Type Others and Hard Drinks


### Recommendations:

Overall, the best model is definitely the tuned Random Decision Tree Regressor Model. There was still some bias in the model, but by far it outperformed the linear regression model.


## Limitations & Next Steps

From here, a business owner could use these insights to figure out the best method to get the most food sales for their business.


### For further information


For any additional questions, please contact Hannah Ploutz @ **hgploutz@gmail.com**