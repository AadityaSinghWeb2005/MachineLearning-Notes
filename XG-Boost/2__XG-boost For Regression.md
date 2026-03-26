
****
**Introduction**

- XG-Boost Regression ki setting mein kaise kaam karta hai 
- XG-Boost Internally Gradient boosting hi hai Toh yeh bhi waise Hi mostly kaam karega jaise gradient boosting kaam akrta tha Regression ke liye 
- Jisme Aap Multiple base Models banate ho 
- First Base model mein Aap sirf Mean lete ho Output column ka aur Wohi Predict karta hai aap aab First base Model ka pseudo residual nikalte ho Mtlb error nikalte ho by Subtracting the First Model prediction with Actual Ouput 
- Second base model mein aap ek decision tree bante ho jisme aap input mein input columns dete ho aur output column mein First Base Model ke Residuals dete ho yeh decision Tree yeh calculate karta hai Error kita kar rhe ho aap aapka error predict karta hai 
- Ab aap isme residual calculate karte ho isbaar Galtiyan kam hoti hai in comparison to First model 
- Third model mien aap wapas decision tree banate ho With same inputs but As output aap second models ke residual ko dete ho 
- **One major difference in XG-Boost :** SO XG-boost ka flow toh same hota hai GB se jisme mein hum base models ko combine karke result nikalte hia Lekin GB mein Hum Decision Tree banate waqt gini Impurity yah entropy ka use karte hai but in ==in XG-Boost hum Different criteria use kte hai Decision tree banane ke liye== 

****
**How Decision Tree Formed in XG-boost ?**

- **Step by Step Calculation**
- **Step-1 :** Hum Model-1 banaenge jiska Ouput hoga Simple Output column ka mean. Phir Model-1 ki galtiyan Nikalenge Residuals-1 
- **Step-2 :** Ab Hum Model-2 mein jaenge Aur ek Decision tree Banaenge With Normual Input columns as Input and Output column as Residuals-1 ab iss tree ko banane ke liiye Hum sabse SS nikalte hai SS(Similarity Score) = (Sum of All residuals)^2 / Number of residuals + $\lambda$ in which lambda is regularization Term.Ab Hum Data mein spilitng Criteria Different wale try karenge aur Jis bhi Spliting Critieria pe Gain jada hai Usse root node maan lenge. Gain Kaise nikalte hai ? sabse Pehle saare spliting criteria mein jo bhi leaf nodes bane unka sabka SS(similarity Score) Nikal rhe hai Ek spliting Criteria ke do nodes bane left leaf node and right Leaf Node ab In dono leafs ka SS calculate karenge aur phir inke Parent Node yah Spliting criteria ka Gain calculate karenge iss formula se Gain = Left SS + Right SS - Root SS. Isse Tarah saare spliting criteria ke Gain nikal lenge aur jiska gain zada hoga usi par data ko split kiya jata hai 
- **Note :** XG-Boost Mein Default Tree ki depth 6 hoti hai 
- **Step-3 :** Ab hum Jo decision Tree banaya hai umse Output nikalne ke Liye leaf Node ki help se Hum ek formula ka use karenge Output = sum of residuals / number of residuals + $\lambda$
- **Step-4 :** Ab Overall model ka output nikalenge Jo nikalenge iss formula se : Model-2 prediction = previous Model Prediction + (learning Rate * Decision Tree Ouput (for that particular Input)) Ab Hum Model-2 ke Residuals Nikal lenge 
- **Note :** XG-Boost mein Default Learning Rate 0.3 hi hota hai 
- **Note :** Agar Residuals ki value Zero ki taraf ja rhe ho toh sahi direction mein ja rhe hoo