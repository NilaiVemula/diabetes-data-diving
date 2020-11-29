# Final Project Write-Up

### Introduction:

  The data we are analyzing were collected using direct questionnaires from patients from the Sylhet Diabetes Hospital that were located in Sylhet, Bangladesh. Our data is collected from 520 patients from this hospital. The data provides information that points to possible correlations between having diabetes and other factors. These other factors include age, sex, polyuria, polydipsia, sudden weight loss, weakness, polyphagia, genital thrush, visual blurring, itching, irritability, delayed healing, partial paresis, muscle stiffness, alopecia, and obesity. Our data shows the patient’s age, sex, and whether they have experienced any of the above factors, and how this data pertains to whether the individuals are Positive or Negative for Diabetes. All of the answers from this questionnaire were approved by a doctor to make it reliable. 
  
  Through this project, we want to understand these possible and common risk factors that are tied to diabetes and to understand any patterns that occur between having diabetes and the presence of risk factors such as old age, obesity, polyuria, polydipsia, and other factors mentioned within the dataset. The main problem that we are trying to tackle is to see the patterns that occur within the data and decipher these patterns. We want to find the patterns that occur with the factors that are presented within the data and the presence of Diabetes within the individual. By finding these patterns, we can flag individuals with similar factors that might indicate that the individual has a high chance of developing diabetes. One of the most important things with overcoming diabetes is early diagnosis, so by finding these patterns that occur between certain factors and having diabetes, we can help find these flags that can lead to an early diagnosis. 
  
### Model:

In the dataset, out of the 520 patients, 320 of the patients were diagnosed with Diabetes and 200 of the patients were not diagnosed with Diabetes. This is important to know, so we can see the factors that predominantly occured with the 320 patients that were diagnosed versus to 200 patients that were not diagnosed with diabetes. 

The response variable is class, and all other variables are predictors. All predictors are categorical except for Age which is a ordinal variable. The categorical predictors include "Yes" or "No" indicating whether each patient has experienced the specific factor. 

#### Correlation Plot:
![](notebooks/corrplot.png)

#### Age:

There does not appear to be a very large difference in diabetes status based on age.
One of the factors we chose to explore was the Age. Through this plot we chose to  



### Conclusion:
