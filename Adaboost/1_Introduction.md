****
**How Adaboost Classifier Works ?**
Its a boosting Algorithm 
**Weak Learner :** woh machine Learning Model jiska Accuracy Less than 50% Hota hai 
Ada boost mein multiple Weak Learners ko jod ke Ek strong Learner Banate ho Jiski Accuracy High Hoti hai 
**Decision Stumps :** Woh Decision Tree Hote hai Jo sirf ek bhi baar split hote hai Yeh weak learner hote hai jisme Max Depth 1 Hoti hai 
**-1 and +1 :** ISs classification Mein positive Points (1) ko +1 se denote karte hai aur Negative points (0) ko -1 se reprsent karte hai 

****
**Core Idea**
Adaboost ko stagewise Additive method bhi kehte hai Jisme Additive method ka mtlb weak learners ko add karna aur Stagewise ka mtlb hai Weak learners ko Sequentially Add karna 

**How It works :** Sabse Pehle Pure data pe Ek decision Stump apply karenge Yeh Kuch points ko sahi classify karega kuch ko galat 
ab hum yaha se Do cheeze karenge sabse Pehle iss model ka weight Nikal Lenge (is model ka impact on final Result ) which is denoted by Alpha and Hum jo bhi missclassified points hai Unko Upsample kardenge Mtlb hum unki importance bada dhenge taki agli decision stump unpe jada focus kare aur unhe sahi jagah classify kare 
Iss process ko repeat karenge jab tak Saare models train nhi hojate 

**Final result :** Final Result nikalne k liye hum ek formula ka use karenge 
**$sign(\alpha_1 h_1(x) + \alpha_2 h_2(x) + \alpha_3 h_3(x) ...)$**
iss Formula mein Alpha 1 weight hai har model ka and H1(x) hai Har model ki prediction in sabko calculate karenge phir jo bhi answer aaye uska sign dekhenge 
Agar Sign +v aaya toh Final Prediction 1 hoga 
Agar Sign -ve Aaaya toh final Prediction -1 Hoga 

