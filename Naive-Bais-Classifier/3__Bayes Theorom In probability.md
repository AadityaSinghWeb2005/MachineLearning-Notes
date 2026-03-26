****
**Introduction**

- Naive Bayes Classifier Issi Thoerom pe based hai 
- Bayes theorom kehta hai ki agar aapke pass Do Events hai A and B toh 
- ![[Pasted image 20260322113034.png]]
- in Which P(A | B) is posterior Probability and P(B|A) is liklehood and P(A)  is Prior and P(B) is evidence 
- Given p(B) != 0 
- **Prove :**
	- ![[Pasted image 20260322113146.png]]

****
**Sample Problem Upon Bayes theorom**

- **Question :** There is a factory. Factory mein thee machines hai M1 M2 M3 Jo marker banati hai agar 100 marker ban rhe hai toh M1-20 , M2-30, M3- 50 ban rhi hai M1 mein 5% Material Defective hai , M2 mein 3% material defective hai , M3 mein 1% Defective hai. Question is Humne Pure batch mein se Ek Marker uthaya Aur woh defective nikla Uski kya prob hai ki woh M3 se bana hai 
- **Soln :** Probability of M1 = 1/5 and P(M2) = 3/10,P(M3) = 1/2 . Ab defective piece ki probability kya hai Defective Piece ki probability jab M1 ki proabability hai toh yeh ek conditional prob banegi. 
- P(D | M1) = 1/20 , P(D | M2) = 3/100 , P(D | M3) = 1/100
- Ab question mein de rkha Hai Hume probability dikhani hai ki marker M3 se defective hai 
- P(M3 | D) = ( P(D| M3) P(M3) )/ P(D) According to bayes theorom 
- Ab P(D) probability of defective mtlb Total defective ki probability 
- P(D) = P(D intersection M1) prob defective hone ki M1 se  + P(D intersection M2) prob defective hone ki M2 se  + P(D intersection M3) .....
- Condition probablity ki help se P(D | M1) = P(D intersection M1) / P(M1)
- So aise Hum P(D int M1) aur ... bakiyo ki value nikalenge aur finally bayes theorom formula mein put kardenge 