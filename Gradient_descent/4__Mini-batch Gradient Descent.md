
**Introduction :**
	So types of GD depend On the How many times You update the values of Coefficients and Intercept in batch (you do one Update Per epoch after all the rows  it was slow) to solve this stochastic comes (you do N-Updates per epoch for every Row , It is suitable for Big data and Non-convex function Because it can jump out of the local minima because of Random Number ) 
	stochastic main problem its always gives randomness the data 
	So we use One more type which Mini batch Gradient Descent 
	In Mini batch we convert all the N-rows into mini batches and batch contain some part of rows. Now We can Update Our values by seeing One batch at a time 
	So mini batch is actually A General form for both Batch GD and Stochastic GD by tuning the no. of batches 
	Eg. If no. of batches = no. of rows then its Batch GD descent (One single epoch will all the rows together to update values )
	similarly , if You take no. of batches = 1 then its stochastic GD descent 

**Code From Scratch** : 
	``Class MBGdRegressor : 
		`def __init__(self,epochs,learning_rate,Batch_size):`
			`self.epochs = epochs` 
			`self.Lr = learning_rate`
			`self.batch_size = Batch_size`
		`def fit(self,X,Y)`:
			`self.intercept = 0`
			`self.coef_ = np.ones(X_train.shape[1])`
			`for i in range(self.epochs):`
				`for j in range(X_train.shape[0]/self.batch_size) // this loop will run until the batch size` 
					`idx = random.sample(randint(X_train.shape[0],self.batch_size)) // it will generate random for selecting N- random rows in a batch to work with` 
					`Y_hat = np.dot(X_train[idx],self.coef_)+self.intercept_`
					`intercept_der  = -2*np.mean(Y_train-Y_hat)*`
					`self.intercept_ = self.intercept_ - (self.lr * intercept_der)`
					`Coef_der = -2*np.dot((Y_train - Y_hat),X_train)`
					`self.coef_ = self.coef_ - (self.lr * coef_der)`
			`print(self.intercept_,self.coef)`
		`def Predict(self,X_test):`
			`return np.dot(X_test,self.coef_)+self.intercept_`

