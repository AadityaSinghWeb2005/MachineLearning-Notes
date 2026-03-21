
### **1. Random Forest Specific Parameters [[01:18](http://www.youtube.com/watch?v=WOFVY_wQ9wU&t=78)]**

Yeh parameters seedhe ensemble (poore forest) ko control karte hain:

- **n_estimators:** Yeh batata hai ki aapke forest mein kitne **Decision Trees** honge. Default value 100 hoti hai. Trees badhane se accuracy badhti hai aur overfitting kam hoti hai, lekin training time bhi badh jata hai [[02:42](http://www.youtube.com/watch?v=WOFVY_wQ9wU&t=162)].
    
- **max_features:** Best split dhoondte waqt kitne features (columns) ko consider karna hai.
    
    - _Auto/Sqrt:_ Total features ka square root.
        
    - _Log2:_ Log base 2 of total features.
        
    - _None:_ Saare features use honge (Bagging jaisa).
        
- **bootstrap:** Default 'True' hota hai. Yeh batata hai ki samples ko 'with replacement' (ek hi row baar-baar aa sakti hai) lena hai ya nahi [[04:33](http://www.youtube.com/watch?v=WOFVY_wQ9wU&t=273)].
    
- **max_samples:** Agar bootstrap True hai, toh har ek Decision Tree ko training ke liye kitne rows dene hain. Prof. ke according **50% to 75%** range best result deti hai [[07:52](http://www.youtube.com/watch?v=WOFVY_wQ9wU&t=472)].
    

### **2. Decision Tree Parameters [[10:15](http://www.youtube.com/watch?v=WOFVY_wQ9wU&t=615)]**

Yeh woh parameters hain jo forest ke andar ke individual trees ko train karte hain:

- **criterion:** Split karne ka tarika (Classification ke liye: _Gini_ ya _Entropy_; Regression ke liye: _MSE_ ya _MAE_).
    
- **max_depth:** Ek tree kitna gehra (deep) ja sakta hai. Zyada depth se overfitting ho sakti hai.
    
- **min_samples_split:** Ek node ko split karne ke liye kam se kam kitne samples hone chahiye.
    
- **min_samples_leaf:** Leaf node (akhiri node) par kam se kam kitne samples hone chahiye.
    

### **3. General & Computational Parameters [[12:17](http://www.youtube.com/watch?v=WOFVY_wQ9wU&t=737)]**

- **n_jobs:** Parallel processing ke liye. `-1` ka matlab hai saare CPU cores use honge, jisse training fast ho jayegi [[12:30](http://www.youtube.com/watch?v=WOFVY_wQ9wU&t=750)].
    
- **random_state:** Result ko consistent rakhne ke liye taaki har baar same output aaye.
    
- **class_weight:** Agar data imbalance hai (ek class ke samples kam hain), toh aap classes ko alag weight de sakte hain [[13:16](http://www.youtube.com/watch?v=WOFVY_wQ9wU&t=796)].
    

### **Key Takeaway 

Random Forest Classifier aur Regressor ke parameters lagbhag same hain, bas **criterion** badal jata hai. Hyper-parameter tuning karne se model ki accuracy kafi improve ho sakti hai.