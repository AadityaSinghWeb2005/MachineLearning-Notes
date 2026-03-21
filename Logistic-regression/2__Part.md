
# 📘 Sigmoid Function 

## 🟩 1. Identity (Context Anchor)
- **Topic:**  Sigmoid Function 
- **Domain:** (ML / Math / DL / Stats / Coding)  
- **Why does this exist?**  
	- it Exists to correct the Perceptron Trick error
- **Problem it solves:**  
	- It will Try to create a symmetry in the line 
- **Relation to previous topics:**  
	- It answers the Major flow of perceptron by creating a symmetry line with equal distributed margins 

---

## 🟨 2. Core Idea (Explain in Human Language)
> Explain the idea as if teaching a beginner (no math, no code).

-  Perceptron trick approach was to pull the line toward the miss classified points and Ignore the classified points
-  but in new approach what we do is we make classified point push the line and misclassified points pull the line because of this push and pull an equilibrium will be generated 
-  This equilibrium helps us to get the best fit line
- the magnitude of  push and pull will depend on the distance b/w line and the points 
- so when missclassified points :
	- when closer to the line they will pull the line with Minimum Magnitude 
	- when far from the line they will push the line with Maximum magnitude 
- so when classified POints : 
	- when closer to the line they will push the line with Maximum magnitude 
	- when far from the line they will push the line with minimum magnitude 
	
- Impact of Sigmoid : 
	- ![[Pasted image 20260214180432.png]]
- if Plus that means Line Neeche aarhi hai and if Minus that means Line Upar ja rha hi hai
- So these Numbers (yi - y(hat)) (0.2,-0,65,0.7) actually can used as to show Magnitude of Pull and push by misclassified or Classified Point 
- 

---

## 🟦 3. Formalization (Math / Logic / Code)

### 🔢 Math (if applicable)
**Main Formula:**


> Sigmoid Function : $$a = 1/1+e^(-z)$$

**Meaning of symbols:**
-  where z is the value we put in the sigmoid function 
-  a is the output we got a new value 
-  ![[Pasted image 20260214082404.png]]
---

## 🟪 4. Intuition / Visualization / Analogy
- Geometric intuition:
	- When we are Updating the value of Coefficients with the help of the Wnew = Wold - lr*(Yi - Yi(cap))* Xi
	- in the Perceptron trick What we getting for Y= 0,1 or  Yi(cap) = 0,1 is 0 
	- Now we in this procedure we don't want the difference of Yi(actual data ) - Y'(predict value) is 0 or Yi - Y' != 0 
	- we can achieve that by changing the method of how we calculate the Y'(Y-hat) 
	- previously in Y-hat we have only two values 0,1 because of step function But now we don't these discrete terms we want a Number which us to full fill this condition  Yi - Y-hat !=0 
	- so for this instead of Step function we use a new function which is called Sigmoid function 
	- **Sigmoid function :** 
		- so sigmoid function is a function in which if you give it a value it will return a new value 
		- we Give Y-hat value into this function instead of step function 
		- You Represent the Output of sigmoid function as the probability 
			- Eg if Output is 0.6 that mean there is 60% probability of element to be in Positive Region 
		- So we convert the whole system  into probability interpretation 
- Graph interpretation:
	- Visual representation of sigmoid function : 
		- ![[Pasted image 20260214174802.png]]
		- 
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

-  Sigmoid function is alternative of step function which takes a value as input and provides a probability 
-  Probability of a point to lies in which region if its higher than 0.5 then its in a positive region and if its lesser than 0.5 then its negative region and if its 0.5 then its on a line 
-  Because of sigmoid function we can do the Push pull mechanics of Missclassified and classified points 
- its Output value range is between 0 and 1
- its input value range is between -infinity and +infinity 

---

## 🧪 8. Implementation / Application
- How would I implement this?
- Tiny experiment / code idea:

---

## 🏁 9. One-Line Takeaway
> If I forget everything, remember this:

**➡️**sigmoid function convert the value into probability. Probability of lies in which region 

---

# 10. Coding Snippets

```python 

def sigmoidFunction(value):
	return 1/(1 + np.exp(-z))

# 
```

