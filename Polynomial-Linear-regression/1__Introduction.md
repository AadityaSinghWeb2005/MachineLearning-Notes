


**Introduction :** 
	so previously when we study linear regression we study that to get Linear regression we try to fit #BestFitLine in the 2D for simple linear regression 
	But for 3D or N-D we try to fit a plane or hyperplane which is called Multiple Linear regression 
	![[Pasted image 20260209103810.png]]
	as You can see in the above Diagram 
	So For linear regression or #BestFitLine to happen data should show linear behavior but what if don't show linear behavior we have to apply linear regression on it 
	Then we use polynomial regression on it 
	Polynomial regression is a type of linear regression in this You just add polynomial terms in the data 
	Eg. Lets say you have data with X(input column ) and Y(output column) so it will show Non-linear regression and You have to extract the Linear behavior out of it with the help of Polynomials 
	In this we convert the X column into N-categories according degree of Polynomial (if DOP = 3)
	then X -> X^0 ,X^1,X^2
	and put values in it 
	equation of this Polynomial regression look like this :
	![[Pasted image 20260209114837.png]]
	Degree of polynomial is hyperparameter (we have to correct the Optimal value )
	For Two Input columns ( x1 and X2) Equation would look like this : 
	![[Pasted image 20260209115138.png]]
	Why we called this polynomial regression is type of linear regression ? because the relationship between Y and Coefficients (Beta1 , Beta2 ...) are showing linear relationship thats WHy 

**Logic Behind Code**  : 
	`poly = polynomialFeatures(degree =2)` this is How you give degree to You polynomial regression class using Sk-learn
	it means every single Input column will convert into three columns( X^0 ,X^1,X^2) 
	Eg. ![[Pasted image 20260209115905.png]]
	polynomial features always apply on Input pls Not On Y 
	There is also one parameter in `PolynomialFeatures` which is `include_bais` which is by default if we false it then we don't get the X^0 values and by default its True so it showing it 
	It is used to remove the Intercept actually (X^0 is intercept )
	after applying this all these things to Our X_train and then we use linear Regression then That's How #BestFitLine gonna look like in Non-Linear Dataset 
	![[Pasted image 20260209120540.png]]
	So in this Graph it tells the Importance for the Degree of polynomial 
	It should be optimal (not much larger or Not much smaller ) if larger then Model(overfit (it will try to cover every Point of data)) or if smaller then Model(underfit(it will ignore most of the points in data ))
	All above is the example of Simple Polynomial regression (in which Only One Input and One Output column )
	**Multiple Polynomial regression :** 
		So when we try to Implement Multiple Linear regression on a dataset which showing Non-linear behavior it will work like this : 
		![[Pasted image 20260209121634.png]]
		as You can see it try to implement a plane using #MLR from [[2__Mulitple Linear Regression]] and you can clearly see it did not completely cover most of the data points 
		so apply Polynomial regression On it 
		![[Pasted image 20260209122044.png]]
		now in this code we are taking Degree = 2 for 2 Input columns 
		`polynomialFeatures` has method `n_input_features` which tells us how many Input columns we give it and `n_output_features` Gives us the no. of columns it make through input columns 
		Powers are actually power of Your new Input columns (0,0)X^0 and Y^0  and (1,0)X^1 and Y^0 as all the work like this 
		so when You apply Polynomial regression On Multiple Input columns with Degree = 3 
		it gonna look like this : 
		![[Pasted image 20260209122526.png]]
		