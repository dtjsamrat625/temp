---
title: 'Ch.2 Exercises: Statistical Learning'
output:
  html_document: default
  pdf_document: 
    latex_engine: lualatex
  word_document: default
---

#### __Conceptual__

__1.__

__(a)__ 

- **Better** : A large sample size means a flexible model will be able to better fit the data.

__(b)__

- **Worse** : A flexible model would likely overfit. Flexible methods generally do better when large datasets are available.

__(c)__

- **Better** : Flexible methods perform better on non-linear datasets as they have more degrees of freedom to approximate a non-linear 

__(d)__

- **Worse** : A flexible model would likely overfit, due to more closely fitting the noise in the error terms than an inflexible method. In other words, the data points will be far from $f$ (ideal function to describe the data) if the variance of the error terms is very high. This hints that f is linear and so a simpler model would better be able to estimate $f$.


__2.__

__(a)__

  - **Regression**;The response in this case is quantitative and so this is a regression problem.
  - **Inference**; We want to understand how the predictors impact the salary of a CEO, and not actually predict the salary of a CEO. Therefore, inference is our aim. 
  - n=500. p=profit, number of employees, industry. 

__(b)__

  - **Classification**; response(success or failure) is a binary value.
  - **Prediction**; we want to know predicted value of the target. 
  - n=20. p=price, marketing budget, competition price and 10 other variables.
  
__(c)__

  - **Regression**; response(% change in the USD/Euro) is a quantitative value. 
  - **Prediction**, we want to predict the response. 
  - n=52. p=% change in US market, % change in UK market, % change in German market.


__3.__

__(a)__

```{r echo=FALSE, out.width = '100%'}
knitr::include_graphics("/Users/Home PC/OneDrive/Introduction_to_Statistical_Learning/ISLR_lab_r/Ex2Q3.png")
```


__(b)__

  - Var(E) is the irreducible error and the test predictions cannot be better than this, therefore it is a straight line. Test MSE reduces to an optimum point as increased flexibility means a better fit, with further increases leading to overfitting. Training MSE continues to reduce as more flexibility means the method can very closely fit the training data. Variance increases as the method tends to overfit as flexibility increases (fitting training data too well and not generalizing to test data). Generally, bias is reduced as the flexibility increases due to the method being better able to fit the data. 

__4.__

__(a)__

**Classification methods would be useful for applications where the outcomes are to be classified into a category, this can be a binary classification or a multi-class classification. Some areas where classification could be useful:**

  - **Breast cancer prediction:** Given a set of predictors such as a mammogram scan, age, family history, lifestyle and other variables, and a response of *Yes*(has cancer) and *No*(does not have cancer) ??? we can then train a model to predict whether a patient has breast cancer.
  
  - **Classifying species of plants:** Given a set of images of a plant, a model can be trained that will classify that plant into one of the trained species. This is a multi-class classification problem. The response would be the species name and the predictors would be images of that species.
  
  - **Fraud detection:** Classify whether a transaction is fraudulent, given data like the transaction amount, location, purchased item or service, previous customer transactions etc. The response would be "Yes" or "No", and our aim is to make a prediction.
  
  - **Stock price:** Classify whether a stock will go up or down in price the next day given a set of financial data and news from the preceding week. The aim is to make a prediction.
  
__(b)__

**Regression methods are useful when we have a quantitative response; that is where we need to predict a numerical value for our response. Some areas where regression could be useful are:**


  - **House price factors:** Given a set of predictors such as location, house features, median income for the area and so on and the house price as the response/target, we can train a model to infer the impact of those variables on house prices. 
  
  - **Salary:** Predict the salary of an individual given their education, work history, skillsets and other relevant data (age, sex, etc.). The response is the salary amount. 
  
  - **Sales:** Predict unit sales of a product given marketing data such as TV, Radio or Internet advert expenditure, and use it to infer the importance of each advertising method. The response is the unit sales of the product.
  
  - **Driving Insurance premium:** Given a set of variables such as the drivers history, age, type of vehicle, expected yearly mileage and the premium as the response, we can train a model to predict the insurance premium for new customers. 
  
__(c)__

**Cluster analysis is useful in cases where we do not have a target response available ??? i.e. unsupervised learning. We can aim to ascertain whether observations can be classed into distinct groups or understand if there are any underlying relationship between variables. Some areas where this can be useful are:**

  - **Tissue classification:** : Clustering can be used to separate different types of tissue in medical images. This can be useful in identifying groups of tissue that are not normal and need further study.
  
  - **Market research:** Differentiate a group of people within a city into distinct market segments to increase marketing effectiveness or identify new opportunities. Given data such as incomes, location, age, sex, opinion polls and so on for a city, we can segment the city into different consumer areas.
  
  - **Image segmentation:** Separate an image into different regions to make object recognition easier. For example, segmenting image frames from a video camera in a car into 'other vehicles', 'humans', 'road signs' and so on can help ADAS (Advanced driver-assistance systems) in vehicles make the correct decision. 
  
  - **Gaming market segmentation:** Given a set observations with variables such as age, location, income, sex, hours spent gaming, gaming devices used and so on. We could use cluster analysis to see if these observations fall into distinct groups. If there are distinct groupings, then it could be helpful with further study ??? say for example one grouping could represent casual gamers and the other hardcore gamers, and another one could be newer gamers (say people over the age 60).


