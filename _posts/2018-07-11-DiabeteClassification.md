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

The first 5 rows show that there are many zero value in some columns, because we can't have biological
data with zero, I considered it as Nans.     
```python
   import numpy as np
   import pandas as pd
   ## Read the file
   df = pd.read_csv('pima-indians-diabetes.data.txt', names = ['Number_times_pregnant','PlasmaGlu', 
   'Dbpressure', 'Tricep_thickness', 'Hour_serum_insulin','Bmi', 'Dpfunction', 'Age', 'Class variable'])
   ## Read the first 5 rows
   df.head()
```   
Here's the first rows.             
<img src="{{ site.url }}{{ site.baseurl }}/images/diabetes/head_diabete.JPG" alt="" width="680" height="400">      
I choose to replace all the 0/nans with the median by each class.            
```python
   ## Imputing nans with median from each class
   df1 = df1.fillna(df1.groupby('Class variable').transform('median'))
```   
Here's the first rows after imputing.
<img src="{{ site.url }}{{ site.baseurl }}/images/diabetes/head_after_imp.JPG" alt="" width="680" height="400">      

Just to remember, we have 2 classes: 0 and 1.
I used five algorithms from scikit learn package: KNeighbors, Random Forest, Gaussian NB, ExtraTrees and DecisionTree. Here is the accuracy on the training set.            
 
<img src="{{ site.url }}{{ site.baseurl }}/images//diabetes/acc_target.JPG" alt="" width="380" height="200">           
        
Random forest model and decision tree gave the highest accuracy around 88% and we can have also the most important predictors.    
Let's examine also the confusion matrix. We have:
- True negative (TN) = 139
- True positive (TP) = 63
- False negative (FN) = 18
- False positive (FP) = 11                                  

Because it's better to predict a person which is negative as positive than a person which is positive as negative, the worse case here would be FN. So, in this case recall is a better metric, let's calculate it. Recall is, out of the positive class, how many did I correctly predict as positive?      
Recall = TP / FN + TP -> 63 / (18+63) which is 0.78   
And precision, out of the cases I predicted be positive, how many are really positives?  
Precision = TP / FP + TP -> 63 / (11+63) which is 0.85       
This is not so good because recall should be higher than precision for this problem.  
<img src="{{ site.url }}{{ site.baseurl }}/images//diabetes/conf_Mat_Dia.png" alt="" width="380" height="200"> 

<h3> What about the weight of the 5 most important features? </h3>        
<img src="{{ site.url }}{{ site.baseurl }}/images/diabetes/imp_feat_Diabete.png" alt="" width="680" height="400">   

The most important features to predict diabetes are : 2-Hour serum insulin (mu U/ml), Triceps skin fold thickness (mm) and Plasma glucose concentration a 2 hours in an oral glucose tolerance test. 
Indeed, these are important parameters to evaluate diabetes.

