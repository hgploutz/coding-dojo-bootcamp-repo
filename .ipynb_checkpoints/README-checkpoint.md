# Food Sales Predictions & Insights
## Analyzing the Sales of Food Across Different Types of Outlets 

**Author**: Hannah Ploutz

### Business problem:

We are trying to figure out how well food sales do based on multiple different categories such as item visibilty, type of grocery store and more.


### Data:

There are 8523 rows, and 12 columns.

### Data Dictionary:

<p align = "center"> 
  <img src = "https://github.com/hgploutz/food-sales-predictions/blob/main/Data/data_dictionary%20(1).png">
</p>

## During the initial cleaning portion for this project the following actions were taken:
- Categorical columns were cleaned up to establish consistency in the data
- Duplicate and Missing Values were taken care of
- Bar chart visualizations were used to determine how to handle some "missing" data in the Outlet_Size column

<p align = "center"> 
  <img src = "https://github.com/hgploutz/food-sales-predictions/blob/main/Data/bar_chart_viz2.png">
</p>


### Exploratory Data Analysis
During the Exploratory Data Analysis phase the following were used to visualize the data 
- Histogram
- Boxplot
- Heatmap

<p align = "center"> 
  <img src = "https://github.com/hgploutz/food-sales-predictions/blob/main/Data/exploratory1.png">
</p>

In the above Histogram, I used the Item_Outlet_Sales column from the dataframe to create a histogram that looks at <br>
the distribution of the Sales of the products in the particular stores. The y column 'Number of Products in Sales Range' <br> 
is the frequency of sales amounts that are bucketed at each of the sales intervals <br>


<p align = "center"> 
  <img src = "https://github.com/hgploutz/food-sales-predictions/blob/main/Data/exploratoryviz2.png">
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


## Model Analysis Revisited 

### LinearRegression Coefficients Plot
<p align = "center"> 
  <img src = "https://github.com/hgploutz/food-sales-predictions/blob/main/Data/LinearRegressionAnalysis.png">
</p>

In our analysis, different factors about our outlets can influence our sales. For instance, if an outlet has the ID "Outlet_identifier_OUT027" or if it's classified as a "Supermarket Type 3," we tend to see higher sales. This suggests that these factors positively contribute to our business success.

Likewise, outlets of medium size tend to see increased sales, pointing to a favorable balance between having a broad range of products and maintaining manageable overhead costs.

However, not all factors are beneficial. When our outlet is classified as a grocery store, we tend to see a decrease in sales. This could be due to a variety of factors, such as lower foot traffic or more limited product ranges compared to larger outlets. Please keep in mind that these observations are based on our current data and trends might change over time.

### Tree-Based Models Feature Importances Plot
<p align = "center"> 
  <img src = "https://github.com/hgploutz/food-sales-predictions/blob/main/Data/RandomForestFeatureAnalysis.png">
</p>

Our analysis shows that the price (MRP) of an item has a major role in predicting its final grade. The higher the price, the better we can predict the grade. When our outlets are a specific type – the 'Grocery Store' type – we seem to predict the final grade more accurately. So, the type of store plays a critical role in our predictions. Interestingly, items that aren't as visible have a greater impact on the final grade. So, visibility is not always key. The weight of an item doesn't tip our predictions too much one way or the other, but there's a slight increase in predictability when the weight is around the middle (12.5).

Finally, the establishment year of our outlets does matter. Those established around 1985 tend to have a larger impact on sales. Like a good wine, it seems our outlets improve with age! As always, these findings are based on our current data. If circumstances change, these factors might need to be reassessed.

### Summary Plot - Bar Version
<p align = "center"> 
  <img src = "https://github.com/hgploutz/food-sales-predictions/blob/main/Data/ShapImageBar.png">
</p>

Both our SHAP and Feature Importance charts show us that the price tag (Item_MRP) of an item is really important. Also, whether an outlet is a Grocery Store can change the sales a lot. However, there's a difference when it comes to the third most influential factor. The SHAP chart points to Supermarket Type 3, while the Feature Importance chart tells us that how visible an item is plays a big role. So, depending on the perspective, the third key factor varies.

