# oumaima-gasmi-About-Logistic-Regression-Project-What-Your-Heart-Rate-Is-Telling-You
About Logistic Regression Project What Your Heart Rate Is Telling You
   
What Your Heart Rate Is Telling You
Examine the relationship between heart rate and heart disease using multiple logistic regression.


Heart disease is the leading cause of death in the United States. Researchers are using several data mining techniques to 

help health care professionals in the diagnosis of heart disease. In this project, you will examine the relationship between 

the maximum heart rate one can achieve during exercise and the likelihood of developing heart disease. Using multiple 

logistic regression, you will handle the confounding effects of age and gender.

This project uses the Cleveland heart disease dataset.

Project Tasks

1. Heart disease and potential risk factors

2. Converting diagnosis class into outcome variable

3. Identifying important clinical variables

4. Explore the associations graphically (i)
5. Explore the associations graphically (ii)

6. Explore the associations graphically (iii)

7. Putting all three variables in one model

8. Extracting useful information from the model output

9. Predicted probabilities from our model

10. Model performance metrics


Task 1: Instructions
Load the data into our notebook.

Use the read.csv() function to read in our dataset ("datasets/Cleveland_hd.csv") and save as hd_data.
Use the head() function to print out the top 5 rows of the data.
Good to know
In this project, you'll brush up on the skills you learned in Multiple and Logistic Regression and Introduction to the Tidyverse, including basic data explorations with ggplot2 and dplyr.

Helpful links:

RStudio's Data Wrangling cheat sheet
RStudio's ggplot2 cheat sheet
read.csv() documentation



Task 2: Instructions
Recode the class and sex variables.

Load the tidyverse package.
Use the mutate()function to recode any > 0 value in the class variable to be 1 and all 0 values to remain 0. Save this new variable as hd.
Use the mutate() function along with factor() to update sex (originally 0 or 1) to a factor with labels "Female" and "Male".
Helpful links:

Mutate verb from Introduction to the Tidyverse
ifelse() documentation
factor() documentation



Task 3: Instructions
Explore bi-variate correlations using a t-test or a chi-squared test.

Use chisq.test() to assess the relationship between sex and hd and save the output as hd_sex.
Use t.test() to assess the relationship between age and hd and save the output as hd_age.
Use t.test() to assess the relationship between thalach and hd and save the output as hd_heartrate.
Check the above results using print().
Helpful links:

chisq.test() documentation
t.test() documentation



Task 4: Instructions
Recode the outcome hd variable and plot it vs. age on a boxplot.

Label hd (0/1) as "No Disease" and "Disease" using the ifelse() function to create the new variable, hd_labelled.
Generate a boxplot with hd_labelled on the x-axis and age on the y-axis.
Helpful links:

Mutate verb from Introduction to the Tidyverse
Boxplot exercises from Introduction to the Tidyverse



Task 5: Instructions
Plot hd_labelled vs. sex on a barplot.

Generate a barplot with hd_labelled on the x-axis and sex as the fill. Set position="fill" in geom_bar(). Add a ylab() with the label "Sex %" (one space between Sex and %).

Helpful links:

Barplot exercises from Introduction to the Tidyverse


Task 6: Instructions
Plot hd_labelled vs. thalach on a boxplot.

Generate a boxplot with hd_labelled on the x-axis and thalach on the y-axis.
Helpful links:

Boxplot exercises from Introduction to the Tidyverse



Task 7: Instructions
Fit a logistic regression model with all three variables.

Use glm() to fit the model (predicting hd using age, sex, and thalach) to save to model. Set the family parameter to 'binomial'.
Get the summary from the model object.
We specify the correct error distribution using the family argument. In this case, 'binomial' is appropriate because we are working with a binary outcome.

Helpful links:

glm() documentation
How to fill out the formula parameter in glm(), via the formula() documentation



Task 8: Instructions
Use the broom package to tidy up the model output.

Load the broom package.
Apply the tidy() function on the model object created previously and save as tidy_m.
Calculate Odds Ratios (ORs) by exponentiating the estimate column.
Calculate the normal approximation for the upper bound of the 95% Confidence Interval (CI) for ORs.
Helpful links:

Introduction to broom

Normal approximation CI


Task 9: Instructions
Extract the predicted probability in the current dataset. In addition, apply the model to predict outcomes on new cases.

Apply the predict() function.
Using ifelse(), create a decision rule for pred_prob >= 0.5 and save the predicted decision (either 1 or 0) as pred_hd.
Using predict(), predict probability of HD on the provided newdata case and save as pred_new.
We include the argument type="response" in predict() to get prediction probability.

Helpful links:

predict() documentation
ifelse() documentation

Task 10: Instructions
Create four model metrics, including AUC, Accuracy, Classification Error, and the confusion matrix.

Load the Metrics package.
Use auc(), accuracy(), and ce() to get the first three metrics.
Obtain the confusion matrix for hd_data$hd and hd_data$pred_hd using the table() function. Use the dnn argument to customize the table row/column names to be 'True Status' and 'Predicted Status', respectively.
auc(), accuracy(), and ce() all take the true label as the first argument and predicted outcome as the second argument

Helpful links:

Metrics package documentation





























