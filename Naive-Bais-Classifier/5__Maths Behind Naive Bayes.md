
*****
**Introduction**

- Maan Lo ek vector hai X = {x1,x2,x3.......} and aur yeh ek vector hai Ck = {C1, C2,C3.....}
- ab X toh features tumhare yani columns and Ck hai classes hai Outputs eg. C1= Won , C2=Lost , C3 = Draw
- According to bayes theorom hum isko aise likh skte hai 
- P(Ck | X) = P(X | Ck) P(Ck) 
- Denominator same hi hai sab ke liye toh usko ignore marenge woh constant hai 
- Ab Hum P(Ck | X) ko simple condition probability ke form mein likhe toh hum isse aise likh skte hai P(CK | K ) = P(X,Ck) where , is intersection 
- Now Hum X ko x1,x2,x3,x4..... mein likh lenge 
- toh yeh ban jaenga P(x1,x2,x3,x4......xn,Ck) 
- Ab yaha pe , ka mtlb hai Intersection toh P(x1, x2,x3,x4,...Xn,Ck) hum inko Again Condition probability ke First form mein likh skte hai kuch asie P(x1 | X2,x3,x4,....,Ck)P(x2,x3,.....Xn,Ck)
- Ab P(x1 | X2,x3,x4,....,Ck) isme x1 sirf Ck pe depend karta hai toh hum isse aise likh skte hai P(x1 | Ck)
- Aur ab hum aise hi todte jaenge P(X1|Ck)P(X2|Ck)....
- toh final Formula kuch aisa Banega 
- $$P(Ck|X) = \prod_{i=1}^{n} P(x_i|Ck)$$
- toh Final Prediction ke liye Yeh form hogi 
- y = argmax k ={1,2,3}$P(Ck|X) = \prod_{i=1}^{n} P(x_i|Ck)$
- This Rule is called maximum a posterior rule jisme hum final ouput Mein Maximum probability ko dete hai kisi given Class ke liye 