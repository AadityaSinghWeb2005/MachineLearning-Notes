
**What is Random Forest and Its Intuition  ?**
Random Forest basically Collection hai Multiple Decision Trees ka 
Yeh ek bagging Technique hai
Iska Naam Random Forest Word Kyu Pada ? Forest Mtlb hum multiple Decision trees ko Train karte hai 
Random word aarha hai ki Yeh Algorithm Bagging Algorithm hai Jo Do process ka mixture hai Bootstrap Aggregration Bootstrap means Strapping (means Random Sampling of Data) and Aggregration is the process of selecting the Output 
Yeh ek baggin Technique ka Speciliazation hai Jisme Hum Base Model Mein decision tree lete hai 

How it works ? hUm sabhi base models mein decision Tree lete hai Ek dataset uthat the hai 1000 Rows ka Iss Dataset ko Row sampling Yah Column sampling ki help se Random Sub datasets bana dete hai Aur yeh random Subdataset ko Base Models (decision tree) ko assign Karte hai 
PHir woh Us data pe train hota hai Iss process ko bootstraping kehte hai 
Uske Jab sab Decision tree Yah base Model ka prediction aata hai toh Hum Aggregration Process lagate hai Jisme agar Problem classification hai toh Majority Voting ka Conept use karte hai jis class ki majority jada hai woh Final Output banta hai 
Agar Regression Problem hai toh Hum saare prediction ka Mean leelte hai Usse Final Output maan lete hai 