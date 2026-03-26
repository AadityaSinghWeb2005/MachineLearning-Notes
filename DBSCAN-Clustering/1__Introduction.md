****
**Why we need DBSCAN ?**

- Kmeans mein Flaws the woh the : YOu have to specify the no. of clusters, Sensitive to Outliers, Kmeans Centroid Mechanism pe kaam karta hai Jiski wjah se Woh sirf SPherical data pe hi accha kam karta hai Non-spherical data pe kaam nhi karta 
- **What is DBSCAN ?**  : It follows the density based clustering Principle jisme aap clustering karte ho on the base of Density. Mtlb density based algorithms Clusters waha banaenge jaha points ki density jada hogi 
- **DBSCAN :** Density based Spatial Clustering of Application and Noise 
- **Min Points & Epsilion :** Yeh do Hyperparameters hume help karte hai pata karne mein Ki Points mein density hai ki nhi Eg. Min-Points : 3 , Epsilion : 1 Unit. Epsilion ka mtlb hai radius Hum koi bhi random point padkdenge aur ute epsilion ka circle banenge uske around Uss circle mein jite bhi points gire hai agar woh Min-points se zada hai yah equal hai toh Woh dense mana jaenga aur Agar Kam Hue min points se toh Woh Spatial Space mana jaenga 

****
**Types of Points in DBSCAN**

1. **Core Point :** Kisi datapoint ke epsilion neighbor hood mein agar Aapke min points se Zada yah barabar points hai toh aap use Core point kahonge 
2. **Border Point :** Woh point jiske Epsilion Neighbour hood mein Min points se Kam Points ho but Usme ek Core point zaroor ho Use Hum border point kehte hai 
3. **Noise :** Woh points jinke Epsilion Neighbour Hood mein Min Points se kam points ho te hai and Koi core point bhi nhi hota unhe Noise Point kehte hai 
4. **Diagram :**![[Pasted image 20260325092636.png]]
5. **Diagram-2 :**![[Pasted image 20260325092655.png]]

****
**Density Connected Points :**

- Do points Agar Density Connected points hai toh Ek hi Cluster mein aaenge. Ab Density Connected ka criteria kya hai ?
- Do point A and B ek dusre se connected hone chaiye through Core Points in Core Points ki Ek dusre se Distance <= Epsilion 
- Agar Koi Core Point Ki distance > Epsiliion se yah koi point core na hoke border yah Noise nikla toh creiteria match nhi hoga aur Do point ek cluster mein nhi aaenge Woh density connected nhi hai 

****
**DBSCAN Algorithm**

**Step-1 :** sabse Epsilion and Min points decide karlo , sabse Pehle har point ko lable kardo woh konse point hai Core point hai , yah noise point hai , Border point hai 

**Step-2 :** Sabse pehle Saare Core points ko pakdo jo cluster mein nhi hai 
	**Step- 2a :** Un sabko Individually Cluster bana lo 
	**Step-3a :** In sabhi Points ko Dekho Kya Yeh density connected points hai Agar haa toh inhe ek cluster mein le aao

**Step-3 :** Jo bhi unclustered Border points the Unko unke Closer Cluster Core Point mein daal denge 

**Step-4 :** Noise Points Ko aise hi chod do 

****
**Limitations**

1. Sensitive to Hyperparameters 
2. Difficulty with varying density Clusters : mtlb kuch clusters ki agar alag alg denisty hogi toh epsilion value fail ho jaengi 
3. Does not predict : Yeh prediction nhi de skta 