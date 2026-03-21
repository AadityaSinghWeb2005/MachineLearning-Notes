
Mathematical Formulation for 2D Data : 
	So in the previous session [[Ridge-Regression/1__Part]] we have seen that how can Value of Slope(M) can be the reason of Overfitting so we have tried to Lessen the Value of M to a much optimal value which Helps us to find a correct best fit line which does not overfit (this new best fit line has Higher Bias but Much lesser variance Due to Bias Variance Trade off ) 
	so this is How we lessen the value of M 
	![[Pasted image 20260210113135.png]]
	in this When You Lambda(m^2) for 2D  to a #ErrorFunction function its whole value is always Lesser than the original M value we Got from the just #ErrorFunction part 
	Lets Derive it why : 
		so when You Put the value Of Y-hat(predicted value from ML model) it look like this : 
		![[Pasted image 20260210113447.png]]
		to get the value of M we just differentiate it with respect to M 
		From [[1__Simple Linear Regression]] we got the value of B = Y(mean of Y train ) - m(slope)X(mean of X train)
		putting the values it look like this : 
		![[Pasted image 20260210113732.png]]
		after differentiating with respect to M its gonna look like this : 
		![[Pasted image 20260210113928.png]]
		taking 2 common then it looks like ; 
		![[Pasted image 20260210114544.png]]
		![[Pasted image 20260210114609.png]]
		![[Pasted image 20260210114638.png]]
		so this is How Ridge-regression Calculates the value of M in Lambda(m^2) 
		It similar to how we calculate the M in the [[1__Simple Linear Regression]] 
		but we just add the Hyperparameter Lamba in the denominator 
		so it affects the value of M 
		and also affect the value of B because to find b we need this formula 
		B = Y(mean of Y train ) - m(slope)X(mean of X train)
		so that's how it regularized the Error Function to find the best fit line which does not overfit In the ML model 

Code From Scratch for 2D Data : 
	Create a Class with Alpha(default value =0.1) `self.m = None and self.b = None `
	first Calculate the M value using this formula : 
	![[Pasted image 20260210120032.png]]
	`num = 0 and den = 0 ` Now we calculate its values 
	we will first initialize the Loop `for i in range(X_train.shape[0)` it will run for all the rows No. 
	then `num = num + (y_train[i] - Y_train.mean())*(X_train[i] - X_train.mean())` this will calculates the Num 
	for `den = den + (X_train[i] - X_train.mean())^2
	Now we will exit the Loop and assign Values 
	`self.m = num/(den + self.alpha) and self.b = Y_train.mean() - self.m*X_train.mean()`
	will return the `self.m and self.b` 
	this will all become part of Fit()

Mathematical Formulation for N-Dimensional Data : 
	so previously we are working the 2D data but in this we will work with N-Dimensional Data
	so first we convert the #ErrorFunction 
	in to the Matrix to control Multiple Rows and Columns of X and we Have N+1 Columns and M columns 
	![[Pasted image 20260212064702.png]]
	so we convert the #ErrorFunction into matrix form in which W is coefficients of the columns or weights of the column and W0 is the intercept so there N+1 weights  where values are : 
	![[Pasted image 20260212064927.png]]
	Now this is the loss function for the normal Linear regression Now for the Ridge regression we just add the lambda(w^2) value to this equation and it becomes like this : 
	![[Pasted image 20260212065245.png]]
	Where w is the Weight Matrix which is given above which can be written as (Weight)^T * Weight 
	![[Pasted image 20260212065407.png]]
	this is the loss function for the ridge regression for N-dimensional Data
	So to get the value of W we just need to differentiate this equation with the Respect to w (matrix differentiation ) We got value : 
	![[Pasted image 20260212070240.png]]
	**Code Snippet for this :** 
		using the Diabetes Dataset `solver = chelesky` will do this function in Sklearn class Ridge 
		```python
		class MeraRidge : 
			def__init__(self,alpha=0.1):
				self.alpha = alpha 
				self.coef = None
				self.intercept = None 
			def fit(x_train,Y_train,self):
				x_train = np.insert(x_train,1,0,axis=1)
				I = np.identity(X_train.shape[1])
				I[0][0] = 0 // because it we dont want to multiply Lambdas to Intercept Only Slope is allowed
				result = np.linalg.inv(np.dot(X_train.T,X_train)+self.alpha*I).dot(X_train.T).dot(Y_train)
				self.intercept = result [0]
				self.coef = result[1:]
			def predict(self,X_test):
				return np.dot(X_test,self.coef) + self.intercept
			
		```