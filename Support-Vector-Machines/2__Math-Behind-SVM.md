****
**Intuition**

- Pehle rule discuss karte hai Jiske base Pe hum data points ko classifiy karenge ki konsa point postive Direction mein jaenga Konsa Negative 
- is rule ko **Decision Rule** Kehte hai 
- **Decision Rule :** ![[Pasted image 20260320171349.png]]
- Maan lete hai Hum Random W vector banate hai Iski direction kuch aisi hogi ki Woh har hyperplane Ke Perpendicular ho 
- Ab hume W ki direction pata hai bas magnitude ni pata 
- Ab maan lo Koi random new Data point aaya hume pata Karna hai WOh postive Region mein aaya yah Negative region 
- Iss Naya point ko Hum U vectore kehte hai ab Bas Hume iss U vector ko W vector pr projection karna hai 
- Mtlb W-vector and U-vector ka Dot product aur unka Dot product Scalar Hoga Jo bataenga Hyperplane kite distance pe Hai Random Data point se 
- Toh final Equation kuch aise banegi $W \cdot X + b \geq 0$  agar Yeh case bana toh Point Positive Region mein hai aur agar Eqn yeh hai $W \cdot X + b < 0$ toh Point Negative Region mein hai 

****
**Hyperplane Equation**

- In previous Section , Humne Yeh jana ki koi bhi point ko classifiy kaise with the help of **Decision Rule** 
- Ab hum Aisa Hyperplane banana hai Jo maximum margin show kare Hyper plane ki equation hai $W^T\cdot X + b = 0$  ab hume W aur b ki aisi Values calculate karni hai Jo Aisa Hyperplane banaye jo Maximum margin show kare
- margin mtlb distance between Postive Variant of Hyperplane and Negative variant of Hyperplane iss Distance ko maximize karne wala hyperplane ke W aur b find karne hai 
- Sabse Yhe distance calculate karenge by assumptions 
- First lets say Postive Variant ki Equation hai : $W^T\cdot X + b = 1$ and Negative Variant ki Equation hai : $W^T\cdot X + b = -1$ 
- Now some questions : WHy we take -1 and 1 to the L.H.S why not 1 and -2 ? Because Main hyperplane ki distance Postive Hyperplane se and Negative hyperplane se equall Honi chaiye isliye 
- Why take 1 ? Its just for mathematical Convinence 
- **Why are We Using these Equations Only ?** Taki mathematical Calculations Easy ho aur hume ek fixed margin Boundary mil jaye 

****
**Margin Formula**

- Margin yah distance nikalne ke liye Har Data Point ko Ek constraint Cross karna hoga Yeh contraint Yeh hai ki  Koi bhi Positive Data point positive Hyperplane ke Neeche nhi aaenga
- AUr koi bhi Negative Point Negative Hyperplane Ke upar Nhi jaenga 
- Points Hyperplane pe aaskte hai (Un points ko Support vectors Kehte hai )
- In Contraints Ko mathematically Aise likhte hai : ![[Pasted image 20260320175031.png]]
- Ab in dono equations ko Merge karke likhte hai Kaise ek kaam karte hai Hai saare data points ko label karte hai Positive data points(Y+) ko 1 se aur Negative Datapoints ko (Y-) =  -1 se 
- toh ab hum equation ko kuch aisa likh skte hai : ![[Pasted image 20260320175320.png]]
- Yi hai Postive yah negative Points 
- So yeh main Constraint Hai Jab tak yeh constraint True hai Tab tk Distance Valid hogi agar Constraint False hua toh Distance Invalid hogi 
- **Margin Formula :** distance Formula ![[Pasted image 20260320180104.png]]
- WHole derivation to get the distance Formula : d = 2/(magnitude of W vector)
- ![[Pasted image 20260320180149.png]]
- This is the Optimization problem which is solved what its saying : yeh keh rhi hai hum W aur B ki aisi Value dhundhni hai jiise 2/||w|| Maximize ho mtlb distance maximize ho jab take yeh Contraint True hai $Yi(W\cdot Xi + b) >= 1$ iss Hard Margin bhi kehte hai 
- Ab agar Koi point Positive hyperplane yah Negative hyperplane se upar neeche ho jaye toh Yeh problem kaam nhi karegi 
- Kyunki Constraint False hogya 
- Aisi Situations ke liye hum Soft Margin ka use karte hai 
****
**THE END**
