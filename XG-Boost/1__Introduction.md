****
**Introduction**

- Machine learning algorithms Kisi specific type ke data ke upar hi Operations perform kar skte hai 
- Jaise Linear Regression -> Linear data , Naive Bayes -> Textual Data 
- but kuch algo hai jo bohot powerful hai jaise RF , SVM , Gradient boosting but inmhe problem Overfitting ke aur scalability ki 
- Phir aaya 2014 mein XG-boost jo koi algorithm nhi ek library hai yeh library Gradient boosting algorithm pe bana hai 
- XG-Boost Combination hai ML(Gradient Boosting) + Software engineering Concepts ka 
- XG-Boost ke main Features : Performance , Speed , Flexibility 

****
**Flexibility**

- **Cross Platform :** Yeh kisbhi operating system mein chal skta hai 
- **Mutlilple Language Support :** kayi Algorithms sirf kuch hi Programming Languages mein kaam akrte hai Jaise python , R , matlab But XG-boost kai languages ko support karta hai Jaise JAVA , C , C++
- **Integration with Other libraries and Tools**
- **Support all kinds of Machine Learning Problems :** Regression problem , Classification problem , Anamoly Detection isme aapkoi bhi Loss function use karskte ho

*****
**Speed**

- XG-boost baki ke ml algos se fast hota on the bigger datasets In *6 Reasons ke karan*
- **Parallel Processing :** paralle Processing kam karta hai Models ke individual building mein mtlb Hum jaante hai ki boosting mein Model Sequentially Train hote hai Hum isme parallel processing nhi lagaenge Jab ek model ko individual banate hai Decision tree ki help se toh uss Decision tree ko banane mein hum parallel processing ka help lete hai. Kaise Hum jab decision tree banate hai toh Hum har feature ka spiliting criteria banate hai Aur usse har dusre feature ke spilliting criteria se match karte hai ek Final splitting criteria ke liye. Parallel processing bas har feature ka spilliting criteria ek saath find karta hai jisse time bohot kam lagta hai 
- **Optimized Data Structures :** Mtlb XG-Boost data ko kaise store karta hai Operation karne ke liye baaki algos mein row block bante hai data pe operations karne ke liye but XG-boost mein Columns blocks bante hai Jisse Parallel Processing bhi easy ho jati hai 
- **Cache Awareness :** XG-Boost Cache memory ka concept use karta hai to build decision tree faster 
- **Out of Core Computing :** Yeh concept bade datasets ke liye use hota hai Maanlo 12 GB ka dataset aagya aur aapke RAM sirf 8 GB ki hai toh Yeh concept Us Data ko 2GB ke parts mein tod ke Sequentially Train karvata hai XG-boost mein ek hyperparameter hota hai jisse ==tree method== kehte hai jiski value hist set karne par yeh concept activate ho jata hai Yeh **Cache Awareness** ko bhi use karti hai 
- **Distributed Computing :** Distributed computing hota hai Jo bi task mila hai Usse equal chunks mein divide karke Multiple Devices mein process karna parallel process in multiple devices ko node kehte hai Yeh kaam kaise karta hai XG-boost mein so Hum pehle dataset ko divide kardete hai Equal chunks mein Nodes ko ab har node decision tree banegi use data pe jo unko mila hai toh har Node Ek Spilliting criteria degi Ab hum aggregration ki process yeh decide karenge konsi Node ke spiliting criteria se Zada fayda mil rha hai aur use select kar lenge. Distributed computing us karne ke liye hume libraries import karni padti hai jaise Dask , kubernetes 
- **GPU Support :** Instead of CPU we use GPU by Using a hyperparameter Called tree_method : gpu_hist
- XG-boost ki full form hoti hai Extreme Gradient boosting kyunki inhone kuch zada extreme concepts ka use kar liye Isko banane ke liye 

****
**Performance**

- XG-boost Mein speed Software engineering ke concepts se Tez hui thi Lekin performance ML concepts se Acchi hui hai Uske 5 concepts hai ML ke Hum use karenge 
- **Regularized Learning Objective :** XG-boost Generally Saare Tarah ke Training data pe kaam karega kyunki usme Loss Function mein Regularized add hai Jo ki gradient boosting mein nhi tha Isliye XG-Boost Overfitting ka case acchi tarah handle kar pata hai 
- **Handling Missing Values :** by using sparsity aware split finding 
- **Sparsity Aware Split finding :** Sparasity Mtlb hota hai Data mein kitne zeroes hai Split finding hota hai Hum agar features mein koi Value Missing hai toh XG-boost jab decision Tree banata hai toh Us Nan value ko har node bhej ke one by one sab nodes ka gain nikalata hai jis bhi node mein sabse jada gain hota Wohi Humare naya Splitting point ban jata hai 
- **Efficient split finding(Weighted Quantile sketch + Approximate Tree Learning) :** Yeh data distribution ko study karke "Approximate Tree Learning" karta hai, jo speed aur accuracy dono balance karta hai
- **Tree Pruning :** Mtlb aap decision trees ki depth ko kam karte ho ya Tim karte hao complexity kam karne ke liye Yah overfitting kam karne ke liye XG-Boost Hyperparameters provide karta hai Jaise pre-pruning (jisme mein aap tree ko construction  ke saath hi prun karte hoa ) and Post pruning ( jisme Tree ko pura banne dete ho aur phir pruning karte ho data ke base pe) ek aur hyperparameter hota hai Gamma Jisme aap Yeh decide karte ho ki agli branch banegi yah nhi 
