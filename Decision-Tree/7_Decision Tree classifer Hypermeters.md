

---

## **Decision Tree Hyperparameters: Detailed Notes**

Decision Tree ek **Greedy Algorithm** hai jo training data ko "perfectly" fit karne ki koshish karta hai, jisse **Overfitting** hoti hai. In hyperparameters ka main kaam is overfitting ko rokna (Pruning) hota hai.

---

### **1. Criterion (Gini vs Entropy)**

Ye decide karta hai ki "best split" kaise choose kiya jaye.

- **Gini Impurity (Default):** Ye thoda fast hota hai calculate karne mein[[4_Gini Impurity]].
    
- **Entropy:** Ye Information Gain use karta hai. Dono mein results ka bahut zyada farak nahi aata, par kabhi-kabhi Entropy thode better results de sakti hai[[2_Entropy]].
    

---

### **2. Max Depth (Sabse Important)**

Ye tree ki total lambai (levels) ko control karta hai.

- **High Depth:** Tree bahut deep jayega, har point ko capture karega $\rightarrow$ **Overfitting**.
    
- **Low Depth:** Tree bahut chota rahega, patterns miss kar dega $\rightarrow$ **Underfitting**.
    
- **Solution:** Iski ek optimum value dhundni padti hai (e.g., 3 se 10 ke beech).
    

---

### **3. Min Samples Split**

Kisi node ko tabhi split kiya jayega jab usme **minimum** itne samples (rows) honge.

- **Example:** Agar `min_samples_split = 50` hai aur kisi node mein sirf 40 points bache hain, toh algorithm use aage split nahi karega, bhale hi wo node pure na ho.
    
- **Impact:** Iski value badhane se overfitting kam hoti hai kyunki tree "early" ruk jata hai.
    

---

### **4. Min Samples Leaf**

Ek **Leaf Node** (aakhri node) banne ke liye usme minimum kitne points hone chahiye.

- **Logic:** Agar kisi split ke baad leaf mein sirf 1-2 points bach rahe hain, toh wo split noise ho sakta hai.
    
- **Impact:** Iski value badhane se tree "smooth" banta hai aur ajeeb se outliers ko capture nahi karta.
    

---

### **5. Max Features**

Har split ke waqt algorithm saare columns ko check karne ke bajaye sirf **kuch random columns** ko hi consider karta hai.

- **Kyun?:** Taaki tree har baar best column par hi depend na kare.
    
- **Impact:** Ye variance ko kam karta hai aur overfitting rokne mein help karta hai (Random Forest mein ye bahut kaam aata hai).
    

---

### **6. Max Leaf Nodes**

Ye total number of leaf nodes par limit laga deta hai.

- Agar aapne `max_leaf_nodes = 5` set kiya, toh poore tree mein 5 se zyada terminal nodes nahi honge, chahe depth kitni bhi ho.
    

---

### **7. Min Impurity Decrease**

Ek node tabhi split hoga jab split karne se impurity (Gini/Entropy) mein **itni minimum kami** aaye.

- Agar split karne se sirf 0.0001 ka fayda ho raha hai, toh algorithm split nahi marega.
    

---

### **Summary Table for Tuning**

|**Parameter**|**To Reduce Overfitting**|**To Reduce Underfitting**|
|---|---|---|
|**Max Depth**|Decrease it|Increase it|
|**Min Samples Split**|Increase it|Decrease it|
|**Min Samples Leaf**|Increase it|Decrease it|
|**Max Features**|Decrease it|Increase it|
|**Max Leaf Nodes**|Decrease it|Increase it|

---

