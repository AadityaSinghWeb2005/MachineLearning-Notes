
**Meaning of Ensemble :** Ensemble mtlb hota hai Mulitple Cheezon ka group 
Machine Learning Ensemble = Mulitple Ml ko combine karke ek powerful model banana 
Instead of Ek hi model se prediction lete hai 
Multi Model Se prediction by combining them 

**Wisdom of Crowd Concept**
Yeh Phenomena hai jiske Hisab se Koi individual Galat ho skta hai par ek bheed or Crowd Collectively kabhi Galat nhi hote 
Eg. Amazon Review , 1 Review -> 4.5 (No trust) , 1500 Reviews -> 4.0 ( BOhot trust)
Eg. KBC Poll : Audience Poll -> Audience Mostly Gives Correct Answer 

**Core Idea of Ensemble Learning**
machine learning mein two main Stages hoti Hai : Training , Prediction 
Ensemble learning mein Hum Multiple base models ko train karte hai , Prediction ke time sabko input diya jata hai 
Fir Output combine kiya jata hai 
Rule of ensemble Learning 
Base Model Different hone Chaiye kaise Different Hone chaiye Iske 3 Method hai 
**Method 1 :** Different Alogrithms (SVM,LR,DTC)
**Method 2 :** Same Algorithms , but har kisko different training data de diya jata hai 
**Method 3 :** Dono combine karo : Different data + Different Model 

**How prediction Happens in Ensemble ?**
In the classification Case : Ex Placement Hoga ya nhi ? 
5 Models ka Ouput :
3 bole -> yes 
2 bole -> no 
to yah majority vote ke concept se final answer Yes hoga 

In the regression Case : Ex Placement Kite LPA ka hoga ? 
5 Models ka Output : 3.4,5,6,7.8,9,0,2.3
5 Models ke output ka mean Nikalenge Aur yehi final ouput mein dedegne 
Final Output : Mean(Average )

**Types of Ensemble learning**
1. **Voting Ensemble :** Different alogrithm, Same data Example Lr, svm , decision Tree. Sab same Data pe train hote hai Prediction ke time Majority yah mean nikala jata hai 
2. **Stacking :** Yeh voting ka Advance version hota hai . Yeh ek extra model hota hai Yeh model Decide karta hai Kaunsa base model accha perform kar rha hai Yeh weights assign karta hai base models ko 
3. **Bagging (Bootstrapped Aggregration) :** same algorithm , Different Training Data . How it works ? Agar 1000 data points hai toh Har base model ko 500 random data points assign hoge iss process ko boot strapping kehte hai 
	**Note :** Agar bagging mein saare Algorithm Decision Tree hai toh isse Bagging ki jagah random forest kahenge 
4. **Boosting :** Model Sequentially Train hota hai Jaise Model 1 train hoga aur mistakes karenge Model 2 Model 1 ki mistakes per dhyan dega aur unhe kam karega ussi tarah Model 3 Model 2 ki mistakes per dhyan dega aur unhe kam karega Issi tarah Gradually Mistakes hoti hai iss algo mein 
   famous Boosting alogrithms : Adaboost , Gradient boosting , XGboost 


**Why Ensemble Learning Works ?**
**Classification Intuition :** different base model alag alag Decision Boundary dete hai. Jab hum majority vote karet hai toh Noise Remove hoti hai , BOunday smooth hoti hai , Accuracy Improve hoti hai 

**Regression Intuition :** har model thoda different prediction deta hai . Mean lene se Extreme errors cancle ho jate hai , Stable Output milta hai 


**Disadvantage :**
1. Computationally Expensive 

**Advantages :**
1. Improvement in performance 
2. Bias-variance ko Reduce karta hai 
3. More Robust model (data change hone pe performance drastically drop  nhi hoti)


**When to use ?**
Always 