---
title: "Red Wine Classification (with Python)"
date: "Monday, April 02, 2018"
tags:
  - red wine
  - Classification
  - Python
  
---

<p><img src="{{ site.url }}{{ site.baseurl }}/images/vino.jpg" alt="image-center" class="align-center" /></p>    

## Can we use the physicochemical characteristics of a wine to predict his quality?
 
From the last post, we will continue with the wine dataset. Here, I will apply machine learning technique to classify it. Just to remember, we have 3 categories: low, medium and high.
I used five algorithms from scikit learn package: KNeighbors, Random Forest, Gaussian NB, ExtraTrees and DecisionTree. Here is the accuracy on the training set.
 
<img src="{{ site.url }}{{ site.baseurl }}/images/wine/accuracy.png" alt="" width="680" height="400">
        
The random forest model gives the highest accuracy around 88% on the training set and we can have also the most important predictors.    

<h3> What about the weight of the 5 most important features? </h3>        
<img src="{{ site.url }}{{ site.baseurl }}/images/wine/important_feature.png" alt="" width="680" height="400">        
The most important features for red wine classification are : alcohol, volatile acidity, sulphates, density and total sulfur dioxide. Indeed, these are important parameters to evaluate the quality of a wine.
