
Jaha pe bhi Target Columns Numerical Hote hai Waha Hum Regression Trees ka use karte hai 
Jaha Data Linear Relation Ship Show karta hai Waha Linear Regression BEst rehta hai 
Lekin Jaha Data Non-Linear Relationship show karta hai Waha Hum Decision Regression Trees Use karte hai 

**How Decision Regression Trees Work ?**
sabse Pehle Hum Data ko Hisso mein baat lete hai Eg. 3 parts mein baat liya Hum Ek condition ke base pe Baat te hai Eg. Hours > 30 Which leads to two Conditions Yes or No if Yes then we just take Mean of Hours of Student study aur agar No aata hai toh hum wapis split marte hai condtion ke base Hours > 15 Answer agar No hota hai toh mean nikal lo and agar yes bhi hota hai toh bhi mean Nikal Lo 
**Summary :** Algorithm Data ko kisi threshold ki value ke basis pe Split karta hai , Splits ke baad jo regions bante hai unka mean nikala jata hai , Agar Koi naya datapoint us Region mein aata hai toh wohi Mean Humara prediction hota hai 

**How to find Spliting Criteria ?**
Ok sabse Pehle hum X-axis Pe saare Points yah hours ko ek ek Karke Lenge Aur Unka MSE nikalange
Jis point ka MSE Minimum hua Uss point ko hum Root node maanke split kardenge Yehi process Hum bar bar Repeat karenge Har point Ke liye Tree bananke liye 
Lekin Agar Har point ke liye karenge toh Har Point split ho jaenga jisse Overfitting ka case ho skta hai Isse Bachne ke liye Hum No. of Points Ka ek threshold set kardenge 
Yeh threshold Ensure karenge Ki Split karne ke liye Ite Points Hona jaroori hai Group mein Agar Kam hai Toh Hum split nhi karenge Aur Jo point split Nhi hoga WOh Leaf banke reh jaenga 
Yeh No. of Points(THreshold) Ek hyperparameter hai Jisse Tune kar skte hai Iski Normal value 20-25 hoti hai Data set pe depend karta hai 
Eg.![[Pasted image 20260228184744.png]]
Ab iss me Dikkat Yeh hai ki abhi Humare pass sirf ek hi Indepdent variable hai Hours Agar 1 se zada variable hote toh kya karte ? 

**How to Handle Multiple Independent Variable ?**
![[Pasted image 20260228185240.png]]
maan ke chalte hai Humare pass 2 Input variable hai (CGPA , HOURS) aur ek output variable hai MARKS Karke. Ab inka plot 3d mein banega Jisme X-axis pe Hours aaenga aur Y-Axis pe marks and Z-axis pe CGPA Ab data ko split karne ke liye sabse pehle Hours aur CGPA ka independently Graph plot karenge with Output variable Marks aur dono MSE nikal lenge. Toh yeh kuch aise niklenge for Hours : MSEh      For CGPA : MSEcgpa   
Ab hum dono MSE ko compare karenge aur jiska MSE chota hoga Uske Parallel mein Hum split kardenge data kko 3D Original Graph mein Eg. Hours ka MSE Chota hai toh Hum Hours ke according Split karenge Data kko With No. of Points Threshold value is 4 
Ab data split hogya Do Children mile ab agr children Mein 4 points hai sirf toh woh leaf node banke reh jaenga usko aage split nhi karenge Uska sirf mean nikal denge 
Agar Points 4 se zada hai toh woh furthur split hoga On the basis Of MSE Of Hours vs CGPA again 
Jiska MSE kam Woh Naya Spliting Criteria Banega Jaise iss Bar CGPA ka MSE kam hai toh woh spliting criteria banjaenga 
Bas iss process Ko repeat karte Rehenge again and again jab tak Saare Leaf Node na ajaye jinme 4 se kam point hai aur Bas unka Mean nikal ke dedenge 

**Note :** MSE calculate karne ke liye Har point ka uske region ke mean se distance nikala jata hai aur uska square karke sum kiya jata hai 