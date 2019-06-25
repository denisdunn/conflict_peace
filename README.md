# conflict_peace
Overview:

  This project analyzes disputes between countries in an 18 year time span.  I wanted to see if i could predict whether disputes between countries would result in some sort of military action or if the dispute would result in nothing but threats. I used data sets from the Correaltes of War project. They have brought together different datasets ranging from military power, diplomatic & allie relations, etc. I took features from a few different data sets to see if I could predict military action from a dispute. I was able to predict conflicts with high accuracy and an f1 score of .74.
  
Data description:

  I engineered a few features from the datasets, connecting diplomatic relationships on certain levels and allied relationships to build three general variables: US Allies, Russian Allies, China Allies. The thinking is that having a relationship with one of the three superpowers might affect how a dispute is going to end up. There were over 8,000 disputes in an 18 year span. Here is a list of the variables used in the project:
  
  
![Plot](https://github.com/denisdunn/conflict_peace/blob/master/Screen%20Shot%202019-05-10%20at%208.51.52%20AM.png)


Models:

  I used Smote to handle a slight class imbalance. The models I tested the analysis on were: logistical, decision tree, random forest, adaboost, xgboost,gradient boosted trees.
After tweaking the parameters on each model, I found that the bagged decision tree was the best. It surprisinly beat out the random forest. There is a minor difference between the two. A random forest takes out one different variable for each tree to create the random forest. This cuts down on variance, which may have led to overfitting. I kept all the variables in the random forest model and was able to generate a slightly higher f1score and a better confusion matrix. here is the scoring before and after some parameter tweaking:
![Plot](https://github.com/denisdunn/conflict_peace/blob/master/Screen%20Shot%202019-05-10%20at%209.26.25%20AM.png)
![Plot](https://github.com/denisdunn/conflict_peace/blob/master/Screen%20Shot%202019-05-10%20at%209.28.57%20AM.png)

Here is the confusion matrix to go along with the bagged decision tree. I thought that the best mistake would be to say if there was a false positive vs a false negative. Being ready for war instead of unprepared..
![Plot](https://github.com/denisdunn/conflict_peace/blob/master/Screen%20Shot%202019-05-10%20at%2010.30.35%20AM.png)


Analysis:

  It isn't surprising that fatalities on the initial dispute is the biggest factor that could lead to a military action, but it is interesting to see the other higher ranking features. In the feature chart below you will see that urban population, imports and energy consumption are the next highest ranking features. All three variables seem to be very vurnerable to world trade dynamics. 
![Plot](https://github.com/denisdunn/conflict_peace/blob/master/Screen%20Shot%202019-05-10%20at%2010.14.02%20AM.png)

Next steps:
  I am going to find additional exogenous variables to add to the models.
