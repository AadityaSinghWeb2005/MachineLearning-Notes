
what are outliers ? Outliers are those observations or data points which performs anomaly in the Dataset 
Eg. if we take data set of No of hours Vs No. of marks students Got then there is some students who got more marks by less amount of study (these cases are called Outliers )
Sometimes Outliers can be useful but in most cases its just Degrade You model or worsen its performance Specially linear models.
Useful cases like anomaly detection like credit card fraud detection. There you need to find the Outlier.

The most difficult thing is how to handle outliers either we remove it or contain it or make changes in it We have to carefully decide 

**Effect of Outliers On ML Algorithms :** 
There are algo which is worse impacted by Outliers : Logistic regression , Linear regression , Adaboost , Deep learning.
But Outliers Does not impact on some Algo like decision trees, random forest etc. 

**How to treat outliers ?** 
There are many ways but we mostly use two ways : 1. Trimming (removing the Outliers )
	2. Capping ( where we make a boundary for dataset in which if data point is lesser or more than a specific Point then its considered Outlier)
	More ways We can treat Outliers : is by considering them Missing values (doing missing values Operations On it ) or We use Discretization ( in which we make the Intervals like 0-100,100-200,200-300 and put all the values in numerical in b/w these intervals so there if any outlier comes it also got included in the interval also )


**How to detect Outliers ?** 
1. Normal distribution : if column showing normal distribution then we can use range (mean + 3Std. deviation , mean - 3std.deviation ) to detect outliers if its not in the range then data point is outlier 
![[Pasted image 20260201202429.png]]
2. Skewed Distribution : If its a skewed Column then we use Interquartile Range proximity rule which is says if a data point is smaller than min Num and larger then Max num then its a Outlier 
	![[Pasted image 20260201202435.png]]

3. Other Distribution : if any data point is out of the range (2.5th percentile value of dataset < x < 97.5th percentile value of dataset ) then its s outlier 
	![[Pasted image 20260201202445.png]]
	

	
	