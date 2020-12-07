# Final Project Write-Up

### Introduction:

  The data we are analyzing were collected using direct questionnaires from patients from the Sylhet Diabetes Hospital that were located in Sylhet, Bangladesh. We found this data through the UCI Machine Learning Repository. Our data is collected from 520 patients from this hospital. The data provides information that points to possible correlations between having diabetes and other factors. These other factors include age, sex, polyuria, polydipsia, sudden weight loss, weakness, polyphagia, genital thrush, visual blurring, itching, irritability, delayed healing, partial paresis, muscle stiffness, alopecia, and obesity. Out of these variables, we had one ordinal variable, which was age. All of the other variables were categorical with either a "yes" or "no" answer. The response variable was "Class", which could either be "positive" or "negative" for diabetes. All of the answers from this questionnaire were approved by a doctor to make it reliable. 
  
  Through this project, we want to understand these possible and common risk factors that are tied to diabetes and to understand any patterns that occur between having diabetes and the presence of risk factors such as old age, obesity, polyuria, polydipsia, and other factors mentioned within the dataset. The main problem that we are trying to tackle is to see the patterns that occur within the data and decipher these patterns. We want to find the patterns that occur with the factors that are presented within the data and the presence of Diabetes within the individual. By finding these patterns, we can flag individuals with similar factors that might indicate that the individual has a high chance of developing diabetes. One of the most important things with overcoming diabetes is early diagnosis, so by finding these patterns that occur between certain factors and having diabetes, we can help find these flags that can lead to an early diagnosis. 

  In conclusion, our main goals were to analyze the various data that was included to make novel, important conclusions about diabetes and related medical conditions. We also wanted to build a predictive model to be able to accurately determine if a specific patient has diabetes given their medical data, history, and symptoms. Additionally, we want to be able to determine which factors out of the variables in our data are the best predictors for if a specific patient will be diagnosed with diabetes or not. 
  
### Model:

In the dataset, out of the 520 patients, 320 of the patients were diagnosed with Diabetes and 200 of the patients were not diagnosed with Diabetes. This is important to know, so we can see the factors that predominantly occured with the 320 patients that were diagnosed versus to 200 patients that were not diagnosed with diabetes. 

#### Correlation Matrix:


#### X^2 Feature Selection

#### Selected Features:
When analyzing the various features we selected, we first came to an initial hypothesis as a group. We then created bar charts to provide an analysis in the specific variable and how this affects the possibility of diagnosis for diabetes. Then, we came to a conclusion based on our analysis of the bar chart. Our conclusion was based on if our bar chart supported or contradict the initial hypothesis, and what our bar chart indicated was the relationship between the variable and the possible diagnosis for diabetes.

##### AGE:

##### GENDER:

<img src="plots/Diabetes_Incidence_by_Gender.png" alt="gender" width="500"/>


##### POLYURIA:
INITIAL HYPOTHESIS:
Polyuria is the production of abnormally large volumes of dilute urine. Our initial hypothesis was that if the patient experienced polyuria, they have a higher chance of being diagnosed with diabetes. We came to this initial hypothesis through some research and prior knowledge. If an individual has diabetes, they tend to havehigher blood suagr levels, and their kedney will try to filter out their high blood sugar levels. This produces a lot of excess urine, leading to polyuria. Out of the 520 patients that were interviewed, 258 had polyuria and 262 did no thave polyuria. 

BAR CHART:

CONCLUSION:
By the bar chart, we can tell that a great number of individuals who were diagnosed with diabetes experienced polyuria. A few patients that were not diagnosed with diabetes also experienced polyuria, but there was a greate difference in the frequencies in the two situations. Due to this great difference, we can come to the conclusion that nearly all patients with polyuria hav diabetes. Therefore, if a patient experienced polyuria, they have a higher chance of being diagnosed with diabetes. This shows us that a possible predictor/indicator for whether an individual has diabetes should definetly be polyuria. Our bar chart also agreed with our initial hypothesis. 

