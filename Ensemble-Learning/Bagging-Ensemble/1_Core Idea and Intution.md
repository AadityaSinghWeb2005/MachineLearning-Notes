
**What is Bagging ?**
Bagging Do words se bana hai Bagging and aggregration 
Bagging mein Generally Same algorithm ka use karte hai Base Models banane ke liye aur ab in base models mein Hum Ek dataset Denge 
But ab isme ek twist hai Hum Ek saath dataset nhi dete sab models mein 
Hum Datasets ko sub datasets mein convert kardete jo different hote Hai ek dusre se 
Ab In datasets ko hum Models Mein Daalte hai Aur prediction lete hai Agar classification hai toh Majority Vote Concept ka use and if Regression Then we use Average 
Dataset ko sub datasets mein todna is Bagging 
Prediction Process is called Aggregration 

**Why We need Bagging ?**
Bagging Ke sahi use se Hum Low baise Low Variance Wali condition Activate kar skte hai. Kaise Kar skte hai ? 
Sabse pehle Hum Woh Algorithm lete hai Jisme Low Bias High Variance hota hai Jaise Decision Tree(Max_depth = None) Jo overfitting karta hai 
So jab Hum Sub Dataset Dete hai Models mein hum Dataset mein 100 Nay Rows Jod dete hai Ab kyunki Rows Distributed hai Base Models mein toh ho skta hai 50 new rows M1 ko mile , 30 Rows M2 ko Mile , 0 M3 ko Mile (jisme M1 M2 M3 base Models hia )
Ab Dekh 100 Nay rows Judne ka effect Ita nhi Models Ke performance per Kyunki effect distributre Hogya Jisse Variance thoda Low Hogya aur performance Consistent Hogyi 
Isse Hum Low Bias Low Variance ki Condition acheive Kar skte hai 

**When To Use it ?**
When You are dealing with Low Bias High Variance Model Eg. Random Forest 

**Types of Bagging**
1. **Pasting :** isme Aap Same Row sampling karte ho but without Replacement 
2. **Random subspaces :** Isme hum Row sampling Ki jagah column Sampling karte hai With or Without Replacement 
3. **Random Patches :** Isme Hum Row Sampling and Column Sampling Ek saath performe karte hai with or Without Replacement 