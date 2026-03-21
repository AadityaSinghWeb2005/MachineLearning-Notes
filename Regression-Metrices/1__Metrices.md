

Introduction : 
	there are many methods to calculate Regression Metrices some of them are : 
	1. MAE
	2. MSE 
	3. RMSE 
	4. R2 Score (Coefficient )
	5. Adjusted R2 score 

MAE(Mean Absolution Error): 
	to calculate this we just need to find $Y1$ (Actual Point On graph ) and $Y1'$ prediction done by Machine learning 
	difference of them for every Point in the Graph gives us Total Absolute Error
	which look like this : $$\sum_{i=0}^{i=n}|Y1-Y1'|$$
	Now we divide by the No. of Total Points in the Dataset it becomes 
	#MAE : $$(\sum_{i=0}^{i=n}|Y1-Y1'|)/n$$
	Advantage : 
		1. It Gives Answer which have Same Unit As Y 
		2. It robust Outliers (less effected by Outliers )
	Disadvantage : 
		1 The modulus function which is used In #MAE in not Differentiable 

MSE(Mean Square Error) : 
	Mean Squared error #MSE  is calculated same as #MAE but in this we just use Square in place of Mod 
	because of the disadvantage of Mod Not being differentiable and Square is 
	MSE represents in geometry Like this : 
	![[Pasted image 20260204123242.png]]
	This square just represent $(Y1 -Y1')^2$
	The number it gives is called loss function we just minimize 
	Advantage : 
		1. it use square which is easy to differentiate 
	Disadvantage : 
		1 Its Not robust to Outliers 
		2 Its answer  Squared of Y-Unit which is hard to interpret

RMSE(root Mean square Error ):
	its just a Root of #MSE which is called as #RMSE 
	same properties as #MSE
	Mostly #RMSE used 
	Advantage : It just convert the squared Unit into Normal 
	Disadvantage : Not robust to outliers 
	Mostly used in Deep learning 

R2-Score : 
	#R2_Score It tell how good is Your Model Performance 
	its a comparison of the performance of Y-mean line VS regression line 
	Y-line is worst way of doing prediction by just creating a mean line on data points from Y-Axis 
	regression Line is the #BestFitLine by Machine learning algorithm 
	formula of #R2_Score  : $1-(SSr/SSm)$
	SSr(Sum of squared error for regression Line ) = #MSE For Regression Line 
	SSm(Sum of squared error for Mean line ) = #MSE for Mean line 
	Interpretation of #R2_Score :
		lets #R2_Score  is 0 (in the case of SSr/SSm is 1 that both showing same error which is wrong ) 
		lets say #R2_Score  is 1 (in the of SSr/SSm) is 0 that mean both showing No error which is good ) 
		if #R2_Score is close to 0 then Your Model is wrong and If its closer to 1 then its Good 
		What to do if its -ve
		 ? 
			in that case it means you have interpreted the wrong regression line or you dataset is showing Non-linear behavior but You apply linear regression on it 
			so Doob maro 
	How #R2_Score  is interpreted ?
		Eg. Lets say our R2_score is 0.80 it means Our Input columns has able to explain that why the 80% of Variance happens in Output column Eg. CGPA and Package #Example1 if the score is 80% in this dataset that mean CGPA ables to tell that there is 80% variance in Package and 20% is unknown 

Adjusted R2-score: 
	 #AdjustedR2-Score Major flaw in the #R2_Score  is that if You add New input columns in this the #R2_Score will increase or stay as previous . Now the problem is when we add a irrelevant column (like temp in placement dataset ) It should have not Impacted it at all But guess what #R2_Score will increase That's the problem 
	 To solve this We Use #AdjustedR2-Score Formula for this : 
	 ![[Pasted image 20260204190817.png]]
	 in this K = No. of cOlumns , n = no. of rows, R2 = #R2_Score 
	 #AdjustedR2-Score will decrease when you add a irrelevant Column and Increase when You add a relevant column 
	 
 
	

Notes : 
	Use MSE when Handling with No Outliers 
	Use MAE when Handling With many Outliers 
	R2-score gives absolute No. which gives The direction of you model (is your model Doing Good or bad ) No matter whats the dataset 
	In case other they heavily depend context of Dataset 