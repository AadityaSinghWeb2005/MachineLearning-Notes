![[Pasted image 20260201195311.png]]


this technique is used where is a normal distribution so it means 68 % values lies in first std. deviation and 95% values lies in 2nd std. deviation and 99% values lies in Third Std. Deviation 
Example : We need to find outliers of age column so we applied Z-score on all the values of Age column if any values lies out of the range of -3 to 3 then its a outlier 
z-Score Formula : Xi '= (Xi - Mean of Age Column)/Std. deviation of Age column 

How to Handle the outliers ? 
So lets say we have 5 observations which are outlier now we can use 2 techniques Either we trim (means we remove those 5 rows out of the dataset ) but the fault in this technique is that if quantity is high for outliers that means Dataset become thin so we dont use it 

second technique is Capping so we know the range of normal Distribution is (mean+3std. deviation , mean-3std. deviation ) we just cap these range by just eg. mean + 3std. dev= 80 (max value) , mean-3std. deviation = 3(min ) and any outliers(eg. 83,2,) comes then we just change them to their limit like 85 becomes 80 and 2 becomes 3 