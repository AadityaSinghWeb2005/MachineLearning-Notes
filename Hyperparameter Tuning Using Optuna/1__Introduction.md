****
**Why Learn Optuna ?**

- Humne Ab tak do methods apdhe hai Hyperparameter Tuning ke Grid Search CV aur random Search CV in domo hi kuch specific Problems thi jaise Grid Search CV Takes too much Computational power and takes too much time on bigger dataset with Mutiple Hyperparameters
- In random Search CV the problem is isme Ek chance ho skta hai ki yeh Correct wale parameters na Jo High Accuracy De 
- Optuna Yeh Dono Problems Ko Solve karta hai with the help bayesion Step 
- Bayesian Step kya karta hai ki woh aapke Hyperparameters mein Mathematical relationship dhoondhne ki yah establish karne ki koshish karta hai 
- yeh relationship Actually Graph mein Accuracy ke saath plot ki jaat hai toh bayesian Try karta hai find karne ka is graph ka Nature kaisa hai Taaki Woh iske Maximum Point tak pahunche 
- Maximum Point pe hi Maximum accuracy hai aur Uske Corrresponding hyperparameters ki value Hum pata lag jaati hai 
- ![[Pasted image 20260325200150.png]]
- Bayesian Search mein Pichle searches aur Accuracy help karti hai Hume Naye Searches Mein 
- So Basically Optuna ek Hyperparameter tuning Software hai Jo backend mein Bayesian Search ko use karta hai to find perfect hyperparameters 

****
**Key Terms In Optuna**

1. **Study :** FInding the best Hyperparameters for the Ml Algo Iss pure process ko Study kehte hai Optuna ki Language mein 

2. **Trial :** Ab Jab Hyperparameters ke combination ko data pe train kar rhe ho Toh uss Process ko Trial kehte hai Group of Trials Ko Study kehte hai 

3. **Trial Hyperparameter :** Woh Hyperparameters Jinka Combination aap Trial mein le rhe ho 

4. **Objective Function :** Yeh woh process Hai jisme Hum Hyperparameters mein Value as a input de rhe hai Aur hume Output Mein un input values ke Corresponding maximum Accuracy mil rhi hai. 

5. **Sampler :** Sampler Hume Help karta hai Jaane mein Hum konsa Hyperparameter ka Combination Next try karna chaiye with the help of Combination of Previous Hyperparameters which we try. Hum issme Ek sample use karte hai jisse kehte hai TPE(Tree structured Parzen Estimator)

****
**Different Type of Samplers**

- Multiple Samplers are available like There is sample which use random Search . THere is sampler which use Grid Search 

****
**Features**

- Visualization 
- **Define by Run :** Iski Help se Aap Dynamic Search Space Generate kar skte ho Mtlb Yeh hume help karta hai Best Algorithm Konsa lagega Jo maximum results dega aur Uske bhi Best Hyperparameters Yeh hum Optuna ki help se karte hai 
- **Distributed Computing :** Multiple devices pe run honge 