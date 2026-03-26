*****
**Introduction**

- naive Bayes Classifier Simple Cheeze use karta hai Example se smjhte hai 
- Ek dataset hai CSK ka Jisme features hai toss , weather , Venue , Result 
- Result Ouput column hai with binary classification WIn or Lost toh Naive bayes kaise kaam karege woh dekthe hai 
- Ek input data aaya {Lost , Sunny , Mumbai} toh naive bayes do prob nikalega P(W) and P(L) win or loss dono probability with respect to input features 
- P(W | Lost Intersection Sunny Intersection Mumbai) : probability of Win 
- P(L | Lost Intersection Sunny Intersection Mumbai) : probability of Loss 
- jiski Probability jada aaengi Naive Bayes simply Woh result dedenga 

****
**How naive Bayes calculate Probability ?**

- Hum bayes theorom ka use karenge jisme A = w and B = Lost , Sunny , Mumbai
- AUr formula mein value put kardenge 
- iss bayes theorom ke Formula mein value put karne ke baad Denominator Calculaet krni ki jaroorat nhi pdti kyunki Woh Dono cases mein same W aur L ke case Jisse iska koi impact ni padta final result mein 
- toh Hum Numerator pe dhyan denge 
- Ab Bayes theorom iss dataset pe kuch aise lagenga 
- For P(W | Lost , Sunny , Mumbai) : P(Lost,sunny , Mumbai | W)  P(W) / P(Lost, sunny , Mumbai)
- For P(L | Lost , Sunny , Mumbai) : P(Lost , Sunny , Mumbai | L) P(L) / P(Lost, sunny , Mumbai)
- Ab ek problem hai Humare iss specific dataset mein Win wale case Ke liye Koi aisa combination nhi hai Features ke Jisme Lost , Sunny , Mumbai ek saath aarhe ho Win ke liye toh iski prob zero hogi Right ? No Iss algo naive bayes Isliye Kehte hai Kyunki Naive hai Mtlb yeh assum karta hai toh yeh kya karta hai Puri badi prob ko tod leta hai kuch aise 
-  P(Lost , Sunny , Mumbai | W) P(W) == P(Lost | W)* P(Sunny | W) * P(Mumbai | W)* P(W)
- Hume bas har feature ko specific win probability nikal li tohinki value banegi 
- 1/5 * 2/5 * 4/5 * 5/8 = 0.2
- So P(W | Lost , sunny , Mumbai) = 0.2
- Same way P(L | Lost , sunny , Mumbai) = 0.4
- so final answer would be 0.4