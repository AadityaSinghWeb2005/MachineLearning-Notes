	
Entropy ka Mtlb hai hota hai Disorder jis bhi dataset Mein jada disorder hoga usme Entropy Jada hoga 
Simple word mein Entropy ek "Measure of Impurity Hai " (Uncertainity)
Yeh batata hai Data kitna bikhra hua hai aapas. Data jitna jada ek jaise hoga utna entropy Kam hoga 
Rule of Thumb : "More Knowledge = Less entropy "
Agar kisi dataset ko dekhke aapko Confirm ho jaye Ki iska answer toh pakka Yes hi hoga yah aapko answer pata hoga toh Entropy = 0 
Lekin agar kisi dataset ko dekhke aapko Confirm nhi hoga ki iska answer kya ho skta hai Kya pata Yes yah No Jaha pe confusion ho Waha Entropy Jada hoga 

**How to Quantify this Entropy :**
Ek formula ke through hum pata karskte hai Ki kis dataset kitni entropy hai 
Formula : 
![[Pasted image 20260227104553.png]]
Agar multi class hai toh bas Hum Elements ki Probability Add karte jate hai 
Ex : $$H(S) = - P_1\log_2(P_1) - P_2\log_2(P_2) - P_3\log_2(P_3) \dots$$

**Observations :** 
1. Two classes ke case mein Minimum Entropy 0 hogi aur max entropy 1 Hogi 
2. Multiple classes ke case mein Min entropy 0 hogi aur Max entropy 1 se zada ho skti hai 


**Entropy for Numerical/continous values :**
1. Numerical Ke case mein abhi ke liye hum bas ek baat yaad rkhte hai 
2. Jis bhi data set ka High Peak hoga Uski Entropy Sabse Kam hogi 
3. Aur jis bhi dataset ka Peak steep hoga uski entropy jada hogi 
4. Mtlb jisme Jada variance usme jada entropy aur jisme kam variance usme kam entropy 
