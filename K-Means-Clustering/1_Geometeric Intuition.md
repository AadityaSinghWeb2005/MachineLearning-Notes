****
**Introduction** 
Clustering ek Unsupervised Algorithm hai Jo same type ke data ka group bana deti hai 
****
**How this Algorithm Works In Steps**

**Step-1 :** **Decide n Clusters**
Pehle Hume Algorithm ko yeh Batana Hota hai ki usse kitne Clusters Banane hai Algorithm 
Lets Take Number of CLusters is 3 which is denoted by K = 3 

**Step-2 :** **Intialize Centroids**
Jitni K value decide ki hai Utne Hi hume centroids Decide karte hai. Centroid hum random Data points ko maan lete hai pure data mein se 

**Step-3 :** **Assign Cluster** 
Sab points jo data mein hai Unki Eculdian Distance nikalo In Centroid Point se Jis Point ki distance kam hai Centroid se usse Point ko uss centroid ke cluster Mein assign kardo 

**Step-4 : Move Centroids**
Naye Clusters banne ke baad Un clusters ka naya center nikala jaata hai (Mean) aur Centroids ko waha shift kar diya jata hai 

**Step-5 : Repeat(Convergence)**
Step-3 and Step-4 ko jab tak repeat kiya jata hai jab tak Naye Mean aur Purane Centroid Same na aaye Mtlb jab tak Centroid shift hona band na karde 

****
**How to Know No. of Clusters (K)**

**Elbow Method**
Iss method mein Hum ek graph ki help se pata karte hai appropriate No. of Clusters With the Help of Some Terms : **Elbow Curve , WCSS , elbow Point**

- **WCSS** : iska full form Hota hai Within Cluster Sum of Square Mtlb ek cluster mein sabhi points ka Centroid se Distance ka Square ka sum 
- **Elbow Curve :** yeh Ek graph hota hai Jo No. of clusters aur WCSS ke beech Mein banta hai 
- ![[Pasted image 20260313191129.png]]
- **Elbow Point :** Woh point hota hai jaha yeh Graph Steep Hone lagta hai. Jis value se woh steep hone lagta hai Wohi Point humara Optimal No. of Clusters Hota hai 

**Note :** WCSS1(Wcss for Cluster1) > WCSS2(wcss2 for Cluster 2) > WCSS3(wcss for Cluster 3) Always True 