### Summary plot - Dot Version
<p align = "center"> 
  <img src = "https://github.com/hgploutz/food-sales-predictions/blob/main/Data/ShapImageDot.png">
</p>

Our SHAP dot chart tells us a few things. First, the price tag (Item_MRP) of an item can really change our sales predictions for a single item. The more expensive the item, the bigger its influence on the prediction. Second, whether an outlet is a Grocery Store also makes a big difference. But in this case, being less of a 'Grocery Store' type seems to change our predictions more.

Lastly, if an outlet is a 'Supermarket Type 3', this too can shake things up. Again, being more of a 'Supermarket Type 3' tends to alter our sales predictions more. 

## High MRP & High Visibility Analysis

- The reason I chose High MRP is because it seems to be very impactful on the data and I wanted to explore it more. The more an item MRP is, theoretically, the lower the food sales could be depending on the situation. Like, if there is a store with the average cost of bread is 2 dollars, but there is a bread that costs 15 dollars, could that be lowering the food sales? I wanted to explore that thought more

- The reason I chose High Visibility is it seems like a fairly straightforward thought - if the item is easier to see, then it should be driving up sales right?

### High MRP Insight
**Shap Force Plot**
<p align = "center"> 
  <img src = "https://github.com/hgploutz/food-sales-predictions/blob/main/Data/HighMRPShap.png">
</p>

We start with a baseline sales prediction of 2,145, with the actual prediction of 3424.20. Certain characteristics of our outlets and items can adjust this prediction. For example, if the Outlet Type is 0 and the item has a high price (Item MRP), it increases our sales prediction to a higher value.

On the other hand, some features reduce our sales prediction. If an item isn't very visible or if the outlet has been established for a long time, our prediction for sales tends to go down. 

**Lime Tabular Explanation** 
<p align = "center"> 
  <img src = "https://github.com/hgploutz/food-sales-predictions/blob/main/Data/HighMRPlime.png">
</p>

Our model predicted value for high MRP is 3424.20. To understand why the model made this prediction, we used a tool called LIME. For this particular prediction, it turns out that the item's price (Item MRP) of over 181.39 and whether the outlet was a Grocery Store were the deciding factors. If the item was sold in a Grocery store, it drove the prediction up by about 2,000 and if the item had an MRP of about 200, then it also drove up the prediction by about 1,600. In the opposite direction, if the item was sold at a Supermarket, then it would drive the prediction down by about 400.

### High Visibility Insight
**Shap Force Plot**
<p align = "center"> 
  <img src = "https://github.com/hgploutz/food-sales-predictions/blob/main/Data/HighVisShap.png">
</p>

We start by a baseline of 2,145. Then, we adjust this prediction based on specific characteristics of our outlets and items and wind up with a prediction of 361.28. That's quite a decrease!!

The reason it decreased so much was that if the type was "Grocery Store" then it would drive the predicition sharply downwards by about 1600. 

On the flip side, if an outlet was established in 1985, our sales prediction increases, to up the predicition by about 150.


**Lime Tabular Explanation** 
<p align = "center"> 
  <img src = "https://github.com/hgploutz/food-sales-predictions/blob/main/Data/HighVisLime.png">
</p>

Our model predicted value for high Visibility is 361.28. To understand why the model made this guess, we used a tool called LIME.

In this specific case, the factors that made the most difference were that the type was Grocery Store, Supermarket, and Item MRP. 

- Just selling the item at a Grocery store significantly decreased the prediction by about 2,000
- If the item was sold at a Supermarket, then it would decrease the prediction by just over 400
- If the item had an MRP of a little over 140, then it would increase the prediction by 403

## Limitations & Next Steps

From here, a business owner could use these insights to figure out the best method to get the most food sales for their business.


### For further information


For any additional questions, please contact Hannah Ploutz @ **hgploutz@gmail.com**