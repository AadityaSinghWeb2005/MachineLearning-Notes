

**What is Regularization ?** 
	Regularization is a technique in which you add some data in Your Model to decrease #Overfitting (in which Model tried to cover Every Point ) We should use it where there is a chance of Overfitting in [[Overfitting and Underfitting in Machine Learning]] 
	Many engineers by default take it In their Model Because it don't have any worse effects 
	there are three type of regularization : 1. Ridge Regularization 2. lasso Regularization 3. Elastic regularization 

**Geometric Intuition of Ridge Regularization :** 
	#Overfitting is the phenomena in which our machine learning Model Performs very well on Training Data but does not Give That Performance On different Dataset 
	General Understanding is its have high Variance ( means Performance on One dataset is different and On other dataset its different )
	So lets see in the Linear Regression context , as we know the whole idea for the linear regression is to find the best fit line from [[1__Simple Linear Regression]] by finding the values of M and B 
	So to find out the about the Overfitting Means is Our Model Doing Overfitting Or not we will find the M value(slope value) because it tells the weightage of X (meaning it tells How much X is important for finding the value of Y ) so if M is Smaller that means x is not important and if M is larger that means X is Important for finding Y 
	So in the case of Overfitting M value is much Higher in Linear Regression Context 
	Also it can also indicate is that Your Model Doing Underfitting or Not ? by checking the value of if its Too smaller or 0 that means it underfitting 
	So in mathematical if we have to control the Overfitting We have cool down the value of M or make it smaller (not much smaller because then it will start underfitting ) we have to Get it to a optimal point where Y value Does Not Depend Heavily On X only 
	Eg. ![[Pasted image 20260210104944.png]]
	as You can see in the dataset blue points are our training Data points and crosses our Test Data points
	So Our ML model when tries to build a best fit line it will make a best fit line for Training data and its Equation is Y = 1.5X + 0.8 
	But as You can see its overfitting Because it Only working ON training Data Properly Not On Test data 
	ON the other hand You can See a Optimal Line name Lr which should be correct the Best fit line and Its Equation is Y = 0.9X + 1.5  
	Now as You can see in both the equations in First Our Model Heavily depends ON X that s why its Showing a Not Good Best Fit LIne 
	On the other hand In second Equation Ml Model does not heavily depend on X that's why its giving a More Good BestFit Line 
	Now How to select the Best Optimal Lines for Our ML Model 
	SO we select the Correct Best fit line (which have minimum #ErrorFunction ) As You can in the Graph as well 
	So We need to select the Best Fit line which shows Minimum #ErrorFunction and also Don't Overfit in Our Model by this formula #RegualrizedErrorFunction
	 : 
	![[Pasted image 20260210105842.png]]
	in which M is slope value and Alpha is Hyper parameter which value lies in 0 to Infinity 
	Now we need to apply this formula to the above Diagram slopes to get the correct Best fit line which will have the Minimum #ErrorFunction and don't Overfit in Our ML Model 
	for Line LN : ![[Pasted image 20260210110153.png]]
	In the first Line as we see it correctly Crossing the Every Data Point of training Dataset it don't have any error So #ErrorFunction become 0 and we take Lambda = 1 and M slope value is 1.5 now putting the values in the #RegualrizedErrorFunction we Got a value of 2.25 
	Now when You Apply #RegualrizedErrorFunction on Lr You got something like this 
	![[Pasted image 20260210110605.png]]
	in which #ErrorFunction is calculated for Lr then You add Mslope value for it which is 0.9 and multiply it by Lambda =1 And it gives value of 2.03 
	Now LN(2.25) < LR(2.03)  so that Means Our ML Model selects the LR line even though its showing errors on training data buts not overfitting 
	Now this regularization technique is also called L2 Norm Why ? so we only work with One Input column Until Now and what if there are Multiple Input columns what will be the equation which we add in the #ErrorFunction  to make it #RegualrizedErrorFunction so for we add $$\lambda(M1^2 + M2^2 + M3^2.....+Mn^2)$$
	where M1 M2 M3 are coefficients or Slope values of all the Input columns in regularization we Do Square of them and Add them with each other that's why its also Called L2 norm 
	There is also other techniques rather than Regularization which is called Lasso (L1 Norm) in which instead of Square of M-values we take simple |M| of them and add them
