****
**Why ROC Curve ?**

- ROC Curve Aap Binary Classification pe Lagate ho 
- **Threshold Selection :** Jab hum koi prediction nikalte hai Kisi classification problem se related Jo Bhi algorithm Prediction deta hai Woh Probability ke Roop mein Uss probability ko hum Class mein change karte hai Jiase agar prob 0.5 se zada hai toh Class -1 and if less than 0.5 then class -0 Ab yeh jo 0.5 hi threshold value hai yah threshold section hai 
- Ab yeh jo Threshold ki value 0.5 Kaafi problematic ho skti hai Kai cases jaise Email spam classifier toh aise cases mein hum threshold ki value 0.5 se zada lete hai jaise 0.75 , 0.90 
- Ab iss Threshold value Select karne mein Hum ROC Curve help karta hai 
- **True Positive Rate :** iss Rate ka intuition hai ki Jite bhi positive cases Unme se Kito Algorithm actually Positive bata paya Iska Formula : TPR = TP / TP + FN. Aap true positive Rate ko maximize karna chahonge 
- **False Positive Rate :** Yeh rate hume batata hai Ki Jite bhi negative Case Unem se kito ko algorithm Positive Bata rha hai Hai Isski help se Hume Cost pata chalta hai Iska formula hota hai : FPR = FP / FP + TN. Iske Zero hona accha rahega Yeh tab Hoga Jab FN = 0 
- Humare Liye Sabse Ideal case hoga Jisme Confusion Matrix mein FN = 0 and FP = 0 rahe 
- in dono cases mein Hi Hume Truse Positive Rate and False Positive Rate Maximum milegi 
- **ROC Curve :** Receiver Operator Characteristic Full form of ROC 
	- TPR aur FPR ke beech ke Graph ko hi ROC curve kehte hai 
	- Jisme hum Threshold ki alag alag values pe TPR aur FPR ka graph plot karke dekhenge Konsa Point TPR axis ke close hai Kyunki Humara Ideal case hai TPR =1 and FPR = 0
	- **Shape of ROC Curve :** Threshold ki value kam lene se TPR And FPR dono ki value increase hongi 
	- Agar Threshold ki value kam longe toh FPR and TPR dono ki value Kam hogi Decrease Hongi 
	- How ROC curve Actually Look Likes : ![[Pasted image 20260326204333.png]]
- **AUC :** Ek aur Cheeze hoti hai AuC karke Which is Area under the Curve yeh aapko help kart hai Alag Alag Model ko compare karne mein ki Kon threshold wise badhiya Perform kar rha hai 