
****
**Introduction**

- Gradient Boosting ek Ensemble Technique hai jo boosting Category mein aati hai 
- isme multiple weak Learners ko stagewise add kiya jata hai taaki ek strong Model ban ske 
- is Model ko additive Modeling kehte hai 
- **Goal :** isme Jo weak learners Use hote hai Model woh High Bias Low variance Hote hai Insabko jod ke aap Low Bias Low varaince condition ko acheive karne ki koshish karte hai 

****
**Classification VS regression in Gradient Boosting**

- Gradient boosting Classification bhi wohi algorithm use karta hai jo Gradient boosting regression use karta hai Mostly 
- The Only difference is hum Regression mein least square Method ko loss function mein us kar rhe the but in classification Hum Logg Loss Ka use karenge 

****
**How Gradient Boosting works in Classification ?**

- Humare goal hai Classification ke liye ek Strong Model banana Jo combination hoga weak learners ka 
- Abhi ke liye hum Teen Models Lenge Sirf Jisme First Model simple model hoga aur baki 2 model decision Tree honge 
- Ab hum Three stages mein in models ko handle karenge 
- **First Stage : Handling Model-1**
	- hum Log(odds) calculate karte hai log(odds) ka mtlb hai log(Number of Ones in Output / Number of Zeroes in Output) Ex : log(5/2) Mtlb Ouput mein 5 Ones hai and 2 Zeroes hai aur Inke divide ka log lelenge bas Yehi karna First Model ke value ke liye 
	- **Note :** Hum Log base e use karenge instead of Log base 10 
	- Ab Hume Aage ki stages mein residuals nikalne padte hai woh nikalte hai Actual value minus Predicted value but in this Case Actual value 0s yah 1 Mein hai  hai aur Predicted (log(odd) value) Continous values hai 
	- toh hum in Actual values ko Probability mein change kardenge with the help of this formula : $1/1+e^-log(odd)$
	- iska Ouput Woh probability hogi jis probability Dominance Actual Output Mein hoga Ex. Jaise agar ouput column mein 1 jada hai toh yeh Probability 0.5 se zada hogi aur agar 0s zada hai toh yeh prob 0.5 se kam hogi 
	- Ab hum iss Model ki galtiyan Calculate karenge Which is Residuals By Pseudo Residual Technique (Actual Value - predicted Value) so iss case mein hoga Actual Ouput Column - Probability column AUr iss column ka Naam hoga res1 
	- Yeh bataenga humare Model 1 mein kiti galtiyan hai 
- **Second Stage : Handling Model-1 and Model-2**
	- Ab Model-1 ki galtiyon ko as a Output and Actual Input columns ko hum ek decision tree regressor mein denge (Regressor isliye kyunki Output Continous values mein Hai )
	- Ab Hume Model-1 and model-2 ko combine karke inki combine prediction value nikalani hogi Lekin ek problem hai 
	- Model-1 ki prediction hai Log(odds) hai aur Model-2 ki Prediction ke liye hum Decision Tree regressor ke ouput pe depend hai Lekin Ouput nikala hai Model-1 ke Residual column ke help jo ki probability tha so Yeh ouput bhi probability aur Log(odds) aur probability ko add nhi karskte toh ab hume iss probability ko logg(odds ) mein hange karna hoga 
	- Ab Hume Yeh formula help karega : ![[Pasted image 20260317194214.png]]
	- yeh formula Hume har Leaf Pe apply karna hoga Decision Tree Regressor ke 
	- Jisme sabse Pehle Jis bhi leaf node pe Hum Log(odds) Calculate karne hai toh Yeh pata karo ki uss Leaf mein Kitne Rows gire hai Manlo 2 Rows Gire hai Toh Un Do ka Pehle Sum of Residual Calcuate karo aur usse Unki Probability(1- Probability) ke sum nikal ke Divide karado as per formula Aur uss leaf ka Log(odds) nikal jaenga 
	- Aise hi karke hum har Leaf ke liye log(odds) value Nikal lenge 
	- **Final Prediction :** final Prediction hoga Model 1 + Model-2 ka Combine Prediction hogi Woh Calculate krne ke liye 
	- Mujhe sabse Pehle har row ke liye Final Log(odds) value banane hogi Jo hogi : Model-1 Prediction (pred-1(log(Odds)) + har Row Jis Leaf mein Gir rha hai Uska Log(odd) and After that we got pred-2(log(odd)) which is the final prediction of Combination of Model-1 and Model-2 
	- Ab Hume iss stage ka residual calculate krna hai res2 : which is calculated by Actual Output(y) - pre2(probability) ( yeh probability column hoga Humare final Prediction wale Columns Pred-2(log(odds)) Humne Saare Log(odds) ki value ko proabibility mein change kar diya with the help of this formula :$1/1+e^-log(odd)$  ) aur Hume phir Res2 mil jaenga Jo Mistakes Hogi Jo Yeh super model kar rha hai (Model-1 + Model-2)
- **Third stage : Handling Model-1 , Model-2 and Model-3**
	- Ab ek naya Decision tree banaenge jisme Actual Inputs aur Res-2(Mistakes  of Super model(model-1 + model-2)) as a output Column denge 
	- **Note :** res-1 Hai Mistakes of Model-1 and res-2 combined mistakes of model-1 and Model-2 agar aap inka difference dekhonge toh bohot bada lagega iss diff ko aap control kar skte ho With the help of learning Rate 
	- Ab Humare pass Model-1 + model-2 + model-3 Hai Iska Ouput nikal lana hai Log(odds) ke term mein 
	- model-1 ka value hai Model-2 ke bhi Leaf Nodes ka Log(odds ) value hai 
	- Ab hum model-3 ke decision Tree ke leaf nodes ko Log(odds) mein convert karna hai 
	- ![[Pasted image 20260317194214.png]]
	- With the help of this Formula again 
	- Ab hum har row ko dekhlenge woh konse leaf node mein jaake gira hai aur jab pata chal jaye kon kon se row kis leaf node mien jaake gire hai 
	- Hum un rows ka residual (res-2) sumission kar ke unki probability se divide kar denge according to formula aur Hum pure Leaf ki value Log(odd) mein convert ho jaengi 
	- Ab hum prediction-3(log (odds)) nikalenge kaise bas Hum har row ke liye Log(odd) nikalna hai Kaise nikale?
	- Pred-2(log(odds)) + us Leaf ka Log(odd) value jisme woh particular Row Gir rha hai 
	- final ouput Hum kabhi log(odd) mein nhi De skte unhe probability ke terms mein hi dena padta hai so bas pred-3(log(odds)) ko probability mein change kardenge with the help of this Formula : $1/1+e^-log(odd)$

****
**Geometeric Intuition**

- [Ref-Material](https://towardsdatascience.com/all-you-need-to-know-about-gradient-boosting-algorithm-part-2-classification-d3ed8f56541e/)
