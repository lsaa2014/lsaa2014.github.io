---
title: "EDA of Breast Cancer University of Coimbra (with R)"
date: "Tuesday, October 30, 2018"
tags:
  - Breast Cancer
  - EDA
  - R
  - University of Coimbra
  
---

<p><img src="{{ site.url }}{{ site.baseurl }}/images/breast_cancer/breastCancer.jpg" alt="image-left" class="align-left" width="150" height="150"/></p>   

## Background    
Breast cancer is an uncontrolled growth of epithelial cells originating in the ducts or breast lobules Carbone et al (1993). Breast cancer is the primary cause of cancer in women, accounting for one-third of all cancers. It is important to use routine blood analysis for breast cancer diagnosis.

## Data  
In this is exploratory analysis, I will use Breast Cancer data set from University of Coimbra. The data is from the [Uci archive](https://archive.ics.uci.edu/ml/datasets/Breast+Cancer+Coimbra#) using R. The paper can be found [here](https://bmccancer.biomedcentral.com/articles/10.1186/s12885-017-3877-1)

This data consist of 116 observations of 10 variables. The variables are:   
1. Age (years) 
2. BMI (kg/m2) 
3. Glucose (mg/dL) 
4. Insulin (µU/mL) 
5. HOMA 
6. Leptin (ng/mL) 
7. Adiponectin (µg/mL) 
8. Resistin (ng/mL) 
9. MCP-1 (pg/dL)     
10. Class variable (1 or 2) (1 means Healthy controls and 2 Patients)       
The class variable is the dependent or response variable. 

On this analysis, I want to respond to two questions:      
   1. Can Glucose, resistin and BMI can be used as biomarkers of breast cancer?    
   2. Is there a relationship between resistin and MCP-1?  
The original data has 500 tested negatives and 268 positives after removing the missing values, we have 262 tested negatives and 130 positives.
 
### Can Glucose, resistin and BMI can be used as biomarkers of breast cancer?
- BMI         
<img src="{{ site.url }}{{ site.baseurl }}/images/breast_cancer/ecdf_bmi.png" alt="" width="680" height="400">        

On the above plot, we can see the empirical cumulative distribution function (ECDF) of BMI. It shows for any given number the percent of individuals that are below that threshold. We can see that for BMI equals to 32.5, we have around 75% of healthy below that value and 87.5% of unhealthy below it. In other word, there are more (25%) healthy people with BMI above 32.5 than unhealthy (12.5%).

- Glucose and resistin      
<img src="{{ site.url }}{{ site.baseurl }}/images/breast_cancer/glucose_resistin_by_class.png" alt="" width="680" height="400">        
This plot shows that both glucose and resistin are higher on unhealthy patients than healthy.

### Is there a relationship between resistin and MCP-1? 
<img src="{{ site.url }}{{ site.baseurl }}/images/breast_cancer/resistin_mcp.png" alt="" width="680" height="400">        
There is a moderately strong relationship between resistin and MCP-1.

 
## To conclude
From this analysis, we can see that Glucose, resistin and BMI could be used as biomarkers of breast cancer.
