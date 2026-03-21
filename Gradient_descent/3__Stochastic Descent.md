
**Introduction :** 
	its one of the most used Descent 
	but what's the problem in Batch Gradient Descent ? 
	with the large no. of data it takes Too much computational Time which makes your Model Super slow 
	It will ineffective In deep learning 
	second problem is with the hardware 
	to tackle all these problems we implement the Other form of Gradient Descent which Stochastic Descent 
	So in [[2__Batch_Gradient_Descent or Gradient_descent_for_N-dimensional Data]] when You run the code and when the 1 epoch run You analyze the whole data(all the rows ) and Update the Intercept and Coefficient 
	so In stochastic You just see One Row of the data and update the Coefficient value and intercept value 
	so it will faster to converge You don't need Larger Epochs 
	it gives You faster convergence and You don't need to load full data all together so you don't have to pressure on hardware 
	Stochastic word Definition : 1. having a random probability distribution or pattern that may be [analysed](https://www.google.com/search?sca_esv=fc7fb3900d27d98e&sxsrf=ANbL-n5ohkYSrN6KT0ehNWb74u_c-MYXdg:1770468573499&q=analysed&si=AL3DRZGqprsEvjmyWiMbyiIKX3gMYzh6HYR99n2D3jJFuV6KmyvDxaVIDdj7FYgb8k0n6SPdtyT9B6_oCCVTJo8_a4HTlReF30UYUb5C8jjvOWm3d4Pv2vU%3D&expnd=1&sa=X&ved=2ahUKEwjl8qKztceSAxV1UGcHHTOaHK0QyecJegQIHBAd) statistically but may not be predicted precisely.
	it simply means random It means it will select the row from N-rows randomly to update the values of intercept and coefficients 
	Disadvantage : it did not give steady solution (when you implement this on Model it will give You different value every time You implement It )

**Time Comparison :** 
	at the same no. of epochs [[2__Batch_Gradient_Descent or Gradient_descent_for_N-dimensional Data]] will be faster than [[3__Stochastic Descent]]
	Because In Batch what you will do is just update the value 1 time after accessing the rows but in Stochastic You need to Update every time for every row for every epoch 
	![[Pasted image 20260207184820.png]]
	
**When to use stochastic Descent :** 
	in the case of Big Data (many rows and many columns ) 
	second case would be when You are dealing with Non-convex Function ( which have Gloabal and local minimas ) because it did not get stuck into local minima and it can get out of local minima even if it stuck and Reach to Global Minima 
	The problem with stochastic descent is when it reaches to near of the Minima it starting fluctuating more (because of random Values ) to solve this problem we use concept like **Learning schedules :**
		so what it will do ? it will try to control the learning rate  as by making a relation with epoch 
		Means we are making Learning rate a function of epoch so that it changes with epoch 
		![[Pasted image 20260207190237.png]]
		![[Pasted image 20260207190243.png]]
		in this when epoch is decreasing learning rate will also decrease which will control the fluctuation 
		Means varying the learning rate with Epochs
	
**Code From scratch :** 
	```sh
	Class SGDregressor : 
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
				
				for i in range(self.epochs): // it will run until the No. of epochs 
					for j in range(X_train.shape[0]) : // it will until the no. of rows 
						idx = np.random.randint(0,X_train.shape[0]) // it will select the random no. of row 
						//Now we need to extract the prediction of the Selected random row we got from Idx 
						Y_hat = np.dot(X_train[idx],self.coef_) + self.intercept_	

						//Now we need to find the intecept_der so in this we are just finding the derivative of single row we dont have to sumission and m=1 
						intercept_der = -2*(Y_train[idx] - Y_hat)
						self.intercept_ = self.intercept_ - (lr* intercept_der)


						//Now coefficient Derivation we just dont need summission and n=1 because single row and and Xim dont need that because we just need One row only so we use X_train[idx]
						coef_der = -2*np.dot((y_train[idx] - Y_hat),X_train[idx])
						self.coef_ = self.coef_ - (self.lr * coef_der)
			def Predict(self,X_test):
				return np.dot(X_test,self.coef_) + self.intercept_
	```