__5.__ & __6.__

  - Flexible methods work well when the underlying function is non-linear. The predictions in general have a lower bias but can have a higher variance, as these models are more likely to overfit the data. 
  
  - Less flexible methods do not tend to overfit the data but can have a high bias when the underlying function is non-linear. They can also use fewer observations and parameters, particularly when it is assumed that the underlying function is linear. Flexible methods tend to require a larger number of observations and parameters, and can lead to overfitting (higher variance). 
  
  - Flexible methods (non-parametric methods) are preferable when we make no assumptions about the function to be estimated.Most real-life relationships are non-linear and so a non-parametric approach is better suited to modelling them. Flexible models by their nature are more complex and less interpretable than their linear counterparts, so even though their predictions might be more accurate, we may not be able to explain why it has made those predictions (a black box model).
  
  - Less flexible methods (parametric) are useful if we assume or know that the underlying function is linear. As a linear relationship is assumed, the model needs to predict fewer parameters than a non-parametric method. Additionally, these models are more interpretable, and so will be preferred when we are interested in making inferences or the interpretability of the results. 
  
__7.__
__(a)__
The Euclidean distance is the straight line distance between two points. This can be calculated using the Pythagorean theorem.

For 3D space we have:

  $$d(p,q) = \sqrt{(p_1-q_1)^2 + (p_2-q_2)^2 + (p_3-q_3)^2}$$
Using the above formula, we get the following distances:


$$
\begin {aligned}
d(1,test) &= 3\\
d(2,test) &= 2\\
d(3,test) &= 3.16\\
d(4,test) &= 2.24\\
d(5,test) &= 1.41\\
d(6,test) &= 1.73\\
\end {aligned}
$$


__(b)__ 

  - **Green**; as nearest single observation is green.

__(c)__

  - **Red**; as nearest three observations are green, red and red.The probability of the test point belonging to red is 2/3 and green is 1/3. Therefore, the prediction is red.

__(d)__

 - For highly non-linear boundaries, we would expect the best value of K to be small. Smaller values of K result in a more flexible KNN model, and this will produce a decision boundary that is non-linear. A larger K would mean more data points are considered by the KNN model and this means its decision boundary is closer to a linear shape.
  
#### __Applied__

__8.__
```{r}
library(ISLR)
#library(ggplot2)
```

__(a)__ __(b)__

```{r}
college.rownames = rownames(College)
```

__(c)__
**i.**
```{r}
summary(College)
```

**ii.**
```{r fig.width=10, fig.height=8}
# Pair plot of first 5 variables
pairs(College[,1:5])
```

**iii.**
```{r fig.width=10, fig.height=8}
# Boxplots of outstate vs Private.
boxplot(Outstate~Private, data = College)
```

**iv.**
```{r}
# New variable 'Elite'
Elite = rep("No",nrow(College))
Elite[College$Top10perc>50] = "Yes"
college.df = data.frame(College, Elite)

summary(college.df)
```

  - There are 78 elite universities.

```{r fig.width=10, fig.height=8}
boxplot(Outstate~Elite, data = college.df)
```


**v.**
```{r fig.width=10, fig.height=8}
par(mfrow=c(2,2))
hist(College$Apps, xlim=c(0,25000), xlab = "Applications", main = "Apps using default bin sizes")
hist(College$Apps, xlim=c(0,25000), breaks=25, xlab = "Applications", main = "Apps using smaller bin sizes")
hist(College$Top10perc, breaks=25, xlab = "Pct. new students from top 10% of H.S. class",main="Top10Perc")
hist(College$Outstate, xlab="Out-of-state tuition",ylab="Amount",main="Outstate")
```

  - Histogram of Apps(Number of applications received) is highly right skewed. This shows that most universities received 5000 or fewer applications. The mean number of applications received will also be heavily skewed.
  
  - Histogram for Top10Perc(Number of new students who are the top 10% of their class) is also right skewed; this shows that only a few universities get a majority of their new students from this cohort.
  
```{r}
mean(college.df$Apps)
median(college.df$Apps)
```

**vi.**
```{r fig.width=10, fig.height=8}
# Exploring the relationship between Grad.Rate(Graduation Rate) and S.F.Ratio(Student/faculty ratio).
plot(college.df$S.F.Ratio, college.df$Grad.Rate, 
     xlab = "Student to Faculty Ratio", ylab = "Graduation Rate",
     main = "Plot of Grad.Rate vs S/F Ratio")

# Linear regression line.
abline(lm(college.df$Grad.Rate~college.df$S.F.Ratio), col="red")

# Local regression line with smoothing of 25%.
loessMod = loess(Grad.Rate ~ S.F.Ratio, data=college.df, span=0.25)
j = order(college.df$S.F.Ratio)
lines(college.df$S.F.Ratio[j],loessMod$fitted[j], col="blue")
```

  - The results suggest a negative linear relationship between the graduation rate of students and the student to faculty ratio at universities.
  - As the student to faculty ratio increases, we can expect students to have a lower graduation rate.


