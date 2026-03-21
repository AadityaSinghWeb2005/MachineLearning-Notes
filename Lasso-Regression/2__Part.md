
# 📘 Lasso Regression Under the Hood working 

## 🟩 1. Identity (Context Anchor)
- **Topic:**  Why Lasso Regression Creates Sparsity 
- **Domain:** (ML / Math / Coding)  
- **Why does this exist?**  
	- it Exists to 
- **Problem it solves:**  
	- we will understand How math work under the hood in the lasso Regression 
- **Relation to previous topics:**  
	- Why its Create so many zeroes when Alpha value getting higher in [[Lasso-Regression/1__Part|1__Part]]

---

## 🟨 2. Core Idea (Explain in Human Language)
> Explain the idea as if teaching a beginner (no math, no code).

-  How lasso Regression Reaches to Zero and why stops on it  ? 
	- Lasso regression reaches to zero by using it Assumptions Formula and the reason why it stops at zero because zero will be best value for that particular assumption after zero new formula will start applying on that value and it become more Bigger or smaller than before 
-  first just like in ridge regression we need to find the value of M by differentiating the Loss function of Lasso regression but Mod value is not differentiable at 0 so we take a case of |M| > 0 that means we can write  |M| = M 
-  so for M>0 Formula to calculate M in lasso regression : ![[Pasted image 20260213065953.png]]
- for M = 0 then its a simple Linear Regression : 
- ![[Pasted image 20260213070020.png]]
- for m < 0 
- ![[Pasted image 20260213070043.png]]
- 

---

## 🟦 3. Formalization (Math / Logic / Code)

### 🔢 Math (if applicable)
**Main Formula:**
>Loss Function in the case of Lasso regression : $$\sum_{i=0}^{n=0}(Yi - Y')^2 + \lambda|M|$$ 

**Meaning of symbols:**
-  Where Yi is the actual position and Y' is the predicted position 
-  Lambda is alpha value and Mod M is absolute value of M(coefficient or slope) 
-  now we know Y' can be written as Y' = MXi + C
- and C can Be written as Mean of Y - M*Mean of X 
- so formula can be written as : $$\sum_{i=0}^{n=0}(Yi - MXi - Y(mean) + M*X(mean))^2 + \lambda|M|$$
>Formula to calculate Coefficient in case of Lasso Regression : $$\sum((Yi - Y')(Xi - X')-
\lambda)/\sum(Xi - X')^2$$
- Where Yi and Y' is same as above and Xi and X' is also same as above 
- Lambda is the alpha 

---

## 🟪 4. Intuition / Visualization / Analogy
- Geometric intuition:
	- From the formula of M > 0 we can say that if Alpha value is equal to (Yi - Y')^2 then M becomes zero and what if Alpha value greater than in that case M value become -1 but we don't write it 
	- we always stop at zero because if negative value comes then we use the formula for M < 0 which will just make it back positive but make it more larger than before 
	- for intuition : ![[Pasted image 20260213072029.png]]
	- for M < 0 it will as same as above but we use the formula for M <0 and we can see it get the value of M to 0 and stops at it because after that M > 0 formula start applying 
	- ![[Pasted image 20260213072354.png]]
	- Lasso regression reaches to zero because Alpha values in Numerator and Ridge Regression Never Reaches Zero because its value always in denominator so Until Numerator is 0 no matter what value you put in Alpha the M will never become zero 
	- SO how do we know which assumption to use ? well for that You need to find the COvariance of M and if its bigger than alpha then M > 0 if its smaller than Negative alpha then M < 0 and if it lies between negative and positive alpha then M = 0 
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

-  Lasso regression takes three assumptions to calculate the M value ( 1. M > 0  2. M = 0  3. M < 0)
-  There is formulas for all three of the assumptions (in that assumption what will be the formula to calculate the M )
-  Lasso regression reaches to zero because of these Alpha value in numerator 

---

## 🧪 8. Implementation / Application
- How would I implement this?
- Tiny experiment / code idea:

---

## 🏁 9. One-Line Takeaway
> If I forget everything, remember this:

**➡️** Lasso regression Creates so much sparsity because Alpha value is in numerator due to which when Alpha value reaches to MSE Value it becomes Zero 

---

# 10. Coding Snippets

```python 

def fit(self):
	pass 

def predict(self):
	pass
	
# 
```


