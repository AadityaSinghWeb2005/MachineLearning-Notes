
# 📘 Applying Gradient Descent in Logistic Regression 

## 🟩 1. Identity (Context Anchor)
- **Topic:**  
- **Domain:** (ML / Math / DL / Stats / Coding)  
- **Why does this exist?**  
	- it Exists to solves the Logistic Regression using gradient by finding the Optimal Coefficients to find the best fit line 
- **Problem it solves:**  
	- it Helps us to find to Best fit Line 
- **Relation to previous topics:**  
	- We solve the logistic regression with the help of Gradient descent and loss function from [[Logistic-regression/3__Part|3__Part]] 

---

## 🟨 2. Core Idea (Explain in Human Language)
> Explain the idea as if teaching a beginner (no math, no code).

-  To apply Gradient descent in the Logistic Regression First we need to Get the Y(hat) in matrix form 
- so Y(hat) = sigma(X* W) where sigma is sigmoid function and X is input matrix and W is coefficient Matrix 
- Now We need to convert the Loss function into Matrix form which we do in Math Formaliation
-  Now we need to Partial Derivate the Loss function with every coefficient Value and create a matrix of them . This Matrix is called Gradient and represented by Delta L / Delta W 
-  This Delta L / Delta W is helps us in the Gradient Descent Equation to Update the W-Matrix 
- Both the Gradient Descent and Delta L / Delta W values is present in Math Formalization 

---

## 🟦 3. Formalization (Math / Logic / Code)

### 🔢 Math (if applicable)
**Main Formula:**


> Loss function in matrix form : $$L = -i/m[YlogY(hat) + (1-Y) log(1-Y(hat))]$$

**Meaning of symbols:**
-  Where Y(hat) = $\sigma$(X* W) sigma is sigmoid function and X is X-train matrix and W is the coefficient Matrix 
-  Y is the Actual output matrix 
-  M is the no. of Rows in X Matrix 

>Calculate the Delta L / Delta w : $$-1/m(Y-Y(hat))*X$$
- where Y is output matrix and Y(hat) is the Predicted value matrix and X is the Input Matrix 
- Y(hat) =  $\sigma$(X* W)
- m is the no. of rows 

>Calculate the Equation to Update the W value in Gradient Descent : $$ Wnew = Wold + \eta*1/m(Y- Y(hat) )*X$$

- W is the Matrix of coefficients with ((n+1),1) shape 
- X is the input matrix with (m,(n+1)) shape where m = no. of rows and n = no. of columns 
- Y is the matrix of Actual Output with (m,1) shape 
- Y(hat) is the matrix of Predicted values with (m,1) shape 
---

## 🟪 4. Intuition / Visualization / Analogy
- Geometric intuition:
	- Derivative of Sigmoid function : ![[Pasted image 20260215065515.png]]
	- First we need to get the Y(hat) by this equation : ![[Pasted image 20260215070458.png]]
	-  where X is the X-train matrix and W is coefficient Matrix  and sigma is the sigmoid function 
	- Loss function can be written in Matrix form  
	- Now we need to apply the Gradient descent on this loss function to Get the W matrix values or coefficients values 
	- To apply gradient descent 
		- First we need to initialize the W with random values and update value with the help of this Equation : $Wnew=Wold-\eta*\delta L / \delta W$   
		- where delta L / delta W is the matrix of partial derivates of all the coefficient or weights which size is N+1
		- how to calculate this Delta L / Delta W : 
			- with the formula of to calculate the Delta L / Delta W 
		- 
- Graph interpretation:
- Analogy (if any):

---

## 🟥 5. Edge Cases & Limitations
- When does this fail?
- What assumptions does it make?
- Overfitting / underfitting behavior:

---

## ❓ 6. Confusions & Questions
-  
-  

---

## 🔁 7. Active Recall (After Video – From Memory)
> Write 3–4 lines without looking at notes.

-  You can't apply OLS methods to find the minimum point of Loss function of Logistic regression so You use Gradient Descent 
-  With the Help of Gradient Descent You can find the Coefficients for which Loss function would be Minimum and these Coefficients helps us the for creating a best fit line 
-  Gradient Descent Equation : $$ Wnew = Wold + \eta*1/m(Y- Y(hat) )*X$$
- in which 1/m(Y-y(hat))* X is the Delta L / Delta W which is gradient or matrix of partial derivates of Loss function with respect to Different coefficients 

---

## 🧪 8. Implementation / Application
- How would I implement this?
- Tiny experiment / code idea:

---

## 🏁 9. One-Line Takeaway
> If I forget everything, remember this:

**➡️** Gradient descent help us to find the coefficients which is for Minimum point for Loss function. these coefficients helps us to create a best fit Line to create a right model in logistic regression 

---

# 10. Coding Snippets

```python 

def Gd(X,y):
	X = np.insert(X,0,1,axis =1)
	weights = np.ones(X.shape[1])
	lr = 0.1
	
	for i in range(5000):
		Y_hat = sigmoid(np.dot(X,weights))
		weights = weights + lr*(np.dot((Y-Y_hat),x)/X.shape[0])
		
	return weights[0],weights[1:]
# 
```

