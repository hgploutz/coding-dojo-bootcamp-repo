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


## Model Analysis Revisited 

### LinearRegression Coefficients Plot
<p align = "center"> 
  <img src = "https://github.com/hgploutz/food-sales-predictions/blob/main/LinearRegressionAnalysis.png">
</p>

Think of our sales like a recipe. Certain ingredients will make our dish better, and some might not. In our case, the 'ingredients' are different characteristics of our outlets. We found that when an outlet has the ID "Outlet_identifier_OUT027" or if it's a "Supermarket Type 3," our sales tend to be higher. It's like adding extra cheese to a pizza - it makes it better! We also noticed that when an outlet is medium-sized, sales tend to increase as well. It's as if having just the right amount of salt makes our dish tastier. But not all 'ingredients' make our sales recipe better. We noticed that when our outlet is a grocery store, sales tend to go down. It's like adding too much vinegar to our dish - it doesn't really help. Remember, this is what we found based on our current data. If things change in the future, we might have to tweak our recipe.

### Tree-Based Models Feature Importances Plot
<p align = "center"> 
  <img src = "https://github.com/hgploutz/food-sales-predictions/blob/main/RandomForestFeatureAnalysis.png">
</p>

Our analysis shows that the price (MRP) of an item has a major role in predicting its final grade. The higher the price, the better we can predict the grade. When our outlets are a specific type – the 'Grocery Store' type – we seem to predict the final grade more accurately. So, the type of store plays a critical role in our predictions. Interestingly, items that aren't as visible have a greater impact on the final grade. So, visibility is not always key. The weight of an item doesn't tip our predictions too much one way or the other, but there's a slight increase in predictability when the weight is around the middle (12.5).

Finally, the establishment year of our outlets does matter. Those established around 1985 tend to have a larger impact on sales. Like a good wine, it seems our outlets improve with age! As always, these findings are based on our current data. If circumstances change, these factors might need to be reassessed.

### Summary Plot - Bar Version
<p align = "center"> 
  <img src = "https://github.com/hgploutz/food-sales-predictions/blob/main/ShapImageBar.png">
</p>

Both our SHAP and Feature Importance charts show us that the price tag (Item_MRP) of an item is really important. Also, whether an outlet is a Grocery Store can change the sales a lot. However, there's a difference when it comes to the third most influential factor. The SHAP chart points to Supermarket Type 3, while the Feature Importance chart tells us that how visible an item is plays a big role. So, depending on the perspective, the third key factor varies.

### Summary plot - Dot Version
<p align = "center"> 
  <img src = "https://github.com/hgploutz/food-sales-predictions/blob/main/ShapImageDot.png">
</p>

Our SHAP dot chart tells us a few things. First, the price tag (Item_MRP) of an item can really change our sales predictions for a single item. The more expensive the item, the bigger its influence on the prediction. Second, whether an outlet is a Grocery Store also makes a big difference. But in this case, being less of a 'Grocery Store' type seems to change our predictions more.

Lastly, if an outlet is a 'Supermarket Type 3', this too can shake things up. Again, being more of a 'Supermarket Type 3' tends to alter our sales predictions more. Remember, these factors don't always matter this much for every prediction, just the particular ones we looked at.


### High MRP Insight
**Shap Force Plot**
<p align = "center"> 
  <img src = "https://github.com/hgploutz/food-sales-predictions/blob/main/HighMRPShap.png">
</p>

We start with a baseline sales prediction of 2,145. Certain characteristics of our outlets and items can adjust this prediction. For example, if the Outlet Type is 0 and the item has a high price (Item MRP), it increases our sales prediction by 266.2, bringing the prediction to 3,424.2.

On the other hand, some features reduce our sales prediction. If an item isn't very visible or if the outlet has been established for a long time, our prediction for sales tends to go down. It's important to remember that this doesn't mean these features are "losing"; they're just contributing in a way that decreases the final sales prediction.

**Lime Tabular Explanation** 
<p align = "center"> 
  <img src = "https://github.com/hgploutz/food-sales-predictions/blob/main/HighMRPlime.png">
</p>

Our model predicted that the sales would be near the lowest possible value, which is 66.06 in this case. To understand why the model made this prediction, we used a tool called LIME. For this particular prediction, it turns out that the item's price (Item MRP) and whether the outlet was a Grocery Store were the deciding factors. Keep in mind, these factors might not always be the key influencers for other predictions, but they were crucial for this one.

### High Visibility Insight
**Shap Force Plot**
<p align = "center"> 
  <img src = "https://github.com/hgploutz/food-sales-predictions/blob/main/HighVisShap.png">
</p>

We start by predicting that sales will be around 2,145. Then, we adjust this prediction based on specific characteristics of our outlets and items.

For example, if an outlet is a type 1 Grocery Store, we would expect our sales to go up, increasing our prediction to 361.28. This isn't about "winning" or "losing," but about how this particular type of store tends to increase sales.

On the flip side, if an outlet was established in 1985, our sales prediction goes down a bit. Again, it's not that this feature is "losing," it just tends to decrease our prediction of what sales will be.


**Lime Tabular Explanation** 
<p align = "center"> 
  <img src = "https://github.com/hgploutz/food-sales-predictions/blob/main/HighVisLime.png">
</p>

Our model guessed that sales would be near the lowest we've seen, around 61.99. To understand why the model made this guess, we used a tool called LIME.

In this specific case, the factors that made the most difference were the type of outlet (if it was a Grocery Store), the item's price, if the store was established in 1985, and if the items were classified as 'Others' or 'Hard Drinks'. These factors were particularly influential in leading the model to its low sales prediction. But remember, these factors might not be as influential in other predictions. They were just key for this one.

## Limitations & Next Steps

From here, a business owner could use these insights to figure out the best method to get the most food sales for their business.


### For further information


For any additional questions, please contact Hannah Ploutz @ **hgploutz@gmail.com**