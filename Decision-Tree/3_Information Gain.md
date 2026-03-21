

Information Gain ek metric hota hai Jo Split ki "QUality " Ko measure karne mein help karta hai 
In simple Word : Jab hum data ko kisi column ke basis pe split karte hai toh humarei Entropy Kitni kam hui Iss Decrease ko hi Hum **Information Gain** bolte hai 
**Note :** Algorithm humesha uss column ko chunta hai data split karne ke liye jiska information gain Highest Hota hai Kyunki Woh data ko sabse best tarike se "Pure" classes mein divide karta hai 

**Mathematical Formula :**

information Gain = Entropy(Parent) - Weighted Average of Entropy(Children)

**Step by Step Calculation(Algorithm) :**

Maanlo Humare Pass play tennis ka dataset aur hume check karna hai Outlook column ka split sahi rahega yah Nhi 
**Step 1** :  **Calculate Parent Entropy**  : Mtlb pure table yah dataset ki entropy nikali jaati hai Jaise iss dataset mein 14 rows hai jisme 9 yes and 5 No hai toh entropy formula se Unki Entropy(parent) nikal lenge 

**Step 2:**  **Split the data(child nodes banao)** : ab Outlook ko teen data ke base pe tod do ( Sunny , Overcast , Rainy ) yeh teen naye dataset banajaenge 

**Step 3:** **Children ki entropy Calculate karo :** ab in teeno children ki Entropy alag alag calculate karo Eg. E(O) = 0 hogi 

**Step 4:** **Calculate Weighted Average of Children :** Weighted average nikalne ke liye Harchildren ki entropy se uska Size/weight se multiply Karado aur sabko add kardo milgya aapko weighted average Ex. ![[Pasted image 20260227110735.png]]

**Step 5:** **Put the values in the Information Gain Formula**



**How to Make The decision ?**
1. Algorithm in steps ko har column ke liye recursively repeat karta hai 
2. Phir sabhi columns ke information Gain values ko compare kiya jata hai 
3. Jis columna ka Information gain value highest hoti hai Wahi column Root Node Ya decision Node banta hai jaha se tree niklta hai 


**Recursive Nature :** 