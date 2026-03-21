****
**Explanation of How Adaboost Works Internally**
Sabse phele hum har row ko equal Weights assign Kardenge ex : 5 Rows hai toh 1/5 weight sabko assign hoga 
N rows ko 1/N Weight assign hoga 
Iske Baad Hum stages Mein kam karenge 
 ****
 **Stage-1 : Training the First Model(decision Stump)**
 Data pe Ek decision Stump implement karo (Decision Tree with Max depth = 1) isme Woh stump choose hota hai jiski Information Gain zada hai 
 ****
 **Stage-2 : Calculating Error and Alpha**
 Error : Jo rows Galat Classify hue unka weight ka sum kiya jata hai 
 Alpha : Yeh batata hai  ke FInal Results Mein kis model ka importance jada hoga Wit the help of formula : $$\alpha = \frac{1}{2} \ln\left(\frac{1 - \epsilon}{\epsilon}\right)$$
 ****
 **Stage 3 : Updating Weights**
 Ab hum Weights ko update karenge Dono Missclassified Points ke weight ko aur Classified Points Ke weight ko 
 Incorrectly Classified Points : Inka Weight bada diya jata hai taaki Agla base model inpe dhyan de aur inhe Classify kare ($W_{new} = W_{old} \times e^\alpha$).
 Correctly CLassified Points : inka weight kam kiya jata hai ($W_{new} = W_{old} \times e^{-\alpha}$)
 Iske Sabhi Weights (updated) ko normalize kiya jata hai taaki sum 1 aaye Kyunki jab humne Stage 0 mein Eights assign kare the tab unka sum 1 tha 
 **Note :** Normalize humne inhe Inke total Sum Se divide karadiya Mtlb har Updated weight ke column ke row unke Column ke total sum se divide kardiya Aur yeh Ban gye humare naye Normalized Weight 
****
**Stage-4 :Up-scaling (Creating a New Dataset)**
Ek range banayi jati hai aur random numers generate karke un rows ko bar bar uthaya jata hai jinka weight zada hai 
isse missclassified points naye dataset mein zyada baar aate hai aur agle model unhe sahi karne ki koshish karta hai 

****
**Stage-5 : Final Prediction**
Saare trained models ko unke weights ke saath combine kiya jaata hai 
Final Output un sabka weighted sum hota hai 
$$F(x) = \text{sign}\left(\sum \alpha_i h_i(x)\right)$$