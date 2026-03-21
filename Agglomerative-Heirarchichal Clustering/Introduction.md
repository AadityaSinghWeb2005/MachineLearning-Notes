****
**Problem in K-Means Clustering**

- K-means Distance Pe kaam karta hai Yeh Un datasets pe accha kam karta hai jaha Clusters Spherical yah circular Shape Mein HO 
- K-mean kuch datasets ke case Mein Hug deta hai Ex. ![[Pasted image 20260318113001.png]]
- jaise ki dekh skte yeh mix kar rha hai Inko differentiate nhi kar pa rha 
- Isko Solve Karne ke liye Kayi clustering methods ka use karenge Jaise : 1. Heirarchical Clustering 2. Denstiy based Clustering (ek algo used karta hai DBSCAN karke )

****
**Heirarchichal Clustering**

- **Heirarchichal Clustering :** 1. Agglomerative Clustering     2. Divisive Clustering 
- **Agglomerative Clustering :** Maan lete humare pas jite bhi points hai data mein Unko Clusters maan lete hai Individually Har point khud Mein ek cluster Hai Jaise 6 Points hai toh 6 clusters honge Phir Hum jo close Clusters Honge Unko Merge Krte jaenge Aisa karte karte hum ek bade mega Clusters mein chale jaenge. Aur jab hum clusters ko merge kar rhe hote hai toh hum Unhe Note karte rehna chaiye taki Hum heirarchy Form karske Ex. ![[Pasted image 20260318114142.png]]
- iss basde Diagram ko Dentogram bolte hai Ab humare Ek single mega Cluster aagya Ab agar maan lo Hum 2 Clusters chaiye toh bas C5 ko tod denge aur humare Do clusters aajaenge C4 and C2 aur agar 3 clusters chaiye toh c4 ko tod denge toh humare teen clusters aajaenge C2 , C3 , C1. Toh yeh hai Geometeric intuition Agglomerative heirarchial Clustering ka 
- **Divisive Clustering :** yeh bas Exact opposite sense mein kaam karti hai Agglo ke Isme Hum ek bada mega cluster assume karlete hai aur Phir usse eek ek akr todte hai aur clusters form karte hai 

****
**Algorithm**

- **Step-1 : Intialize the Proximity Matrix**
	- Hume ek proximity matrix banan hota hai Har point ki Help se 
	- Jisme Points ki Distance ko fill kiya jata hai Kuch iss tarah 
	- ![[Pasted image 20260318121927.png]]
- **Step-2 : Make Each Point a Cluster**
- **Step-3 : Inside a Loop**
	- a. Merge the 2 closest Clusters 
	- b. Update the proximity matrix 
	- Yeh kuch iss tarah dikhega jab hum clusters ko merge kardenge ![[Pasted image 20260318122143.png]]
	- C1 is the cluster by merging by P3 and  P4
- **Step-4 : Until Only One cluster Left**

**Note :** Clusters ke beech ki distance calculate karna Mushkil hota hai Isliye Hum methods ka use karte hai in methods ke type hote hai Woh hum discuss karenge 

****
**Types of Agglomertaive Clustering**

1. **Single Link :** yeh CLustering method hume Distance Calculate karne mein help karta hai between two Clusters. by Hum har Clusters ke point se Dusre Clusters ke point ki distance nikalenge Jin bhi points ki distance sabse kam hogi wohi Distance ko hum clusters ki beech ki distance maan lenge. **Limitation :** Yeh Method Outliers ki wajah se effect hota hai aur kharab Performance deta hai.
2. **Complete Link(Max) :** Yeh bhi single link ki tarah hi hai bas isme Hum Maximum Distance b/w points ko final Distance maan te hai Clusters ke beech ki. Outliers ka ispe koi effect nhi padta hai 
3. **Group Average :** Isme sabse Pehle aap har point ki cluster1 mein se Point of Cluster 2 se distance nikal sum kardete ho aur total no. of points (Cluster1 + cluster2) se divide karadete ho aur jo final distance aati hai wohi Clusters ke beech ki distance maani jaati hai 
4. **Ward :** Isme hum distance nikalne ke liye ek formula ka use karte hai ![[Pasted image 20260318123421.png]] sabse pehle hum ek centroid banate hai Clusters ke beech aur Har point ki distance nikalte hai iss centroid se phir Cluster mein Variance Nikalte hai (mtlb har point ki mean se duri yah distance) aur unka sum kardete hai phir centroid se points ka distance aur Clusters mein points ka varaince ka addition kardete hai as Per formula(**Sklearn mein Default Method hai **) 

****
**How to find the ideal number of clusters**

- Jaise Hum kmean mein hum elbow method ka use karte hai iss Algo mein Dendogram ka use karte hai ideal number nikalne ke liye 
- ![[Pasted image 20260318124112.png]]
- Dendogram mein sabse lambi vertical line dekhni hoti hai jisse koi horizontal line na kaat rhi ho waha se ek horizontal line kheeche aur Jite vertical cut rhi hai ute hi aapki ideal number of clusters honge 

****
**Hyperparameters**

- **n_clusters :** No. of clusters 
- **affinity :** Konsa distance metric use karonge Ex. Elucidiean 
- **Linkage :** TYpes of Agglomertive CLustering 
- **Distanc_threshold :** ek distance value de skte ho aap do clusters ke beech mein aap agar usse threshold distance se kam distance hui toh Cluster banenge Hi nhi 

****
**Benefits and Limitations**

- **benefits :** 
	- Widely Applicable
	- Dendogram ki help se aap ko puri heirarchy ka  info rehte hai mtlb konsa point kiske pass  hai Jo ki k means mein nhi hota 
- **Limitations**
	- bade dataset(data(10,0000 , 10,00000) pe yeh kaam nhi karta kyunki unme Proximity matrix Bohot bada banega jo jada memory khaenga 