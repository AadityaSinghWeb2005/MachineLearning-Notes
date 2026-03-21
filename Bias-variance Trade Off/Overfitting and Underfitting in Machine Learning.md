
**What is bias-variance ?** 
	![[Pasted image 20260209123345.png]]
	in this Diagram we have three Datasets M1 M2 M3 
	What is bias ? In machine learning Literature Bias is able to tell the How much Good of relationship b/w training data(how good related is Your Training Data )
	So according to bias M3 have High bias and M1 has Low Bias This is called #Bias 
	**Variance :** Variance is a difference b/w error rate of test data and error rate of train data Means Variance = $ErrorRate(test) - ErrorRate(train)$
	if this difference is higher that means We have high variance and Lower means Low variance 
	so In the Diagram as You can see M3 have Highest variance and M1 and M2 both have Low Variance 
	

**Overfitting and Underfitting :** 
	Overfitting means Our model Showing No error On training data and much bigger error on Test data (High variance case) this is called #Overfitting You Model heavily depends On training Data Eg. M3 graph in the above diagram 
	Underfitting Means Our Model showing High Bias (Meaning no good relation ship with Training Data) Means It Not good with training Data and test Data also this is called #Underfitting In Which Bias is High and variance is Low Eg. M1 in the above diagram

**Variance-Bias trade off :** 
	in simpler terms we always try to find the Model which have Low Bias and Low Variance and M2 fits these conditions 
	This is the sweetest Model we can find 
	To find these Types of Model We Use methods Like : 
		1. #Regularization 
		2. #Bagging
		3. #Boosting  	