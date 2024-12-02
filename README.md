# Model Prediction For oil Palm Production

Develop  a  model  that  predicts  monthly  oil  palm  production  for  January,  February  and  March  2024.  
<br/>
View jupyter notebook using this link, since github no longer support ipynb view:https://colab.research.google.com/drive/1V0kY5FRyqwUEUr9YYZP_tpqnVykghJ75?usp=sharing
<br/>


## Parameter
<br/>• Production data have yearly seasonality. The duration of oil palm fruit production takes up to 
36 months. 
<br/>• Production  is  associated  with  its  age  (growth),  with  no  production  from  age  0  –  3,  low 
production slowly increasing from age 4 – 8, optimal production from age 9 – 15, plateauing 
production from age 16 – 20, and drop in production from age 21 onwards. 
<br/>• Production is affected by how many palms is planted in an area. Generally a bigger area would 
have more palm stand. 
<br/>• Fertiliser is a key important input for oil palm to produce fruit. Fertiliser is applied throughout 
the year with only some month having fertiliser applied. Study have shown fertiliser applied 
up to past 24 months ago can affect the production. 
<br/>• Rainfall  have  major  effects  on  production,  in  deficit  or  excessive  amount.  Monthly  rainfall 
exceeding 300mm or less than 100mm for consecutive  3 months will have severe  effect on 
the  production.  Study  have  shown  that  past  rainfall  up  to  24  months  ago  can  affect  the 
production

# Hypothesis Testing
refer the H_testing.ipynb for ref.

## Seasonality 
Oil palm production exhibits yearly seasonality due to climatic patterns and biological growth cycles. to test, we analyze production data across months and years to identify repeating patterns or cycles.

**Null Hypothesis (H₀):** There is no yearly seasonality in oil palm production data.
<br/>
**Alternative Hypothesis (H₁):** There is yearly seasonality in oil palm production data.

Decomposing the production data into trend, seasonal, and residual components using additive decomposition <br/>
![image](https://github.com/user-attachments/assets/8151119b-168e-45f6-961e-f9cb0ef489c9)
<br/> Autocorrelation function (ACF) to detect seasonality. <br/>
![image](https://github.com/user-attachments/assets/c45a029d-36bf-4989-acc7-41b80ab83a9f)

Given the evidence from the decomposition plot and the ACF plot, we reject H₀ and accept H₁, confirming that there is a yearly seasonal pattern in the data.

## Age Groups and Production
Null Hypothesis (H₀): There is no significant difference in production across different age groups.
<br/>
Alternative Hypothesis (H₁): There is a significant difference in production across different age groups.


Compare mean production across age groups with ANOVA <br/>
![image](https://github.com/user-attachments/assets/26f4f415-31db-49ad-b20e-d95ed726cb84)
<br/> ANOVA F-statistic: 0.10, p-value: 0.9026

p-value < 0.05 indicates significant differences between groups. Since p-val > 0.05, Accept H₀, no significant difference in production across different age groups.


## Effect of Palm Stand on Production
Null Hypothesis (H₀): The number of palm stands does not affect production.
Alternative Hypothesis (H₁): The number of palm stands affects production.
<br/>
use Multiple Regression Analysis that nclude lagged fertilizer variables as predictors.
<br/>
Result:
Pearson correlation coefficient: 0.02

Significant coefficients < 0.05 indicate an effect. Since it is < 0.05, reject null hypothesis, and accept alt hypothesis, where The number of palm stands affects production.


## Effect of Rainfall 
Null Hypothesis (H₀): Extreme rainfall conditions do not affect production.
<br/>
Alternative Hypothesis (H₁): Extreme rainfall conditions affect production.

we use regression analysis to assess the impact
![image](https://github.com/user-attachments/assets/fef0705c-da8c-472c-a21a-41c7cda437d7)

p-value < 0.05 (-1.9291), we reject H₀ and accept H₁.

# Prediction result

![image](https://github.com/user-attachments/assets/b9d1f0c8-7e60-4f64-9254-fe6e42572f0f)
![image](https://github.com/user-attachments/assets/e2ab03b7-777e-4183-ba5a-2ca5681fa016)

