
**Introduction :** 
	in the previous sessions we have how gradient descent calculate the value of M and B by over iterating the values using the equation equation of Mnew and Bnew which comes from #GradientDescent 
	Note: Partial derivate of something is called Gradient 
	Now #Batch_gradient_descent Means when we try to calculate the M_slope and B_slope through #SlopeEquation we will pass the All rows init at one time Eg. if we have 300 rows then we will pass it all 300 rows all at once and then it will decide the value of M and B 
	as We do previous in [[1__Gradient Descent]]
	code is the example of #Batch_gradient_descent 
	Its rare and its only used when You have Convex function But also a condition Data should not be big 
	Now what we are gonna do in this In nut shell : is that we gonna apply Gradient descent on N-dimensional data 
	Previously we apply gradient descent on 2D data Only (x,y) but in real world scenarios You will get Multiple linear regression which have multi dimensional Data so we need to calculate the #MLR for it 
	In which we calculate B0 B1 , B2 B3 
	so how to calculate Multiple slopes and One intercept ( B0 )

**Mathematical Intuition** : 
	rather than N-dimensional dataset lets start 3D dataset with 3 features -- CGPA , IQ ,LPA(x1 , x2,x3) and 2 rows which looks like this : 👇👇
	![[Pasted image 20260207155537.png]]
	Now how to calculate Y in this Case : 
	$$Y(lpa) = \beta0 + \beta1*X1 +\beta2*X2 $$
	Now to apply gradient descent we have 1 extra value so lets go step by step 
	step-1 : Initialize the Values Beta0 beta1 beta2 with intialize technique which is You make Beta0(intercept) =0 and Other coefficients like (Beta1 , Beta2 .....) will be equals to 1
	Step -2 decide the Epoch = 100 and learning rate = 0.1 
	![[Pasted image 20260207160314.png]]
	Now we need to find the values of B0 and Beta1 and Beta2 for that we need slope for every Beta respectively 
	How to get these slopes ? Well you just need to partial - differentiate the #ErrorFunction with respect the Beta You are finding the slope As seen in the graph 
	So to handle N-dimensional data we need to find the (N+1)-Derivatives (N+1 ? because of extra Beta0 )
	Now lets try to see the partial differentiation of #ErrorFunction with respect to Beta0
	![[Pasted image 20260207162719.png]]
	So in this process When we partially differentiating the #ErrorFunction there is 1/n with this also which is just n = no. of rows important for formula now putting the values of Yi and Yi(Cap ) according to #MLR and differentiate it with Beta0 we got the slope For beta0 : 
	![[Pasted image 20260207162946.png]]
	Now for calculating Beta1 : 
	![[Pasted image 20260207163400.png]]
	last line is the equation which we got by partially derivate the #ErrorFunction with respect to Beta1 
	Now what is this Xi1 is representing ? This actually representing the first column data so this actually makes sense because Beta1 is actually weight of X1 in the Equation #MLR 
	SO if we want to represent any column weight or any beta M then we can write it as 
	![[Pasted image 20260207163946.png]]
	whatever m you put in Betam You also put it in Xim (that s the general Formula )

**Code From Scratch :** 
	```sh
		Class GDregressor:
			def __init__(self,learning_rate,epochs):
				self.coef_ = None
				self.intercept = None 
				self.lr = learning_rate 
				self.epochs = epochs 
			
			def fit(self,X_train,Y_train):
				//Init You intercept 
				self.intercept = 0 
				self.coef_ = np.one(X_train.shape[1])// what it will do is it will create a array of One 
				for i in range(self.epochs):
					// in this loop i will update the Intercept and coef_ Yi is Y-train and Y(cap) is prediction matrix of Model from Input column X-train 
					Y_hat = np.dot(X_train,self.coef_) + self.intercept_ // Through the vectoriztion process ( in which we Predict the Y for all x-train values )
					intercept_der = -2*np.mean(Y_train - Y_hat)
					self.intercept_ = self.intercept_ - (self.lr * intercept_der)

					// this will give us the intercept 
					coef_der = -2*np.dot((y_train - Y_hat),X_train)/X_train.shape[0] // in this Xim is represented by X_train and this is the same formula for we write in Betam (multiple columns )
					self.coef_ = self.coef - (self.lr * coef_der)
			def Predict(self,X_test):
				return np.dot(X_test,self.coef_) + self.intercept_
	```


