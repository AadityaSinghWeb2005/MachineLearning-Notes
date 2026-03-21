****
**Introduction**

- Support Vector Machines Logistic Regression Ke bohot similar Hai 
- SVM kya karta hai Yeh Ek boundary line yah Hyperplane se Data ko Correctly Classify karta hai jaise Hum [[Logistic-regression/1__part|1__part][LogisticRegression]] Mein karte the but isme Kya twist hai ki
- Yeh  Data ko  Widely classifiy karta hai Mtlb yeh data aur boundary line ki distance ko maximum karta hai 

**Core Logic**

- So hum aisi boundary Line Select karte hai Jo margin(Gap between line and data) Ko maximize kare isliye Hume isse Margin maximizing Hyperplane kehte hai 
- **How to find that Hyperplane or Line ?** 
	- toh hume aisa hyperplane dhoondhna jiska Margin maximum ho taki hum data ko correctly classify kare ek generalized model banaye
	- Uske Sabse Pehle ek Random hyperplane intialize kijiye ab iss random hyperplane ke Parallel mein Hyperplane bante jaiye 
	- kab rukna hai Jab koi Hyperplane Positive Region ke last point ko touch na karle aur dusra Hyperplane Negative region ke first Point ko touch na karle In short aapne Data Mein ek randomly Hyperplane intialize kiya uske dono taraf Hyperplane banana shuru kiya Postive Region mein Hyperplane + and Negative region mein Hyperplane - . Jaise Dono Hyperplanes ko apna First Point mil gya data ka woh ruk jaenge 
	- then bas Hyperplane + and Hyperplan - ke bich ki distance nikal lenge 
	- Ab aise Hi Hyperplane Banate jaiye aur Unka + and - version nikal ke distance calculate karte jaiye 
	- Jis bhi Main Hyperplane ke + and - variants ki Distance jada hogi wohi aapka Hyperplane select Hoga Iss algorithm mein 
	- ![[Pasted image 20260320124334.png]]
- **Support Vectors :** Jin points pe aake Humare Main Hyperplane ke + and - variants aake rukte hai Un points ko Hum Support Vectors kehte hai 
- SVM is robust to outliers Iss algorithm pe Outliers ka impact nhi padta 
- Yeh SVM Algorithm Non-linear Data pe Bhi accha Work karti hai 