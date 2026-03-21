

**Introduction :** Decision Tree classifier ek Machine Learning Algorithm Hai Jo Classification Karne Mein help Karta hai 
Isse aap ek simple if else Ki tarah Dekhiye 
isme hum data Ko ek tree structure mein form karte hai Yeh Data ko rules ke basis pe filter karta jata hai jab tak final Answer na mil jaye 
Decision Tree sirf Categorical Data hi nhi Numerical Data pe bhi kaam karta hai 
Example : Maan Lijiye Mere pass Ek dataset hai Usko Mein Decision Tree mein convert karna chahta hoon 
![[Pasted image 20260227095918.png]]
Isme Outlook Root node (primary Node) isse Hum decision lete hai Jaise iss example mein Outlook hai Isme ek input dete hai {Rainy,Mild,High,Strong} Ab rainy hai outlook toh rainy wali branch mein jaenge phir isme High hai Humidity iska mtlb hai Play=No 

**Geometeric Intuition :** Yeh bhi Normal Classification Algorithms ki tarah Data ko alag alag kata hai Line Ki Help se (bas yeh line condition wali hoti jaise Agar Data ki 1.5 se badi hai toh right side aajao aur agar choti hai toh iss taraf aajao ) Example : 
![[Pasted image 20260227100338.png]]
Jaise iss example mein humne IRIS flower dataset liya jiska Output 4 Flowers aate hai 
toh humne Do condition banayi Redline ka matlb hai agar Petal length 2.0 se Jada hai toh woh simple Left side wale ssaare setosa Flowers hai 
Agar 2.0 se kam hai lekin sepal length 1.5 se jada hai toh Virginica Flowers hai and agar sepal length 1.5 se jada hai toh versicolor flowers hai 

**2D Space :** 2d space mein data ko seperate karne ke liye Hum lines ka use karte hai 
**3D space :** Hum Planes ka use karte hai jisse 3D boxes bante hai (cuboids)
**N-D space :** Hum Hyperplanes banate hai jo hyper cuboids create karte hai 


**How to Create a Tree ?**
1. Data Uthao 
2. Decide karo konsa feature/column aapka root node banega jo further divide hoga 
3. Iss process ko recursively repeat karo bache hue Data aur columns pe jab tak Data acchi tarah classify na ho jaye 

**Important Terminologies :**
1. Root Node : Tree ka sabse Pehla condition jaha se data split hona shuru hota hai 
2. Splitting Point : Woh specific Point yah value jaha se branch divide hoti hai 
3. Decision Nodes : Root Node aur leaf node ke bich ke saare intermediate nodes jaha conditions check hoti hai 
4. LeafNodes/Leaves : Final Nodes jaha classification khatam hoti hai (Yaha final prediction milta hai )

**Advantage :**
1. Highly Intuitive 
2. Minimal Data prep (isme data ko normalize yah standardize karne ki zaroorat nhihai )
3. Fast Testing Time (iski time complexity O(log n))
**Disadvantage :**
	a. Overfitting 
	b. Imbalanced Data issues (agar dataset mein Ek class dusri class se bohot jada hai Eg. 90% Yes and 10% no , Tab yeh algo accha perform nhi kar pata )


**Note :** Desicison Trees mainly classification ke liye use hota hai but yeh regression ke liye bhi use ho skta hai Isliye Isse CART (Classification and regression trees) Kehte hai 
