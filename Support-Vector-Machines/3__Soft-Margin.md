
****
**Introduction**

- SVM mein Hum Data agar Close to linear Hai mtlb data mein kuch Points missclassified hai yah Thode Outliers hai Toh Hard Margin Waha fail hojata hai Uske Constraint ki wajah se 
- Isliye Hum Aisi Situations ke liye Soft margin ka use karte hai 
- Ab Hard Margin mein argmax(w,b) 2/||w|| kartehai iska mtlb hota hai Maximizing the distance but in the soft margin we do opposite Hum Yhe karte hai argmin(w,b) ||w||/2
- Soft Margin Mein overall Formula use hota hai : ![[Pasted image 20260320200600.png]]
- Ab Yeh Zeta $\sum \zeta_i$ Hota hai Distance between Missclassified point with respect to their Hyperplan Variant. Mtlb Jaise Agar Kuch Point Positive Region ke the but woh negative region mein hai Toh un point aur positive Hyperplane ki beech ki distance ko Zeta kehte hai same fore Negative Points in positive Region 
- Zeta Classified ke liye zero hota hai 
- Zeta term ko Hum classification Error Kehte hai aur Minimize Margin ko Margin error kehte hai 
- In dono ke combination ko Objective Funtion kehte hai jo ss mein de rkha hai 
- Isme Hume ||W|| ki value Ko minimize karta he Hai Taaki Margin maximize ho Jita jada margin hoga utna Better Generalization 
- Zeta term : Isme hum saari Galtiyo ko calculate karke sum kar rhe hai Aur C ek hyperparameter hai jo batata hai Ki Galtiyon Ko kitna serious lena hai Agar C ki value jada kardi toh Galtiyan Bilkul allowed nhi hai margin chota ho jata hai. Har point fit karne ki koshish Ovefitting ka case 
- Low C value . Errors allowed hai Margin Bada hota hai aur 
- **Soft margin SVM ka Loss function Hinge Loss Hota hai**
- C∑ζi​ isse **hinge Loss** Kehte hai 
- Aur ![[Pasted image 20260320201920.png]]
****
**THE END**
