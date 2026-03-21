
****
**What is Stacking ?**

- Yeh Voting Ensemble se Similar hai Jaise Hum voting ensemble mein Base Models ki Helpse prediction karte the isme bhi hum kuch similar karenge 
- Hum sabse dataset se Base Models ko train karaenge aur phir Jo un base Models ka Ouput aaenga Woh ek Naye Model (meta model) mein As a Input bhejenge aur Ouput mein Original ouput bhejenge Training Ke liye 
- Training ke baad jo bhi prediction aaenga Meta model se wohi humara final prediction Hoga 
- **Difference B/w Stacking and Voting** : voting mein mean aur majority voting ka use karte the yah hum bas meta model ke prediction ko final ouput maan lenge Waha base model same ho skte hai but stacking mein base different hote hai 
- **Problem In Stacking :** Stacking mein Overfitting ka Case banta hai Kyunki hum bar bar Har model ko Ek hi dataset pe train kar rhe hai isse Meta Model aur base models Overfitting karne Lag jaenge 
- **Solution :**
	- **Hold Out method :** Iss method mein hum data ko train test mein split karlete hai aur train data ko bhi do part mein split karlete hai first part base models ki training ke liye use hota hai second part Meta Model ki training ke liye use hota hai. Jab hum stacking iss method se karte hai toh woh Blending Kehlati hai 
	- **K-fold Method :** K-fold method mein hum sabse Pehle data ko Training aur testing Data mein tod lenge. Phir K ki value decide karenge lets say k = 4 Ab hum training data ko K parts mein divide karna hai randomly ex. maanlo Training data mein 800 Rows hai toh K = 4 ke liye 4 folds bananenge 200-200 rows har fold mein 200 row Now Ab Hum Ek ek karke apne base Model Ko in folds pe Train karenge leking Sirf 3 Folds pe Train karenge aur 1 fold pe test karke Prediction nikalenge 
	- Ex : Maan teen base Model hai LR, KNN,SVR ab sabse Lr train hoga 3 folds par aur 1 fold par prediction karega toh naya column Banega LR_predict ab hum Rearrange karenge folds aur 1 naya fold lenge Prediction ke liye aur phir LR_predict ko update karenge Aisa hum jab tak karna hai  jab tak Har fold ke LR_predict na aajaye toh LR_predict ka size 800 ho jaaenga rowwise Aise hi Hume Har base Model ke liye karna hai toh isse Yeh data banega : Lr_predict,KNN_predict,SVR_predict aur Actual Ouput Column Ab in charo column se hum Meta model ko train karaenge aur Test Data ki help se final Prediction lenge 

****
**Multi-Layer Stacking**

- Abhi Hum sirf ek layer Structure pe kaam kar rhe the jisme sirf ek Meta Model aur 3 Base Models 
- Lekin Multi layer Stacking bhi kar skte hai jimse 6 yah usse zada base Models ka use ho skta hai Kaise kuch iss tarah ![[Pasted image 20260318112124.png]]
- Yeh kaam kaise kartahai first Hum data ko Do hisse Mein tod lenge training And testing data Training data ko aur Teen parts mein tod lenge T1 , t2 , t3 
- Model1 model2 model3 ko hum sirf t1 pe train karenge aur t2 ki help se Unka prediction nikal lenge m1-pred, m2-pred, m3-pred aur Actual ouput column 
- Model -4 , Model -5 Model -6 ko hum t2 pr train karenge aur t3 pe prediction nikalenge m4-predict m5_predict , m6_predict 
- Ab hum saarre prediction column aur actual ouput column ko jod ke Meta model mein dedenge  training ke liye 
- Aur Dtest ki help se r2 Score calculate karlenge 