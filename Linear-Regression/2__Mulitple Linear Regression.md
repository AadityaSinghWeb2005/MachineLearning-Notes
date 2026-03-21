

Introduction : 
	its one of type of Linear Regression In this Multiple Input columns are present and One Output column is present 
	Mostly We use this Regression 
	Its just a simple extension of [[1__Simple Linear Regression]]
	in Simple linear Regression we Create a Regression Line #BestFitLine 
	But in Case of Multiple Linear Regression we use A plane in 3D which tries to minimize the distance with every Point and In 4D and 5D we use hyper plane 
	So equation of plane would be : #MLR
	
	$$Y=\beta 0 + \sum_{i=0}^{i=n} \beta i*Xi $$
	where betas are intercept and n = no. of dimensions 
	these betas are coefficients which are weights
	From #Example1 we can write the equation as Like this ; 
	![[Pasted image 20260205092620.png]]
	it means lpa depends on two Inputs CGPA and Iq and there weights if Weight of IQ is less that means it impact on lpa is lesser 
	These weights helps you to understand which columns are more useful 
	B0 is  the #Offset it s a intercept value 

Mathematical Formulation : 
	How can we find Beta0 , Beta1 till BetaN
	First Lets Make a matrix of Model Prediction Ycap and Put their Values from #MLR 
	![[Pasted image 20260205094839.png]]
	in this Ycap is the predicted values by Machine Learning algo and it can be written using #MLR equation 
	its for 100 students 
	Now there needs to be assumptions we make first assumption lets say there is m column and n no. of rows 
	![[Pasted image 20260205095034.png]]
	which can be written like this 
	we will decompose this matrix into product of two matrix just like this 
	![[Pasted image 20260205095300.png]]
	this first matrix can called X and this second matrix can called be Beta 
	so we write a equation like : 
				$$Y(cap) = X * \beta$$
	so i can find the values of Y(cap) which is a predicted value if calculate the $\beta$ value 
	Now lets create a Matrix Y which is the matrix of real Output values then i create a new matrix name e which equation is this : 
	$$e = Y(cap) - Y $$
	where Y is the real output matrix and Y(cap) is Predicted values matrix so Our e matrix will be : ![[Pasted image 20260205100218.png]]
	so in the [[1__Simple Linear Regression]] we learn about #ErrorFunction Now what we can say that #ErrorFunction can be written as 
	$$E(error Function) = e^T * e$$
	this can written as like this  How : 
	after the transpose it becomes row and then multiply with original one and answer would be a single Number Which is a scaler 
	Now Solving the whole equation just like we do in Simple Linear regression we have the value of Beta Function : 
	![[Pasted image 20260205104047.png]]
	this is how You calculate $\beta$
	where x is x_train and y is y_train 
	Why Gradient Descent ? 
	the method we  study to calculate $\beta$ is #OLS method 
	now this method in which there is a transpose multiplication of matrix as you can see 
	but the time complexity of this computation is n^3 which is too high 
	it based on the no. of columns 
	thats why we use Gradient descent its a approximation technique 

MLR from scratch : 
	we have seen in the previous section How to Calculate 
	#MLR_Coeff ($\beta$)  : ![[Pasted image 20260205105053.png]]
	in this X
	Multiple Linear Regression Using Sk-learn : 
	![[Pasted image 20260205105529.png]]
	Multiple Linear Regression From scratch : 
	first add the 1 value Column to the x_train as per the procedure : 
	using np.insert(x_train,index(0) , 1(values you want in the new column,axis=1))
	Code :
		class Merlr : 
		def __init__(self):
			self.coef = None # In this coef is Beta1 and Beta2s 
			self.intercept = None #beta 0 
			def fit(X_train,Y_train): 
			X_train = np.insert(X_train,0,1,axis=1)#inserting the 1s into first column due to procedure 

			#now calculate the Coefficient and intercept 
					Betas =np.linalg.inv(np.dot(x_train.t,x_train)).dot(X_train.T).dot(Y_train)

			#Extracting the intercept 
			self.intercept = Betas[0]
			self.coef = Betas[1:0]
 
Revision : 
- Multiple Linear Regression is one of the Types of Linear regression in which we are handling with Multiple Inputs and One single Output 
- In Simple Linear Regression we tried to fit the best fit in 2D plane 
- But In multiple linear regression because we are dealing N-D plane we will try to fit  a Hyper plane which will try to minimize the Mean Squared error 
- This model is expressed as Y = X*$\beta$ 
- in the this X is the matrix of Input columns with First column value filled with 1 Only (because to add the Intercept in Our resultant vector ) and Beta is matrix of Weights with 1 Columns and n-rows 
- the equation of this best fit plane would be : $$Y = \beta0 + \sum_{i=1}^{i=n}\beta i *Xi$$

- in which Beta(not) is the intercept value and beta(i) are the coefficients or weight of Xi 
-  so the loss function function can be written as L(β) = (Y − Xβ)^T (Y − Xβ)
- Y is the Actual position matrix of values and X* Beta  ( which is Y(cap))
- after the matrix differentiation of this Error or loss function with Respect to Beta 
- We got Beta = (X^T X)^-1 X^T*Y
	- But we need to make sure that input columns are not showing multicollinearty by X^T* XIf XTXX^T XXTX is invertible, then a unique β solution exists.  
		If XTXX^T XXTX is singular, then the β values are not unique.
- We got a array and first element would be Beta(not) which is intercept and all the other values are coefficients 
- **One word Summary : ** 
- We are finding the β values that minimize MSE.  
	The solution is unique only if XTXX^T XXTX is invertible.  
	If XTXX^T XXTX is singular, then the β values are not unique.
