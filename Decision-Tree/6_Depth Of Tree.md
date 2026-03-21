
Depth ka mtlb hota hai Kisi specific Node se lekar Root tak Distance 
Depth of tree Hi Mainly Karan hota hai Overfitting aur Underfitting ka 

**Overfitting Due to Depth :** jab Hum Data se decision Tree bana rhe hote hai toh usse split karte rhte hai Jab tak Hum saare LeafNodes tak nhi pahuch jate IN leaf nodes mein woh rows hote hai Model Unke Basis pe hi decision leta Hai 
So Mainly Model 2 Points Pe ratta mar rha hai 
Agar woh do points Noise Data / Outliers Hue toh Model ki performance Kharab ho skti hai 
Sklearn Mein ek parameter hota hai `max_depth` jiski by default value None hoti hai Iska Matlb hai Decision tree End Nodes tak jaenga Har Leaf Tak Jaenga 

**Geometeric Intution of Overfitting In Decision Tree :** 
![[Pasted image 20260228105801.png]]
Overfitting In Decision Tree ka simple Mtlb hai Algorithm jab tak nhi rukta jab tak woh har data ko sahi category mein na daal de 
Jaisa aap Diagram mein dekh skte hai Isne Kuch Jada Hi Classes banadi Because of Training Data 
In classes Ke karan Data accha Perform karega On training data 
But fail ho jaenga test data pe Kyunki Maan lo Data mein kuch Outliers aaye toh Model unko Class mein add kardega aur Outliers bhi Add ho jaenge Aapke Model mein Jisse Model ki performance kharab hogi 
In ka Main Karan Sklearn ka parameter `max_depth` hota hai jiski Default value NOne hoti hai Jiski Wajah se tree Infinity tak grow ho jata hai 

**Underfitting and Its Geometeric Intution :**![[Pasted image 20260228110619.png]]
Underfitting ke case mein Hum `max_depth =1` rkh rhe hai Iska mtlb hai data sirf ek baar split hoga so isse kya hoga ki jab Koi naya point aaenga add hone ke liye toh uske pass sirf 2 hi option honge 
so Less knowledge Leads to Underfitting 

**Note :** Underfitting aur overfitting Ko control max_depth ki value se kiya ja skta hai Agar Hum max__depth ki value ek optimal value le jo na Underfitting kare na hi Overfitting Kare 
