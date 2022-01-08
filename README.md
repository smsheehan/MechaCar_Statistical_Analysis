# MechaCar_Statistical_Analysis

## Linear Regression to Predict MPG

First load dplyr by loading tidyverse as dplyr is one of the packages in tidyverse.  One could also load dplyr direcly with library(dplyr).

![image](https://user-images.githubusercontent.com/90977689/147964233-df7fc576-5d14-4bd3-a828-543cd50aedf8.png)

load the data:

![image](https://user-images.githubusercontent.com/90977689/147965457-4e92f6d6-eaf1-4372-8b2d-35e9a1bc4dd8.png)


![image](https://user-images.githubusercontent.com/90977689/147965409-161cc5a3-9958-4042-91c3-e6636de412aa.png)


then build the linear regression model:

![image](https://user-images.githubusercontent.com/90977689/147964313-85500177-1e11-402e-8e04-1905f0c1e4f9.png)

Then use the summary function to determine the p-value and r-squared value for the model:

![image](https://user-images.githubusercontent.com/90977689/147964451-5693dc95-4f9d-4118-b950-315a1ea1ef61.png)

* Which variables/coefficients provided a non-random amount of variance to the mpg values in the dataset?

Based on our linear regression model, vehicle length and ground clearance both provided a non-random amount of variance to the mpg values.  Surprisingly, vehicle weight did not.  Since this doesn't match with our intuitive sense about cars, we would need to dig more deeply into the data to see why.  Perhaps in the data set, vehicle weights didn't change that dramatically across the set of vehicles tested.  Or if there were large changes in vehicle weight, they may have been accompanied by dramatic changes in other which complicated the analysis.  In any rate, we would want to understand this in more depth.
  
* Is the slope of the linear model considered to be zero? Why or why not?

The slope of the linear model is not considered to be zero.  This is because we had two attributes (independent variables) which significantly impact our mpg (dependent variable).  Only in a case where none of the independent variables have an effect on mpg would the slope be zero.

* Does this linear model predict mpg of MechaCar prototypes effectively? Why or why not?

This is an interesting question.  In the vein of George Box's famous quote that "All models are wrong.  Some models are useful", I would say this model is only useful in providing a rough understanding of the general relationship between length and ground clearance on mpg.  According to our summary and looking at the multiple r-squared value, this model is only 71% predictive (in other words only 71% of the variance in our mpg is explained by the analyzed independent variables).  I personally would work to gather more data and perhaps include some more independent variables in my dataset to see if that improves my model.

## Summary Statistics on Suspension Coils

total_summary dataframe:

![image](https://user-images.githubusercontent.com/90977689/147977116-67cfeb58-6f86-494f-83e7-39ad3f28dafc.png)

![image](https://user-images.githubusercontent.com/90977689/147976876-58bc5ce8-de9d-4063-8b20-fb808f7c1b79.png)

lot_summary dataframe:

![image](https://user-images.githubusercontent.com/90977689/147977068-7d8210c9-1cd3-4cf6-b8c3-312a33246602.png)

![image](https://user-images.githubusercontent.com/90977689/147976954-f501b1e6-9698-4e88-b187-0fd298169a13.png)

* The design specifications for the MechaCar suspension coils dictate that the variance of the suspension coils must not exceed 100 pounds per square inch. Does the current manufacturing data meet this design specification for all manufacturing lots in total and each lot individually? Why or why not?

This question helps us see the value of analyzing data at as granular a level as possible.  If we were to only look at the variance in the total summary, we would say that the group as a whole meets the specifications (although the high standard deviation should give us pause and encourage us to look at the individual lots).  Looking at the lot level we can clearly see that lot 3 does not meet our design specs.  Lots 1 and 2 both meet our specifications.


## T-Tests on Suspension Coils

![image](https://user-images.githubusercontent.com/90977689/147998540-c79d37b7-c87c-4045-9d1d-237ef231e87b.png)

![image](https://user-images.githubusercontent.com/90977689/147998562-0b659bca-2551-4ba8-8563-57853b952076.png)

![image](https://user-images.githubusercontent.com/90977689/147998603-aef684f6-0559-42ea-9517-6ff417663df4.png)

![image](https://user-images.githubusercontent.com/90977689/147998646-0e1fb313-bbe6-44e3-817a-64f55fff3829.png)

In this part of the challenge we are performing t-tests on the mean PSI for the group and then for each individual lot.  In each case we are testing to see if we can rule out the Null Hypothesis (No significant difference between the evaluated group's mean PSI and the population mean of 1500 PSI).  If in the t-test we acheive a p-value of .05 or below, then we would reject the Null Hypothesis and accept the Alternative Hypothesis (there is a significant difference between the evaluated group's mean PSI and the population mean of 1500 PSI).  Here is what we learned

* All lots combined: p-value of 0.06028.  We can not reject the Null Hypothesis
* Lot 1: p-value of 1.  We can not reject the Null Hypothesis
* Lot 2: p-value of 0.6072.  We can not reject the Null Hypothesis
* Lot 3: p-value = 0.04168.  We reject the Null Hypothesis and can declare that there is a statistically significant difference between the mean PSI for Lot 3 and the population mean of 1500 PSI.



