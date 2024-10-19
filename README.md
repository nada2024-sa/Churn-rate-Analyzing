
# Churn rate Analyzing

In this Power BI case study, I'll investigate a dataset from an example telecom company called Databel and analyze their churn rates.
Analyzing churn mean knowing what the churn rate is and figuring out why customers are churning, and how to reduce churn.

The first step on this project is to explore the  dataset and to measures to get a better understanding of why customers are churning.


Some of the measures and columns that I created : 

Number of customers  : This measure calculate the Number of customers

Number of customers = COUNT('Databel - Data'[Customer ID])


This column convert the Churn Label column into a Churned column using an IF() statement. This formula checks if the value in the Churn Label column is "Yes". If it is, it assigns a 1 and if it's not, it assigns a 0.
Churned = if('Databel - Data'[Churn Label]="Yes",1,0)

Churn rate 
churn rate = var churned= 'Databel - Data'[Number of churned]
var alldata= COUNT('Databel - Data'[Churned])
RETURN churned/alldata

Number of churned = CALCULATE(COUNT('Databel - Data'[Customer ID]),FILTER('Databel - Data','Databel - Data'[Churned]=1))

Demographics = if('Databel - Data'[Senior]="Yes","Senior",If('Databel - Data'[Under 30]="Yes","Under 30","Other"))


Grouped Consumption = IF('Databel - Data'[Avg Monthly GB Download]<5,"Less than 5 GB", IF('Databel - Data'[Avg Monthly GB Download]<10,"Between 5 and 10 GB","10 or more GB"))


Snaps of my dashboard

![CHURNRATE1](https://github.com/user-attachments/assets/00941008-bf48-42fd-9987-78f09c258f4c)

![CHRNRATE2](https://github.com/user-attachments/assets/a69e1e5c-2cd3-4016-a6e3-2830d5e222f4)
![CHURNRATE3](https://github.com/user-attachments/assets/ce2bcfa1-2042-4161-91a6-e5abf091143b)
