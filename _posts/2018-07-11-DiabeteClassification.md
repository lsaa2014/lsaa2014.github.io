---
title: "Pima Indians Diabetes Classification (with Python)"
date: "Wenesday, July 07, 2018"
tags:
  - Diabetes
  - Pima Indians
  - Classification
  - Python
  
---

<p><img src="{{ site.url }}{{ site.baseurl }}/images/diabetes/pima indians.jpeg" alt="image-left" class="align-left" width="150" height="150"/></p>   

## Use machine learning to predict if a female will be tested positive or not for Diabete?           
 
From the last post, we will continue with the diabetes dataset.    
```python
   import numpy as np
   import pandas as pd
   ## Read the file
   df = pd.read_csv('pima-indians-diabetes.data.txt', names = ['Number_times_pregnant','PlasmaGlu', 
   'Dbpressure', 'Tricep_thickness', 'Hour_serum_insulin','Bmi', 'Dpfunction', 'Age', 'Class variable'])
   ## Read the first 5 rows
   df.head()
```   
The first 5 rows show that there are many zero value in some columns, because we can't have biological
data with zero, I considered it as Nans. Here's the first rows.             
<img src="{{ site.url }}{{ site.baseurl }}/images/diabetes/head_diabete.JPG" alt="" width="680" height="400">      
I choose to replace all the 0/nans with the median by each class.            
```python
   ## Imputing nans with median from each class
   df1 = df1.fillna(df1.groupby('Class variable').transform('median'))
```   
Here's the first rows after imputing.
<img src="{{ site.url }}{{ site.baseurl }}/images/diabetes/head_after_imp.JPG" alt="" width="680" height="400">      

Just to remember, we have 2 classes: 0 and 1.
I used five algorithms from scikit learn package: KNeighbors, Random Forest, Gaussian NB, ExtraTrees and DecisionTree. Here is the accuracy.            
 
<img src="{{ site.url }}{{ site.baseurl }}/images//diabetes/acc_target.JPG" alt="" width="680" height="400">           
        
Random forest model and decision tree gave the highest accuracy around 88% and we can have also the most important predictors.    
Let's examine also the confusion matrix.            
<img src="{{ site.url }}{{ site.baseurl }}/images//diabetes/acc_target.JPG" alt="" width="680" height="400">        


<h3> What about the weight of the 5 most important features? </h3>        
<img src="{{ site.url }}{{ site.baseurl }}/images/diabetes/imp_feat_Diabete.png" alt="" width="680" height="400">        
The most important features to predict diabetes are : 2-Hour serum insulin (mu U/ml), Triceps skin fold thickness (mm) and Plasma glucose concentration a 2 hours in an oral glucose tolerance test. 
Indeed, these are important parameters to evaluate diabetes.

