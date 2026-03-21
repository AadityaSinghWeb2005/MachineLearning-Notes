****
### **1. Core Hyperparameters**

AdaBoost is a relatively simple algorithm compared to others like XGBoost, with four primary hyperparameters to tune:

- **`base_estimator`**:
    
    - This is the model from which the boosted ensemble is built.
        
    - By default, it is a **Decision Tree Classifier** with `max_depth=1` (also known as a Decision Stump) [[01:27](http://www.youtube.com/watch?v=JmXnztjULnQ&t=87)].
        
    - While you can use other models like Logistic Regression or SVM, Decision Trees are used 99.9% of the time in practice [[02:04](http://www.youtube.com/watch?v=JmXnztjULnQ&t=124)].
        
- **`n_estimators`**:
    
    - The maximum number of base models to train.
        
    - If a "perfect fit" is found early, the learning procedure may stop before reaching this number [[02:24](http://www.youtube.com/watch?v=JmXnztjULnQ&t=144)].
        
- **`learning_rate`**:
    
    - Controls the contribution of each classifier.
        
    - There is a significant trade-off between `learning_rate` and `n_estimators` [[02:58](http://www.youtube.com/watch?v=JmXnztjULnQ&t=178)].
        
- **`algorithm`**:
    
    - Options are **SAMME** and **SAMME.R**.
        
    - **SAMME.R** is the default because it typically converges faster and achieves lower test error with fewer iterations [[03:23](http://www.youtube.com/watch?v=JmXnztjULnQ&t=203)].
        

### **2. Impact of Hyperparameters on Model Performance**

The video demonstrates how changing these values affects the decision boundary:

- **Low `n_estimators`**: Leads to **Underfitting**. A single estimator (`n=1`) creates a very simplistic, straight-line decision boundary [[04:49](http://www.youtube.com/watch?v=JmXnztjULnQ&t=289)].
    
- **High `n_estimators`**: Leads to **Overfitting**. With 500 or 1500 estimators, the model creates tiny, complex regions to capture every data point, which reduces generalization [[05:24](http://www.youtube.com/watch?v=JmXnztjULnQ&t=324)].
    
- **Learning Rate & Shrinkage**:
    
    - Lowering the learning rate (e.g., to 0.1) reduces the "amplitude" of weight updates [[07:32](http://www.youtube.com/watch?v=JmXnztjULnQ&t=452)].
        
    - This slows down the learning process, which is a powerful way to **reduce overfitting** even when using a high number of estimators [[08:51](http://www.youtube.com/watch?v=JmXnztjULnQ&t=531)].
        

### **3. Hyperparameter Tuning with GridSearchCV**

To find the optimal balance, the video suggests using `GridSearchCV`. In the practical example shown:

- The default model accuracy was **78%** [[04:13](http://www.youtube.com/watch?v=JmXnztjULnQ&t=253)].
    
- After running a grid search (tuning `n_estimators`, `learning_rate`, and `algorithm`), the accuracy improved to **83%** [[10:33](http://www.youtube.com/watch?v=JmXnztjULnQ&t=633)].
    
- **Optimal Settings found in the example:** `n_estimators=500`, `learning_rate=0.1`, and `algorithm='SAMME.R'` [[10:48](http://www.youtube.com/watch?v=JmXnztjULnQ&t=648)].
    

**Summary Recommendation:** To get the true power out of AdaBoost, focus your tuning efforts on the relationship between **`n_estimators`** and **`learning_rate`** [[09:47](http://www.youtube.com/watch?v=JmXnztjULnQ&t=587)]. 