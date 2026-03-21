IQR Proximity Rule 5 Number theory (Q1,Q3,Maximum Number , Minimum Number , IQR) 
This mainly used for Columns which are Not Showing Normal Distribution and showing skewness and in this we use box plot  and Maximum and Minimum Number range (Min No. = Q3 - 1.5IQR  and Max No. = Q3 + 1.5IQR)
Where IQR = Q3-Q1 ( Q3 is the 75th percentile value of Dataset and Q1 is the 25th percentile value of dataset )
100 Percentile Value is the maximum value in the dataset

**How to detect Outliers Using IQR**
if any value is Bigger then Maximum value ( Q3 + 1.5IQR) and Lesser than Minimum Value ( Q1 - 1.5IQR) then its a Outlier 
IQR is also called Proximity rule 
So in the coding part we just find all the 5 Number theory Components and Will find all the Outliers for the Skewed Dataset 

How to Remove Outliers 
After finding the Outliers Either We trim them or Capp them Using [Capping Method](1__Intro-to-Outliers)