##### POLYDIPSIA:
INITIAL HYPOTHESIS:
Polydipsia is another term for abnormally excessive thirst. Our initial hypothesis for polydipsia was that if an individual expereinced polydipsia, then they have a much higher chance of being diagnosed with diabetes. We came to this hypothesis through prior knowledge. Excessive urine porduction or polyuria can lead to excessive thirst or polydipsia. When the body produces these high level of sugar within the body, the body will produce increased levels of urine to get rid of excess sugar. Due to this increased level of urine production, it can lead to dehydration within the body leading to polydipsia. Out of the 520  patients that were interviewed, 233 said "yes" to experiencing polydipsia, and 287 said "no". 

BAR CHART:

CONCLUSION: 
By looking at the bar chart, we can see that nearly all patients that experienced polydipsia were diagnosed with diabetes. Some individuals that said "no", were also diagnosed with diabetes. However, almost every individual that said "yes" to polydipsia were later diagnosed with diabetes. Our conclusion was that nearly all patients with polydipsia have diabetes. Therefore, if a patient experienced polydipsia, they have a higher chance of being diagnosed with diabetes. This conclusion and the bar chart supports our initial hypothesis because a patient having polydipsia is an important indicator that they might also have diagnosis. Therfore, polydipsia can be used as a predictor/indicator for diabetes due to these patterns. 

##### SUDDEN WEIGHT LOSS:
INITIAL HYPOTHESIS:
Our initial hypothesis for sudden weight loss was that if an individual had recently experienced sudden weight loss, then they have a much higher chance of being diagnosed with diabetes. We came to this hypothesis due to prior knowledge. Insufficient insulin prevents the body from getting glucose from the blood into the body's cells to use as energy. Due to the body not having this instant source of energy, the body must instead use stored fat within the body as a way to get energy. The body starts to burn fat and muscle for energy, causing a reduction in overall body weight. Therefore, we believe that if a patient experiences sudden weight loss, then they have a high chance of being diagnosed for diabetes. Out of the 520 patients that were interviewed, 217 experienced sudden weight loss and 3030 did not. 

BAR CHART:

CONCLUSION:
From the bar chart, we can see that a los of individuals that said yes to experiencing sudden weight loss also were diagnosed for diabetes. There were a few who experienced sudden weight lodd and were still not diagnosed with diabetes. There were also several individuals that did not experience sudden weight loss and were stilll diagnosed with diabetes. Even though, sudden weight loss has a smaller amount of difference between the two values compared to polydipsia and polyuria; however, there is still a significant difference. Therefore, our conclusion was that if a patient has had sudden weight loss, it is very likely that they have diabetes, but the converse is not true. We did not include the second part within the initial hypothesis because we did not really think about the pattern for the converse. However, the first part of our conclusion agrees with our initial hypothesis. Therefore, sudden weight loss can be used as a predictor/indicator of whether the patient will have diabetes or not. 

##### PARTIAL PARESIS:
INITIAL HYPOTHESIS:
Paresis in a condition typifies by a weakness of voluntary movement. We came up with the initial hypothesis that if the individual has partial paresis, then they have a much higher chance of being diagnosed with diabetes. We came up with this hypothesis by using prior knowledge. Diabetes can sometimes lead to nerve damage which can lead to partial paresis in some cases, so we believed that there would be some sort of correlation between the two. There were 224 patients that said "yes" to experiencing partial paresis, and 296 said "no" out of the 520 patients.  

BAR CHART:

CONCLUSION:
According to the bar chart most of the patients that said "yes" to partial paresis were diagnosed with diabetes. There were still several patients that said "no" to partial paresis and still were diagnosed with diabetes. The conclusion we came to was that if a patient has partial paresis, it is very likely that they have diabetes, but the converse is not true. This conlcusion supports our initial hypothesis. Our initial hypothesis did not mention the converse; however, the first part of our conclusion still supports our initial hypothesis.  





### Conclusion:
