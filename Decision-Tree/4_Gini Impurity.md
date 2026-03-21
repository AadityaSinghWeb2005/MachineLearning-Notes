
Gini Impurity bhi Entropy ki tarah hi hai Yeh Impurity ko measure karta hai Ki class "pure(ek jaise)" hai yah "Impur(Mix)"
Hum bas Formula different use karte hai 

**Mathematical Formula :** iss formula mein hum logarithm ki jagah Squares ka use karte hai 
$$\text{Gini} = 1 - \sum (P_i)^2$$
Agar aapke pass 2 class hai Yes yah No toh formula kuch aise hoga 
$$\text{Gini} = 1 - (P(\text{yes})^2 + P(\text{no})^2)$$

**Note :** jab hum information gain nikalte hai toh hum entropy calculate karne ke jagah Gini calculate karte hai Aur Best split decide kiya jata hai Formula ke according [[3_Information Gain]]

**Range of Values(Min and Max) :**
1. Minimum Gini = 0 Mtlb class pure (sab yah toh Yes hai yah No) Same as entropy 
2. Maximum Gini = 0.5 Jaha data 50-50 divided ho aise case mein Gini ki value 0.5 hoti hai but Entropy ke case mein 1.0 Ho jati hai (because of Formula Difference ) issi karan se Gini Ka graph thoda niche banta hai Entropy se 

**Gini Vs Entropy :**
1. **Computation** : Isme Gini jeet jata hai Kyunki computers ko Square karna easy lagta hai Log nikalne se Isliye Yeh fast hota hai computationally Entropy se Yeh bhi ek karan hai yehh Sklearn mein Default classs Mein "Gini" hi hota hai 
2. **Result Quatlity :** Zyadatar cases Mein Gini Entropy same hi Decision Tree banate hai 
3. **Tree Balance :** Kuch cases mein Entropy better Trees banata hai in comparison to Gini Kyunki gini kai baar Overfitting karskta hai 

**Note :** Shuruwat hume gini se hi karni chaiye lekin agar aapko Accuracy theek na lage toh aap Hyperparameter Tuning se Entropy ka bhi use karskte hai 