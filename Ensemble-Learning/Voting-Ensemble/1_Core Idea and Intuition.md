
### **Intuition**

Hum ek dataset ko Multiple Model ke through train karke Ouput nikalte hai 
Agar classification problem hai toh Majority ke base pe final output Decide hota hia 
Agar regression Problem hai toh Final Output ke liye Hum Base Models ke output Ka mean lelete hai 
**Note** : Saare Base models Independently Train hote hai 

### **Assumptions**

1. Base models independent hone chaiye ek dusre se alag hone chaiye 
2. Sabhi Base Models ki accuracy 50% se zada honi chaiye Kyu agar 50% se kam hogi toh humara jo voting ka result Aur bhi kharab aaskta hai 


### **How voting works ?**

Agar ek model glti kare toh dusra model usko cover karta hai Isliye Majority sahi decision De pata hai 
Diverse Model Ek dusre ki weakness chupa skte hai Isliye base models independant hona jaroori hai 


### **Mathematical Proof**

How voting Improves Accuracy We will prove it with the help of Maths 

man lo teen model hai Model 1 -> Accuracy 0.7 
Model 2 -> 0.7 
Model 3 -> 0.7 
Mtlb 70% chance Hai prediction sahi hone ki In individual models se aur 30% chance Hai fail hone 
Ab hum ek voting classifier Banaenge Usme Majority Prediction lenge Jisme Minimum 2 Sahi Hone Chaiye Out of 3 
Saare Sahi ke case mein : 0.7 * 0.7 * 0.7 = 0.343 
2 sahi ke case mein 3 ways hai Each case:
0.7 × 0.7 × 0.3 = 0.147
Total:
3 × 0.147 = 0.441

Final Voting Classifier Accuracy : 00.343 + 0.441 = **0.784**
Means Voting classifier kii accuracy Individual models ke accuracy se jada hai Mtlb yeh accuracy improve kar rha hai 

Yeh ek aur Cheez Dikhati hai Humne ek rule padha hai Ki har Model ki accuracy should be greater than 50% If not then Humare Voting classifier ki accuracy aur Kharab aaengi it will be lesser than 50 % mtlb voting classifier Accuracy ko Aur khrab kar rha hai 
Mathematical Proof : manlo models ki accuracy hai 30% percent ab upar saari values mein 0.7 ki jagah 0.3 rakhenge aur 0.3 ki jagah 0.7 rakhenge 
Toh jo final voting classifier ki accuracy aaengi Woh around 20% aaengi Which is actually bad than base model accuracy 