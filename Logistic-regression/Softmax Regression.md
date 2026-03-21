
**Introduction :** SoftMax Regression OR Multinomial Logistic Regression is extension of Logistic regression in which we handle Multiple Classes. It helps U in Deep Learning Also. 
What is ==SoftMax Function== ? Its A function which is used for calculating the Probability of Every Class With the Help of this Formula : 
![[Pasted image 20260226080703.png]]
Value of this always lies between 0 to 1 and sum of all the Probabilities of classes will be 1 


**Training Intuition :** It's the basic intuition of How Can Softmaxregression can Work in behind the scenes. So lets s take a example of Student Placement In which we have three columns CGPA , IQ and Placement and In Placement we Have three classes 1, 2, 3(in which 1 means He got placed , 0 Means He's Not placed , 3 Means He Opt Out of Placment) What we do Now is We apply OHE(One Hot Encoding) On this Placement Column and Derive Three columns out of this 1 , 2 , 3. 
In column for 1 Every Value is 0 except the 1 values as same we do for other Columns.
Now we divide the dataset in to three mini Datasets D1, D2,D3 according to the columns and Calculate the Coefficients (W1,W2,W0) for Every data set In total we have 9 different values.


**Prediction :** Now we have Coefficients and intercept We will Predict the Output ( Yes , No , Opt. Out). First we need to calculate the Z Values for SoftMax Function to assign the probabilities to the classes. To calculate the Z value for New student for every Dataset we have We use formula $Z1 = W_1 \cdot \text{CGPA} + W_2 \cdot \text{IQ} + W_0$  for Every Dataset and Will Insert These values in the SoftMax Function Like this : 
![[Pasted image 20260226083449.png]]
so Probability of Places is 0.40 and Prob of No is 0.35 and Probability of Opt. Out is 0.25


**Loss Function :** There is One Problem in the previous is that if data or Features are Many then the calculation becomes slower 
So to solve this we Use ==Loss Function== in which we don't Have to Convert the dataset into Mini Datasets and Calculate the Coefficients and Intercept for every Dataset We can directly calculate the 9 values ( coefficients and Intercept) by just using the Loss function for SoftMax regression 
Which is : ![[Pasted image 20260226084253.png]]
When we try to expand this Loss function for the Real dataset we got values Like this ![[Pasted image 20260226085241.png]]
In this We know the actual values but How to calculate the Predicted values ? we will use the SoftMax Function 
![[Pasted image 20260226085411.png]]
Now we know our loss function depend on this coefficients So we Need to find these Suitable Values using Gradient Descent Like this 
![[Pasted image 20260226085606.png]]


