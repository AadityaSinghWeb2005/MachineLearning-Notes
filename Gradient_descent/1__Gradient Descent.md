
**Introduction :**
	its a an optimization algorithm 
	if You give it an function ( which should be differentiable at all points ) It will give the Minima of the function 
	its a general function which used in various algorithms like logistic regression, tsne 
	Its a backbone of Deep learning 
	Intuition For GD : 
			Lets Take a example through Linear regression 
		![[Pasted image 20260206104737.png]]
		in this we take two columns and 4 rows mean only 4 students Now we need to create #BestFitLine we can do that with #OLS but we dont do it here we ill use Gradient descent 
		How to apply gradient descent ? 
		so #BestFitLine logic is we need create a line which shows minimum #ErrorFunction 
		So Mainly #BestFitLine depends on two main parameter #M and #C so we need to minimize the #ErrorFunction with help of these parameters 
		Lets say we take #M be constant and Now we just need to change #C so that Our #ErrorFunction  would be minimum 
		Now we know #ErrorFunction and #C relation is parabolic due to its square and we can easily see the #ErrorFunction Lowest Point by #C 
		![[Pasted image 20260206114209.png]]
		Now I need to find the values of #C at this point because at this #ErrorFunction is lowest 
		How to find this Value : 
			Step 1 : Select a random #C Lets say we took #C = -10 Now what would our Graph Look 
			![[Pasted image 20260206114614.png]]
			so in this as You can Red mark is Our #C Point On #ErrorFunction we need to make it reach the Minima Point . It have Only two options either it Go upwards or Go Downwards so how its decide what s the correct direction to reach the Minima Point 
			![[Pasted image 20260206115002.png]]
			So we can use Slope : How to get slope at any particular Point we will differentiate the whole thing and put the particular point value in it and we got a slope 
			so Basically If slope is Negative then We will Move forward and if slope is positive then we Move backward 
			#GradientDescent Equation will be : $$Bnew = Bold  - Slope$$
			This gradient Descent which helps us to find the correction direction Where Bnew helps us to find the New #C value which helps to reach Minima and Bold is the #C which is random value we took previously in step 1 
			So we are only working with #C which is single Variable this is called Derivative and if we work with two variables #C and #M then its called Gradient 
			Now when do we Know that we reach the Correct Minima : 
				actually when we subtract the slope from the Bold and get Bnew and we do this process repeatedly due to which Our Bnew got drastically change from one point to another doing Zig Zag shape again and again to tackle this situation we transform our #GradientDescent Equation and it will look like this : $ $$Bnew = Bold  - Learning rate* Slope$$
				Generally we take Learning Rate = 0.01 to control the Drastic change in value 
				![[Pasted image 20260206120420.png]]
				Now we do this procedure again and again to reach minima 
				Learning rate is essential to control the value of slope 
				When to stop ? we will stop at minima and How to identify that we reach Minima ? 
				There are many approaches : 
				1. difference b/w Bold and Bnew would be closer to Zero 
				2. Limit the Iteration(means I
				3. will only iterate this process to a optimal no. of iteration to reach the minima ) this optimal no. can be get by visualization and this Optimal no. of iteration is called epochs .