__9.__

__(a)__

  - **Quantitative**: mpg,cylinders,displacement,horsepower, weight, acceleration, year.
  - **Qualitative**: name, origin.

__(b)__

```{r}
sapply(Auto[,1:7], range)
```


__(c)__

```{r}
# Mean and standard deviation.
sapply(Auto[,1:7], mean)
sapply(Auto[,1:7], sd)
```


__(d)__

```{r}
# Remove 10th to 85th rows from Auto.
Auto.reduced = Auto[-c(10:84),]
sapply(Auto.reduced[,1:7], range)
sapply(Auto.reduced[,1:7], mean)
sapply(Auto.reduced[,1:7], sd)
```

__(e)__

```{r fig.width=10, fig.height=8}
pairs(Auto[,1:7])
```

```{r}
cor(Auto[,1:7])
```

  - From the pair plot and the correlation data, we can state there exists linear relationships between some of the variables.
  - For example, `mpg` has strong negative linear relationships with `displacement`, `cylinders` and `weight`. That is we can expect the `mpg` of the car to decrease as their `displacement` and `cylinders` increase.
  - `mpg` has a positive correlation with `year`, and this suggests that newer models tend to have higher `mpg` than older ones.

__(f)__

  - Both the plots and the correlation data suggests we can predict mpg.
  - An increase in the variables `displacement`, `cylinders` and `weight` will lead to a reduced `mpg`.
  - Newer models `year` tend to have higher `mpg`.

__10.__

__(a)__
```{r}
library(MASS)
```

?Boston

```{r}
dim(Boston)
```
  
  - 506 rows of suburbs or towns and 14 columns of predictors.  

__(b)__
```{r fig.width=10, fig.height=8}
# Pair plots of some variables
pairs(~crim+nox+dis+tax+medv, data = Boston)
```
  
  - `crim` seems to have a negative linear relationship with `medv` and `dis`.
  - `nox` has a negative linear relationship with `dis`.
  - `dis` has a positive linear relationship with `medv`.

__(c)__ 

```{r}
# Correlation coefficients between CRIM and all other variables.
cor(Boston[-1],Boston$crim)
```

  -  There are some correlations between `crim` and other variables, but they are not as strong as some of the relationships we observed in the `Auto` dataset.
  - `crim` has a negative linear relationship with `medv`, `dis` and `black`.
  - `crim` has a positive linear relationship with `indus`, `nox`, `rad` and `tax`.

__(d)__

```{r}
# Suburbs with crime rate higher than 2 s.d from the mean(higher than 95% of suburbs).
High.Crime = Boston[which(Boston$crim > mean(Boston$crim) + 2*sd(Boston$crim)),]
range(Boston$crim) ; mean(Boston$crim) ; sd(Boston$crim)
```
  
  - There are 16 suburbs with a crime rate higher than 95% of the other suburbs.
  - Some suburbs have extremely high rates of crime (5-8 s.d from the mean).
  - The range is very wide, it goes from a rate of near zero to 89.

```{r}
# Suburbs with tax rates higher than 2 s.d from the mean.
High.Tax = Boston[which(Boston$tax > mean(Boston$tax) + 2*sd(Boston$tax)),]
range(Boston$tax)
```
 
 - There are no suburbs with a tax rate higher than 2 s.d. from the mean. This seems reasonable as property tax rates are designed not to be extremely drastic.
 - The range is narrower than the crime rate.
 - Some suburbs do have tax rates higher than 1 s.d.(higher than 65% of suburbs) from the mean.

?Boston
```{r}
# Suburbs with pupil teacher ratio higher than 2 s.d from the mean.
High.PT = Boston[which(Boston$ptratio > mean(Boston$ptratio) + 2*sd(Boston$ptratio)),]
range(Boston$ptratio)
```

  - There are no suburbs with a high pupil to teacher ratio, and this a reasonable outcome as educational laws limit the numbers of teacher or students per class/school.
  - The range in quite narrow, and and all pupil teacher ratios lie within 2 s.d. of the mean.
  - Some pupil teacher ratios are higher than 1 s.d.


__(e)__

```{r}
sum(Boston$chas==1)
```

  - 35 suburbs/towns bound the Charles river.
  
__(f)__

```{r}
median(Boston$ptratio)
```

__(g)__

```{r}
which(Boston$medv == min(Boston$medv))
```

   - There are two suburbs (399 & 406) that have the lowest median property values.
   
   
```{r}
# Values of other predictors for suburb 399
Boston[399,]
```


```{r}
range(Boston$lstat)
range(Boston$ptratio)
```
  
  - `crim` is more than 2 s.d. above the mean - very high crime rates in this suburb. Both `ptratio`and `lstat` are close to their maximum values.
  
__(h)__

```{r}
# More than 7 rooms
sum(Boston$rm > 7)
```
```{r}
# More than 8 rooms
sum(Boston$rm > 8)
```

```{r}
summary(Boston)
summary(subset(Boston, rm > 8))
```

  - Relatively low `crim`, `lstat` and much higher `medv` when comparing the IQR range.
