****
**What is Feature Importance and Why it is Used ?**
Feature importance Hum apne Features ko Importance wise quantify karne mein help karta hai jiski help se hum High Importance wale features ko rkhte hai aur bakiyo ko hata dete hai 
Random Forest by Default nikal pata hai Important features ko 
Feature importance hume Interpretability bhi deta hai Mtlb example se smjhte hai 
**example :** Loan dena hai ki nhi aisa Model bana rhe hai Isme Yes yah No target hoga ab agar user puch le Ki aapne Loan No yah yes Kyu bola Toh Most feature Important feature ki help se bata skte hai ki iss waja se nO yah iss feature ka sbse jada impact hai 

****
**How Feature Importance is calculated ?**
First Lets Try To calculate the Feature Importance with the help of Decision tree :
	![[Pasted image 20260311134135.png]]
	this is the formula 
	isme Fi hai Feature Importance and ni hai Node Importance 
	Sabse pehle Node Importance nikala jata hai Formula ke help se jaise 
	**n_t** : Number of Rows in Feature 
	**N** : Number of Rows in Dataset 
	**impurity** : Impurity of that particular Feature 
	**N_t_r** : number of Rows in the particular Feature Right Children 
	**right_impurity** : Right children ki impurity 
	**N_t_l** : number of Rows in the particular Feature Left Children 
	**left_impurity** : Left children ki impurity 

in Fi Numerator Mein Use Node ki importance value rkhte hai jiki nikal rhe hote hai 
Aur denominator mein sabhi nodes ki importance ko Add kardete hai 

In Random Forest , Sabse pehle jite bhi decision Tree banenge Unka Importance calculate hoga Har feature phir Un saare features ka Average Calculate hoga Aur wohi Random Forest ka Feature Importance number banega 