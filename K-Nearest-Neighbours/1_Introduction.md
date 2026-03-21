****
**Introduction**

- Maanlo humare paas ek dataset hai Classification wala Usme Graph mein 2 Clusters ban rhe hai Yes or No 
- Maan lo ek query aayi aur in clusters ke beech mein kahi hai Toh woh Jis cluster mein padegi wohi Point ka classifcation decide hoga agar Yes clusster mein gyi toh Yes and if No cluster Gyi toh NO 
- Ab KNN hota hai K- nearest Neighbours Mtlb sabse ek K ki value decide karlo Ex. K = 3 ab uss point ko uthao aur saare points Jo bhi graph mein availabe hai Unse distance nikal Elucidean Distance In distances ko acsending order mein Set karlo aur First Three distances Wale Point mein Se Majority voting ki help se final prediction Decide karlo 
- KNN is Applicable to N-dimensional Dataset 

**Note :** Jab bhi KNN ke saath kam kar rhe ho tab dataset mein sabhi data ko Same scale pe le aao 

****
**How to Select Ideal Value of K ?**

- There are two approaches : 1. heuristic Approach    2. Experimental
- **Heuristic Approach :** isme bas jite bhi no. of row hote hai Uska AAp sqrt le lete hai but iss sqrt ka ANswer even nhi aana chaiye warna Majority voting ke Conflict ka reason ban skta hai 
- **Experimentation**
	- **Cross-Validation :** isme aap ek dataset ko do parts mein tod lete ho Training and Testing data ab aap Different KNN models banate ho with different K value everytime and aap in models ko train karte ho with the help of training data and aap test karte ho with the help of testing data. aur jiski bhi accuracy high aati hai aap us model ko select karte ho 


****
**Decision Surface**

- yeh ek classification tool hai jo kayi Decision relation maachine learning algorithms mein kaam aata hai jaise Logistic regression , Decision Tree , SVM etc. 
- Decision Surface yah Decision boundary Mainly Humare data ko Unki classification outputs ke basis pe Divide kardeta hai 
- In simple words yeh coordinate system ko Kaat deta hai data ke pbase pe Ki iss jagah bhohot blue points hai toh yeh blue region and red points bhot hai Mtlb red region 

*****
**Overfitting and Underfitting in KNN**

- Overfitting K ki jab smallest value lelete hai us case mein hota hai Ex. K = 1 mtlb neighbour mein sirf 1Point ko dekh ke hum final Prediction denge 
- Underfitting K ki jab hum highest value lenge Highest mtlb Jite Number of Rows Yah number of points hia Jaise No. of rows = 200 and K = 200 that means its Underfitting kyunki Humne Pure data points ko hi Neighbour maan liya ab jis bhi points ka majority vote jada hai Prediction whoi hoga isliye underfitting ka case ban rha hai 

****
**Limitations of KNN**

- Not works on Large datasets because KNN is lazy machine learning Model mtlb yeh training ke time koi calculation nhi karta hai Yeh saare kaam prediction ke time pe hi karta hai toh dataset jita bada hoga uti prediction late hogi 
- It Does not work on High dimension likes Column = 500 because ite bade Dimensions  ke beech elcuidean distance ek accha distance parameter nhi hai 
- Scaling : agar features scaled nhi hai mtlb alag alag scale pe hai toh result alag aaskte hai 
- imbalanaced Data : agar data mein ek class ke points zada hai toh Prediction ka uspe Heavy dominance hoga 
