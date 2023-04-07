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
Supermarket Type1, Supermarket2, Supermarket3 and Grocery Store are the four categories in the Outlet Type column. <br>
There are some outliers in these boxplots, with some more extreme outliers in the Grocery Store boxplot. <br>
Supermarket 1,2 and 3 have a similar distribution of data while the Grocery store seems to have a higher degree <br> 
of item visibilty of their products compared to the other types. <br>

### Explanatory Data Analysis
During the Explanatory Data Analysis phase, I answered the following questions:

1. Which Outlet Type has the most and least amount of sales?
> It was found that the Grocery Store has the least, with an avergae of $500 in sales
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

- Baseline Model, Linear Regression Model, Decision Tree Regressor Model, Tuned Decision Tree Regressor (Training & Testing Set):
<p align = "left"> 
  <img src = "https://github.com/hgploutz/food-sales-predictions/blob/main/model_analysis.png">
</p>



- The Final Model Chosen was a `Tuned Decision Tree Model` with the max depth tuned to 5.
- For the testing set on the model, `56.3%` of the variance in y was explained by x. 
- The Mean Absolute Error was off by about `$31,998.94`.
- The Mean Squared Error was `$2,044,264,641.83`.
- The Root Mean Squared Error had a calculation of `$45,213.55`.


Refer to the metrics to describe how well the model would solve the business problem

### Recommendations:

More of your own text here


## Limitations & Next Steps

More of your own text here


### For further information


For any additional questions, please contact **email**