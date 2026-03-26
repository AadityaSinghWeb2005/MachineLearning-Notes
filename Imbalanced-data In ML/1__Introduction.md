****
**What is Imbalanced Data ?**

- Imbalanced Data woh dataset hota hai Jiska Output mein sirf ek Class Dominance dusri Classes ke comparison mein Eg. Student Placement data mein : 500 Total students = 450 Placed , 50 Not placed. Toh aap dekh skte hai ki Placed Wale kuch zada hi hai incomparison to placed 
- Isko diagram mein dekhe toh yeh kuch aisa dikhega : ![[Pasted image 20260325101414.png]]

****
**Problems with Imbalanced Data**

- **Bias :** Hum agar Koi ML algo iss imbalanced data pe chalaenge toh woh Algo Majority data pe zada dhyan in compariosn to minority jiski wajah se Uska Result bhi Sirf majority data pe Accha aaenga aur Minority pe accha result nhi aaenga Mtlb Ml algo biasness karega 
- **Metrics are Not Reliable :** kuch Metrics jaise accuracy reliable Nhi hote imbalanced data ke case mein 

****
**Why studying imbalanced data is Important ?**

- Imbalanced data is omnipresent 
- kuch aisi Fields hai jaha Machine learning Bohot hi jada important hai Jaise Finance (Credit card fraud detection), Healthcare(disease Prediction) , Customer Internet Jaise Netflix(Churn prediction), Environment science (Earthquake Prediction)
- In Sbhi problems mein aapko imbalanced data milega jisme Minority class bohot choti hai Har koi fraud nhi kar rha hai , Earthquake roz nhi aarhe hai 
- **Interview POV se Important**

*****
**How to solve Imbalanced Data Problem ?**

1. **Undersampling :** Yeh ek technique hai jisse balance Pane ki koshish karte hai Humare imbalanced data Mein Jisse Dono Majority and minority class ko Equal karske by Random sampling of Majority class mtlb Majority class se Random no. of sample uthao Utne hi random no. of sample uthana Jitena data points Minority class mein hai And bas Humare Data equal hogya Example : ![[Pasted image 20260325103234.png|341]] Yeh Bias Mein reduction karta hai , Traning time kam lagta hai Mtlb faster training. but We are loosing A lot of data jisme hoskta hai kuch Important bhi ho skta tha , Sampling bais bhi ho skta hai (mtlb Ho skta hai kisi ek type ke points ko lele aur dusre type ke points ko ignore karde). Very Useful technique.

2. **Oversampling :** Random Oversampling bhi kehte hai isse jisme Hum Minority class ko badhate hai by copying the Random data points of Minority class again and again jab tak Woh majority class ke equal nhi aajate ![[Pasted image 20260325104020.png]] Yeh bais Ko reduce karta hai. But isme size badh gya dataset ka . Duplication ki wajah se Overfitting ka case ban skta hai Kuch Ml algos ke case mein jaise Decision Tree classifier jisme Kuch Points pe bar bar train hoga.

3. **SMOTE(Most Popular) :** yeh bohot popular technique hai Imbalance dataset ko handle karne ke liye iski full form hai : Synthetic Oversampling Technique Yeh Oversampling technique ahi Mtlb Hum Minority class ko badhate hai but isme Minority classs ko badhane ke liye Duplication ka use nhi karte Hum naye data points add karte hai Minority class Ab yeh naye data points kaise banaye ? yeh ek interpolation technique use karta hai jisme do Minority class ki original points ke beech Data point banaenge
		**Algorithm of Creating a New Data Points :**
		1. Sabse Pehle Minority class ke har original point pe KNN train karke Uske 5 Neighbours pata karlonge 
		2. Phir aap ek random point uthanege Minority class se 
		3. Phir aap us random point ka ek random Neighbour select karenge Interpolation process ke liye 
		4. Ab Aap Ek random Number generate karenge 0 se 1 tak iska naam hoga factor 
		5. Phir naya data point banane ke liye HUm ek formula use karenge Which is New Data point = original Data Point Coordinate - Factor(Original Data Point Corrdinate - neighbour Coordinate )
		6. Example : ![[Pasted image 20260325105657.png]]
		7. yeh naye point ke coordinate jo Original Point aur uske Neighbour ke beech aaenge 
		8. yeh process aap tab tak repeat karenge jab Minority class Majority class ke equal na aajaye 
	1. **Limitation :**
		1. Does not Handle Categorical Data well 
		2. Computation Complexity 
		3. Sensitive to Outliers
		4. Its Not necessary that You synthetic Data Shows same distribution as Your Original Data

4. **Ensemble Methods :** Hum Ensemble methods ki help se Data mein balance Late hai. Isme hum ek technique use karte hai Balanced Random forest Jisme Hum Majority class ko Ute Parts mein baat lenge Jite Minority class ka data se equal bane Kuch iss tarah : ![[Pasted image 20260325193340.png]] Aur Model Train Karenge iss data pe teen model train honge aur Unke Output pe aggregrate process lagalke Final Output Nikalenge 

5. **Cost Sensitive Learning :** Isme mein aap Model ke learning mein thoda Tweak karke Imbalanced ko handle karne ki koshish karte ho. isme pehla Method aata hai Class Weights Jisme Aap Output mein classes ko weight assign karte ho Aap Minority ko jada weight assign karte ho comparison to Majority Class Taki Model jada dhyan Minority class pe de sake aur Isme Kam galtiyan ho skae. Mtlb Model Minority CLass pe jadad dhyan dega. Second technique hai aap Custom loss function ka use karte ho 

**Note :** There are Many More Methods to solve imbalanced Data problems 