**Mathematical Formulation to calculate the Slope with C   :**
	so in this mathematical formulation we will just try to calculate with #C 
	step : 1 start with random value #C 
	How to get Slope From the #ErrorFunction 👇👇
	![[Pasted image 20260206145103.png]]
	by differentiating the #ErrorFunction we get the Slope equation which is #SlopeEquation
	![[Pasted image 20260206145135.png]]
	now putting the b(which is random #C value we taking in step1 ) Once You put the values in this #SlopeEquation You get value of slope
	Then you can put the value of Slope in the Bnew to find the Minima of the #ErrorFunction this Slope value is from Bold Value we got 
	Repeat this procedure Until Your Epoch Value 
	![[Pasted image 20260207105541.png]]
	this graph is about Loss vs epoch (means how much loss is decreasing at Which epoch ) as You can after a Number of epochs it becomes a flat line(mean loss is not decreasing More) so you can find Optimal no. of epoch with this 

**Code Example :** 
	```sh
	applying Gradient Descent Considering #M is constant its value is 78.35
	Taking the #C randome value is 0 
	as we know #M = 78.35 and #C = 0 
	// Now calculating the Loss_slope by #SlopeEquation tion 
	loss_slope = -2*np.sum(y-m*X.ravel()-b) // where ravel() will convert the 2D array of X in OneD 
	//Now calculating the step size (which multiplying learning rate into slope  )
	step_size = loss_slope*lr
	//Calculating the New b 
	b = b - step_size 
	//for doing it iteraitvely 
	epochs = 10 
	for i in range(epochs):
		loss_slope = -2*np.sum(y-m*X.ravel()-b)
		step_size = loss_slope*lr
		b= b - (step_size)
	```
	Note : So gradient descent is just a algorithm which is just minimizing the loss function by repeatedly taking the line to closer to the #OLS 
	Creating a Class and Own Methods to implement gradient descent : 
		in this class we just use the #C only and taking #M as constant Now we create a class it just calculates the new intercept 
		class GDregressor : 

			Def __init__(self,learning_rate,epochs):
				self.m = 29.19
				self.b = 0#Randomly selecting the value 
				self.lr = learning_rate
				self.epoches = epoches 
			def fit(X,Y):
				for i in range(self.epoches):
					loss_slope = -2*np.sum(Y-self.m*X.ravel()-self.b)
					self.b = self.b - (loss_slope*self.lr)
				print(self.b)
				Things to Note down : Learning_rate should be 0.01 and epoches should be according to learning rate only 

**Effect of Learning Rate :** 
	Gradient descent is so sensitive on Learning rate a miscalculation can Move our #BestFitLine to wrong place with Same No. of epochs 
	![[Pasted image 20260207110117.png]]
	as You can see in this graph we learning is too low like 0.02 and you start from red line you can never reach the #BestFitLine and if You take too high value of learning rate like 0.5 You will entirely miss the #BestFitLine 
	so You should always take appropriate value of Learning rate which helps to easily reach the best line with low number of computation 

**The Universality of gradient Descent :** 
	Gradient descent mainly works by finding the correct value of parameter 
	Until this point we only work with linear regression our parameter was #C which
	Gradient descent using to find the #BestFitLine 
	![[Pasted image 20260207110833.png]]
	but Gradient descent can be used in many ML algorithms by using the same equation 
	but how do you find value of slope for any Algorithm ? 
	Just differentiate the #ErrorFunction of that algorithm and You got Your slope Equation now From which we can get slope value 

**Gradient Descent For Two Variables :** 
	Until this point we are taking #M constant and Only calculating with #C but now we will try to calculate both their values by step by step : 
	step -1 Intialize the M and B with random Values 
	Step-2 Epochs = 100 , Learning Rate = 0.01 
	step -3 b = b - Lr * slope   , m = m - Lr* * slope     ( here slope which is using in calculating b and M both are different in case of b its same as previous one for m we are calculating a new slope )
	How to calculate slope for m : 
		so previously we calculate gradient descent with respect to b only 
		so slope is calculated previously by differentiating the Error Function in which M is constant and B is variable that Means error function Was only depend on B and showing parabolic nature and we are finding its (parabola) minimum value with the help of B only 
		But in this, Errorfunction Depends on both M and B that means  first its showing parabolic nature with both M and B in 3D space so we need to find the Minimum value of this parabola of Errorfunction(M,B) with the help of M and B 
		![[Pasted image 20260207112526.png]]
		This is How it looks 
		So to calculate the slope we need to find the slope for both the variables (M and B ) respectively so we can get values of M and B (which minimizes the Loss function )
		for finding slope for b we just partial differentiate the Errorfunction with respect to b and for finding slope for M we just partial differentiate the Error Function with respect to M 
		![[Pasted image 20260207122607.png]]
		this is the process to get the slope of b and m both respectively in their direction 
		And we can find gradient descent by these parameter 
		so In 3D space You got point a in a slope and yOu need to find two components of this slope 
		One component is b_slope and Second is m_slope 
		Combination of these tells You where is Minima
		We need to Know the direction of Minima 
	
**Code-From Scratch :** 
	Class GDregressor : 
		def Init(self,learning_rate,epoches):
			self.learning_rate = learning_rate
			self.b = -120 # random
			self.m = 100 # Random number 
			self.epochs = epochs
		
		def fit(self,X,Y):
			for i in range(epoches):
				loss_slope_b = -2*np.sum(Y - self.m*X.ravel() - self.b)
				loss_slope_m = -2*np.sum((Y - self.m*X.ravel() - self.b)*X.ravel())
				self.b = self.b - learning_rate * loss_slope_b
				self.m = self.m - learning_rate * loss_slope_m 
		def Predict(self,X):
			return self.m*X + self.b

**Visualization of M vs Epoch and B vs Epoch and Cost vs Epoch :** 
	![[Pasted image 20260207125644.png]]
	Slope(M) vs Epoch graph 
	![[Pasted image 20260207125714.png]]
	loss vs Epoch 
	![[Pasted image 20260207125731.png]]
	Intercept(B) vs epoch 

**Impact of things On Gradient Descent :** 
	Effect of Learning Rate : 
		Learning rate is hyperparameter which should changed according to the situation You in if You put a Small learning Rate it will take too much time to reach the minimum Point 
		or If You put a larger learning rate it will always skip the minima and will go too far from it doing zig zag moment 
		So You should always put a optimal No. of Learning Rate according to the dataset Eg. 0.1 
	Effect of Loss function : 
		Until this we are working with simple #ErrorFunction which is just #MSE and its also a convex function (which have Only one Minima which is called Global Minima )
		but when You work with Non-convex function the problem is there multiple minimas which divided into two cateogries One Minim is Global minima and all the other minima s are Local minima . Global minima is correct 
		But some times due to the randome intialization of B and M our algo sometimes stuck in the local minima it should be go into the Global minima but it gives Local minima as Ans 
		![[Pasted image 20260207131058.png]]
		This is the visualization of Non-convex function in 2D  
		the #ErrorFunction till we study is convex function because of Linear regression 
		but Non-convex function can be bit difficult to get minima of it so be ready because its mostly in Deep learning 
		visualization of Non convex function In 3D  : 
		![[Pasted image 20260207131432.png]]
		#SaddleProblem In this if the surface On Graph is Flat then Our algorithm becomes so slow because of each step it getting smaller and smaller and at one Time it will think it as a Minima and Stop 
	Effect of Data : 
		You features should be scaled it will increase the Gradient descent speed because Scaled features will have a circular rings in contour Graph ( when you visualize the 3D graph in 2D graph ) and it will be easy for gradient descent algorithm to have a smooth Curve to reach Minima 
		![[Pasted image 20260207133426.png]] 

**ChatGpt Notes :** 
	THis is used for minimizing the loss function By analogy : Lets say you are on top of mountain and You need to reach the lowest point of mountain in this analogy Mountain is #ErrorFunction Lowest point is Minimum loss (best model ) and steps are gradient descent 
	In the Linear Regression we use Line Equation (Y= MX + C ) M and C are the most dominating factors in the Linequation as well as #ErrorFunction so Gradient Descent will How much change should be done in M and C so that #ErrorFunction Would be less 
	**Simple Mathematical Intuition :**   first we need to create a #ErrorFunction Mostly : mean squared error 
	second step would be we create Slope 

Revision : 
	
