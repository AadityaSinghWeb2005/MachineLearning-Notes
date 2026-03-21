
Part-1
--
**What is PCA ?** 
	Its a [[1__Curse of Dimensionality | Feature Extraction technique]]
	Its a unsupervised learning algo Means there is no Output Only Input 
	PCA is used for Dimension reduction 
	PCA mainly Converts the Higher Dimensional Dataset into Best Possible Lower dimensional Dataset 
	While keeping the essence of Dataset (means behavior of Dataset )

**Benefits of PCA : 
	1. reduces the size of Data which helps in faster execution of algo 
	2. Saves computation 
	3. Visualization (PCA Helps to reduce the 10D into 2D or 3D which helps us to plot it Properly )

**Note :** 
	How to do feature selection (means selecting N columns which we will use in a model) in a dataset
	Lets say i have two columns in which i have to select the best Column for that i can plot them on 2D graph and which column has high variance on axis i will select that Axis Column **Eg**: ![[Pasted image 20260203074328.png]]
    in this we have two columns No. of rooms vs No. of grocery shops as you can variance on X-axis (d ) is greater than variance on Y-axis ( d') so that's why we choose Room Column 

**Geometric Intuition :** 
	Now In Above Example we make some changes ![[Pasted image 20260203074833.png]]
	In this we can see we just replace the no. of grocery shops with no. of washrooms but now both of the Features are important You can also see that by graphical representation they both showing Linear relation that mean d=d' so we cant do feature selection on it 
	so we do ==Feature Extraction 
	== what will we do is we just merge the Both features No. of rooms and No. of washrooms 
	 because both of them just are area of plot so we can merge them or we can just make one feature name Size of plot(no. of room , no. of washrooms) and price feature 
	that's what PCA do (in a nutshell ) which is also called Feature extraction 

**How PCA will Be Performed** : 
	so PCA mainly create a maximum variance on One feature Axis which Makes it a New axis 
	Geometeric intuition of this works like this ![[Pasted image 20260203080325.png]]
    this is the graph we use earlier which linear relationship (d=d') now what pca will do is just rotate the both axis's so room become room' and washrooms become washrooms' due to this as you can see variance (d) of room increases and greater than d' of washrooms so Our New Feature will be Rooms' And there will be 2 Principle Components (rooms', washrooms')
    ==No. of Principle Components <= No. of original Features 

**Importance of Variance :** 
	Variance helps us to differentiate the data Whose Means are same by seeing spread
	Now important point to note Spread =! Variance . ==Spread Is directly proportional to variance== 
	formula of variance = Sigma(i=0 to n) (xi - Mean of X)^2/No. of data points
	Always remember spread Is Not variance 
	Why not use Mean absolute Distribution instead of variance  Which exactly shows spreadness like variance ?
	Ans : because its use Mod which is not differentiable at the Graph and Because variance use square which is easily differentiable we use variance 
	Why variance Important In PCA ? 
	ans : To work properly PCA need to maximize Variance because PCA will select only those direction which shows maximum variance ![[Pasted image 20260203082858.png]]
	as shown in this graph the distance between red point and green point in 2D is similar to variance on X-axis So PCA will select x-axis so that distance based algo like KNN works fine In comparison to Y-axis which shows so less variance  in comparison to 2D 


---
## Part-2



**Problem formulation :** 
		We will see How PCA Do things by Math ![[Pasted image 20260203094343.png]]
		In this Graph we can see we ill represent the PCA1(x') as Unit vector and a single data point (x) as x-Vector 
		Now we need to show the projection of x-vector on Unit vector(PCA1) by using the formula : (Unit-Vector * X-vector)/Magnitude of Unit vector
		Now Answer of this formula would be (Unit-Vector)T * X-vector (here T is transpose )
		so answer will be scalar form and answer will be X1*X2 + Y1*Y2 (For More deep understanding refer to this Video Link : [Yt_video](https://www.youtube.com/watch?v=tXXnxjj2wM4&list=PLKnIA16_Rmvbr7zKYQuBfsVkjoLcJgxHH&index=49&t=6m30s))
		so basically Every Single Point act as a vector and get projected On Unit vector and giving a scaler which is length of single Point vector Projection 
		Now Unit vector can be any direction How do we Select which unit vector is Correct 
		by Choosing the Vector which have max variance 
		so How to calculate Variance for the projection 
		![[Pasted image 20260203100543.png]]
		well this is the formula to calculate variance for every projection of Unit Vector then pca will select the projection with Max Variance 
		In this uTxi = All the Data Points Projections 
		utx(mean) = Projection of mean point 
		So to get better Unit vector we use variance which is the mathematical object function Which PCA solves and gives us the Most correct Unit Vector. Now we need to find the Vector which have Max_variance to find that we use 👇
		Now two concepts : Covariance and Linear Transformation to sovle this 
		**Covariance :** 
			Covariance tells the Relation b/w Two variables Means if X is increasing if y is also increasing then its a Positive relation and if X or Y is increasing and X or Y is decreasing then its a negative relation 
			![[Pasted image 20260203102243.png]]
			Direction of relationship Shows by covariance 
			Its value range -Infinity to +Infinity 
			Simple Intuition : How A and B moves together 
		**Covariance-Matrix :** 
			This Matrix Helps us to find the Co-variance between Different Columns (Showing whether they showing -ve or +ve relation )
			eg 3 X 3 matrix of 3 Columns (x,y,z)
			![[Pasted image 20260203103350.png]]
		**Linear Transformation(eigan decomposition of Covariance Matrix )** : 
			matrices are the linear transformations when you apply on the Co-ordinate system(which is group of infinite vectors ) there vector position and magnitude got changed 
			**Eigen vectors :** These are special vectors which do not change its direction after linear transformation apply just change in magnitude. Eigen vector Conidtion : A*V(vector) = lambda*V  // Where A = matrix , Lambda = eigen value , V=vector . Its read as Applying linear transformation on matrix is equal to multiplyling scalar to a vector.
			**Eigen Values** : It s value of how much stretch Our eigan vector has got Eg. Lets say coordinate of A vector in normal 2D is (1,0) but after applying Linear 
			Transformation it becomes Eigen vector (3,0 ) so it mean Eigen value = 3
			EigenDecomposition of Covariance matrix : So we just apply the llinear Transformation to all the vectors by multiplying Covariance matrix to all the vectors and finding eigen values of all the vectos with the help of this. 
			and Whichever vector has the highest eigan value that means it have the Maximum variance and It become our Principle Component 

**Step By Step Solution of How PCA works :**
	1. mean center the N-Dimensional Data 
	2. Find Covariance Matrix 
	3. Find the Eigen value / Eigen Vector for Covariance Matrix (whichever Got Highest Eigen values those vectors Become our Principle Components )

**How to Transform Points :**



	All the points which we have on 3D plane now we just have to project on Our principle Components.
	How to do it ? 
	well you just need to dot product with Unitvector(Vector You chose through Eigan values) and You Got your Columns and values 
	![[Pasted image 20260203112952.png]]
















