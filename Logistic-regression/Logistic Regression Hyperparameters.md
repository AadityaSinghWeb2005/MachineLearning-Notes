

**1. Penalty (Regularization Type) [[01:07](http://www.youtube.com/watch?v=ay_OcblJasE&t=67)]**

- Model mein overfitting rokne ke liye kaunsa regularization lagana hai, yeh decide karta hai.
    
- **Options:** `l1` (Lasso), `l2` (Ridge), `elasticnet`, ya `none`.
    
- Default mein yeh `l2` par set hota hai. Agar aap `none` set karte hain, toh normal Logistic Regression chalega bina kisi regularization ke.
    

**2. Dual [[01:54](http://www.youtube.com/watch?v=ay_OcblJasE&t=114)]**

- Yeh thoda technical parameter hai. Generally isko **False** hi rakha jata hai.
    
- Iska use (True) tabhi kiya jata hai jab aapke dataset mein rows ki ginti columns (features) se kam ho (Dual formulation).

**3. Tolerance (tol) [[02:26](http://www.youtube.com/watch?v=ay_OcblJasE&t=146)]**

- Yeh Gradient Descent algorithm ka stopping criteria hai.
    
- Agar value bohot choti (zero ke paas) hogi, toh iterations zyada lagengi. Agar value badi kar di, toh Gradient Descent jaldi ruk jayega aur shayad global minima tak na pahunche.

**4. C (Inverse of Regularization Strength) ⭐ [[02:51](http://www.youtube.com/watch?v=ay_OcblJasE&t=171)]**

- Yeh sabse **important** hyperparameter hai agar aap regularization use kar rahe hain.
    
- Yeh $\lambda$ (Lambda) ka ulta (inverse) hota hai ($C = 1/\lambda$).
    
- **Rule:** `C` ki value jitni **choti** hogi (zero ke kareeb), regularization utna hi **strong** hoga. `C` ki value jitni **badi** hogi, regularization utna hi **weak** hoga.
    

**5. Fit Intercept [[03:30](http://www.youtube.com/watch?v=ay_OcblJasE&t=210)]**

- Kya aapko apne equation mein $W_0$ (bias/intercept term) chahiye ya nahi? Default value **True** hoti hai aur hum isey change nahi karte.
    

**6. Class Weight [[03:36](http://www.youtube.com/watch?v=ay_OcblJasE&t=216)]**

- Agar aapka dataset **imbalanced** hai (jaise 90% logo ko cancer nahi hai, aur 10% ko hai), toh default model bias ho jayega.
    
- Aise case mein isey `balanced` par set karte hain taaki minority class ko zyada weight/importance mile. Normal data ke liye ise mat chediye.
    

**7. Solver (Optimization Technique) ⭐ [[04:21](http://www.youtube.com/watch?v=ay_OcblJasE&t=261)]**

- Gradient Descent ke alag-alag variations banaye gaye hain optimization ke liye.
    
- **Options:** `newton-cg`, `lbfgs`, `liblinear`, `sag`, `saga`.
    
- **Important Rules:**
    
    - Agar `elasticnet` use karna hai, toh sirf `saga` solver kaam karega [[05:14](http://www.youtube.com/watch?v=ay_OcblJasE&t=314)].
        
    - Agar `multinomial` (Softmax) use karna hai, toh `liblinear` kaam nahi karega [[04:55](http://www.youtube.com/watch?v=ay_OcblJasE&t=295)].
        
    - Badi datasets ke liye alag solvers better perform karte hain (Scikit-Learn documentation ka chart dekhna padta hai).
        

**8. Random State [[06:14](http://www.youtube.com/watch?v=ay_OcblJasE&t=374)]**

- Kuch solvers (`sag`, `saga`, `liblinear`) data ko shuffle karte hain. Agar aap chahte hain ki har baar result same aaye, toh isme koi integer value (jaise 42) de sakte hain.
    

**9. Max Iterations (max_iter) [[06:25](http://www.youtube.com/watch?v=ay_OcblJasE&t=385)]**

- Gradient Descent ko converge hone ke liye kitne epochs (loops) chalane hain, woh yahan define hota hai.
    

**10. Multi_class [[06:33](http://www.youtube.com/watch?v=ay_OcblJasE&t=393)]**

- Jab target mein 2 se zyada classes hon:
    
    - `ovr` (One-vs-Rest): Har class ke liye alag Logistic Regression model banata hai.
        
    - `multinomial`: Softmax Regression use karta hai ek single loss function ke sath.
        
    - **Tip:** Isey `auto` par chhod dena best hota hai, library apne aap decide kar leti hai.
        

**11. Verbose [[07:42](http://www.youtube.com/watch?v=ay_OcblJasE&t=462)]**

- Training ke intermediate results (background mein kya chal raha hai) dekhne ke liye iski value 1 set kar sakte hain.
    

**12. Warm Start [[07:50](http://www.youtube.com/watch?v=ay_OcblJasE&t=470)]**

- Agar ise **True** karte hain, toh agar aap dobara `.fit()` call karenge, toh model scratch se train hone ki jagah purane weights se aage training resume karega.
    

**13. N_jobs [[08:07](http://www.youtube.com/watch?v=ay_OcblJasE&t=487)]**

- Apne computer ke CPU cores ko utilize karne ke liye.
    
- Agar `ovr` approach chal rahi hai jahan multiple models train ho rahe hain, toh isey `-1` set kar dein. Isse saare CPU cores parallel process karenge aur training fast hogi.
    

**14. L1 Ratio [[08:38](http://www.youtube.com/watch?v=ay_OcblJasE&t=518)]**

- Yeh sirf tab use hota hai jab apne penalty mein `elasticnet` select kiya ho.
    
- Value 0 = L2 (Ridge) ki tarah behave karega.
    
- Value 1 = L1 (Lasso) ki tarah behave karega.
    
- Value 0.5 = L1 aur L2 ka 50-50 mix.