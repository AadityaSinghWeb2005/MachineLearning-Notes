
Hum Categorical Data Ki tarah Numerical column (jisme bohot saare Numbers hote hai ) Split karna bohot muskhil 
Solution : Binary Splits Jisme hum Condition ke base pe jaise value > ke base pe Do dataset bana dete hai (True / false)
Aur phir yeh process Har dataset ke liye Repeat karte hai 
then Hum pehle child dataset keliye Entropy calculate karte hai Phir hum Parent dataset ki Entropy Calculate karke Information Gain Nikalte hai 
Jis Column ka Maximum Information Gain hota hai Usse Hum Root node banate hai Aur yeh process iteratively Karte jaate hai 

**TIme Complexity :** Yeh bohot slow aur computationally Heavy hai Lekin yeh hume sirf ek hi baar hi karna pdta hai Training Ke time To uski Complexity Time High hoti hai 
Lekin Testing Ke time Iss process ko karne ki jaroorat nhi hai Isliye Testing Mein Time complexity Kam hoti hai O(log n) 

**Better Approach :** Agar aapke pass ek aisa data hai jisme Multiple Numerical columns hai toh regression Algos Ka use lijiye decision trees ko maaf kare 