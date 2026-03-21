****
**Additive Modeling**

- Gradient Boosting Additive Modeling Ke concept pe kaam karta hai Jaha ek complex Function ko Chote chote Functions (weak Learners) mein Solve Karke Solve Kiya Jata hai 
- **What is Additive Modeling :** Machine Leaerning Mein Hum Input(X) and Ouput(Y) ke beechrelationship(function) dhundhte hai jab data Bohot complex hota hai toh SImple Lines yah polynomial Kaam nhi karte. Yaha pe additive Modeling kaam aati hai Kyu koi bhi Main Function Chote Chote Function se milke bana hota hai. Main function banane ke liye hum chote chote FUntion add karte jaate hai. Same tareeke se Gradient Boosting mein decision Trees as chote function add karte rehte hai asli function tak phauch ne ke liye 

****
**Gradient Boosting Algorithm**

Algorithm Implement karne ke liye hume Training Data Chaiye (x,y) and Loss function which is 1/2sumission(Yi - Yi-cap)^2 
- **Step-1 :** humara main goal hai ki x and y ke beech relationship nikalana hai jo Y = F(x) ab F(x) nikalne ke liye hum iska use karenge f(x)0 + f(x)1 + f(x)2 +........ Step 1 mein hum bas f0(x) ki value nikal ke Liye hume Mean Nikalan hoga Ouput Column ka 
- **Step-2 :** **Iterative Process (The Loop)**
	- Yeh Process M times chalta hai M Mtlb No. of decision Trees Present 
	- **Pseudo residual :** Har row ke liye hum error calculate karte hai Error Actual value aur predicted value ka difference hota hai 
	- **Fit a Decision Tree :** Ab hum ek naya decision Tree fit karte hai jisme Input same rehta hai but target yeh Residuals hote hai 
	- **Terminal Regions :** Decision Tree Data ko alag alag Leaves (region) mein divide kardeta hai 
	- **Calculate Leaf Ouput :** Har leaf ke liye ek optimal ouput value calculate ki jati ai jo loss ko minimize kare. LSE loss ke case mein , Yeh use leaf mein girne wale residuals ko average hota hia 
- **Step-3 : Update the Model**
	- Naya prediction calculate karne ke liye naye tree mein purane tree ka prediction add kar diya jata hai 
	- **Final Formula :**$F_m(x) = F_{m-1}(x) + \nu \cdot \sum \gamma_{jm}$ _(Yahan $\nu$ learning rate hai jo model ko slow aur accurate banata hai)_

****
THE END 
