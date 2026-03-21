	


Introduction : 
	Its easy to understand . Its One of the most intuitive by math 
	what we need to study for LR : Its a supervised learning algo , It solves regression problem ( which output has Numerical column )
	Types of Linear Regression : 1) Simple Linear Regression 2) Multiple Linear Regression 3)Polynomial Linear Regression 
	Simple Linear regression has Only One Output Column and One Input column #Example1 :. Placed student(dataset ) have two Columns : Package(Output ) , CGPA(Input) so we can predict Package using CGPA. This is simple Linear Regression 
	Multiple Linear Regression : which have multiple Input columns Eg. same example as above but adding new columns(input columns) like Gender , state etc.

Geometric Intuition For Simple Linear Regression :
	First thing You need to do with data is to plot it . Real world dataset are Mostly Not completely Linear (because of real life factors These are called #StochasticErrors
	) which makes it closer to linear 
	if its completely Linear You can use Line equation : Y= MX + C 
	where M = slope ( angle of Line From X )
	C= Y-intercept 
	#lineEquation : Y=MX+C
	so if anyone says what will value of Y for value X then we can just simply put it 
	Even if its half linear what will You do ? 
	so in this you try to draw a
	#BestFitLine  ==best fit line(which tries cover most of the most Or closer to every point Or most of the point )== we build this line by choosing M and C 
	for Intuition from the #Example1 we can write as Package = m* CGPA + C 
	m is actually Weightage (How much it depend on CGPA )
	C is actually #Offset mean even lets say our M or CGPA got 0 then our Whole Package don't have to be zero so it don't become Extreme case 

Code Snippets : 
	To find a regression line which Algo draws to decide : 
		plt.plot(X_train,lr.predict(x_train),color='red')
	![[Pasted image 20260204093854.png]]
	to get the Y-intercept(lr.intercept_) and slope (lr.coef_)
	so Behind the scene our algorithm just calculates the slope and intercept and just put down the X value to get Y-value from #lineEquation 

Mathematical Formulation For SLR : 
	How to find M and C ? 
	There are Two Ways Make formula for both of them : 1) Closed Form solution 2) Non-Closed Form Solution 
	#ClosedFormSoln : Direct Formula 
	We use A technique Name #OLS ordinary Least Square SKlearn use this technique Internally to calculate M and C 
	#NonClosedFormSoln : We use approximation 
	We use a Technique name #GradientDescent 
	why we use #GradientDescent and Not #OLS  ?
	because In higher dimension Data It can be tougher to put the values directly into the formula so we use #GradientDescent for higher dimension dataset 
	#OLS : 
		This method is used by SK-learn directly Under the Hood in to calculate M and C we use formulas : 
		#M : ![[Pasted image 20260204100650.png]]Ybar = Mean of Y and Xbar = mean of X
		#C : Ybar - #M X-bar
	#ErrorFunction :  $sigma(from I=1 to n) di^2 $    
	in which di is the distance of data points from the best line 
	di can be write as $(yi - yi')$  in which Yi' represent the Prediction of ML model and Yi is the correct prediction 
	Best line work is to minimize this #ErrorFunction 
	Now Yi' = $MXi - C$
	where M = #M  and C = #C
	Now #ErrorFunctionfinal will become $$\sum_{i=0}^{i=n}Yi-MXi-C$$
	Now we have Final #ErrorFunction which depends On M and C 
	Note : #ErrorFunction  relation with #M is Kind of Parabolic (ref : [YtVideo](https://youtu.be/dXHIDLPKdmA?si=Cpv8PSjLEXAiYe7t)) and #ErrorFunction relation with #C is also Kind of Parabolic 
	#ErrorFunction Relation with Both #M and #C is showing this type of Graph : 
	![[Images/1_09kq2L23D9XM_9Xtr8gc8Q.png]]
	in which J is #ErrorFunction and theta 0 and theta 1 is #M and #C 
	Our work is minimize the #ErrorFunction as Possible 
	How to Find #C and #M the #ErrorFunction : 
		we Just differentiate it with the respect To #C and #M to find both the values 
		$dE/dC$ = #C For proving use this Video as ref ([Video](https://youtu.be/dXHIDLPKdmA?si=Cpv8PSjLEXAiYe7t))
		same for M 
		$dE/dM$ = #M 
		Now You can find the full reference : at ([Video](https://www.youtube.com/watch?v=dXHIDLPKdmA&list=PLKnIA16_Rmvbr7zKYQuBfsVkjoLcJgxHH&index=51&ts=39m)

Revision : 
	- Simple Linear regression is type of linear regression in which we Work With single Input column and One Output Column
	- Linear regression assumes that the expected value of Y given X follows a linear relationship.
	- So we try to predict the Next values by this Relationship 
	- We first create a best fit line which will try to Minimize the total squared error b/w actual value and predicted value (it minimize the squared residual error known as Error function)
	- We create the Best fit line with help of Line Equation ( Y = MX + C )
	- where M is the Slope and C is the intercept and X is the Input and Y is the Output 
	- M also tells the Weightage of X in Y. M tells How much Y changes When x increase by 1 Unit 
	- We can Find M and C value with Two different techniques first Is OLS(ordinary Least squares) and Gradient Descent (approximation Technique)
	- We Use OLS in this section 
	- OLS minimizes the sum of squared Errors(SSE)
	- Formula for C = Mean of Y - Slope * Mean of X 
	- Formula for M = ![[Pasted image 20260204100650.png]]
	- we can get this formula by differentiating the Error Function or Loss function with Respect to M 
	- What is Error Function or Loss Function  ?
	- Error function is the error which our model is creating in Prediction. we can calculate it with 
	- $$\sum_{i=0}^{i=n}(Yi - Y')^2$$
	- in this Yi is the correct position of dataset Point and Y' is the predicted position of Dataset point Which ML model predicted 
	- we can also Write MX + C instead of Y' so formula become like this 
	- $$\sum_{i=0}^{i=n}(Yi - M*X - C)^2$$
	- from the differentiation of this formula we can get formula of M and C to Solve the Simple Linear Regression 
	- Why linear regression is linear ? because its parameters (M and C ) are Linear 