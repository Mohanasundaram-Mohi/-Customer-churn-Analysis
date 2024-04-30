#  Customer churn Analysis - Dashboard

📊 Thrilled to unveil my latest endeavour: a comprehensive Customer churn analysis project focused on Explore Customer churn, meticulously crafted using Power BI and Microsoft Excel! 🚀

 ## Here's what you can expect from this dashboard:

🛠️ Toolkit: Power BI, Microsoft Excel

📊 Datasets: Microsoft Excel

Project Overview:

Diving deep into Customer churn, this project revolves around Active/Inactive and credit card holder, exit and retain of the customers. 

Here's what you can expect from this dashboard:

• Getting customer details by year/month and geographical location wise, exit/gender category. 

• Exit customers comparison

• Exit customers by credit type 

• Exit customers by Gender type 

# DAX 

Used Time Intelligence functions 
Date Master = CALENDAR(FIRSTDATE(Bank_Churn[Bank DOJ]),LASTDATE(Bank_Churn[Bank DOJ]))
Month = MONTH('Date Master'[Date])
Month Name = FORMAT('Date Master'[Date],"MMM")
Year = YEAR('Date Master'[Date])

Data Relation/modelling : creating relations with data. 
DAX functions :
Total customers = Count(Bank_Churn[CustomerId])

Active Members = CALCULATE(COUNT(Bank_Churn[CustomerId]),'Activecustomers'[activeCategory]="Active Member")

Credit card Holders = CALCULATE(count(Bank_Churn[CustomerId]),'Credit card'[Category]="credit card holder")

Non Credit card holder = CALCULATE(count(Bank_Churn[CustomerId]),'Credit card'[Category]="non credit card holder")

Inactive Members = CALCULATE(COUNT(Bank_Churn[CustomerId]),'Active customers'[ActiveCategory]="Inactive Member")

Exit customers = CALCULATE(COUNT(CustomerInfo[CustomerId]),'Customer Exit'[ExitCategory]="Exit")

Retain Customers=[Total customers]-[Exit customers]

DAX creation for the new column 

Creadit Type = SWITCH(TRUE(),Bank_Churn[CreditScore]>=800 && Bank_Churn[CreditScore]<=850,"Excellent",Bank_Churn[CreditScore]>=740 && Bank_Churn[CreditScore]<=799,"very good", Bank_Churn[CreditScore]>=670 && Bank_Churn[CreditScore]<=799,"Good", Bank_Churn[CreditScore]>=580 && Bank_Churn[CreditScore]<=699, "Fair", Bank_Churn[CreditScore]>=300 && Bank_Churn[CreditScore]<=579, "Poor")

Previous Month exit cusotmer = CALCULATE([Exit customers],PREVIOUSMONTH('Date Master'[Date]))

#
Dashboard Screenshot

![Screenshot (18)](https://github.com/Mohanasundaram-Mohi/-Customer-churn-Analysis/assets/168515064/958b3cdf-2359-488b-a3cc-ea4cc28f71f7)

![Screenshot (19)](https://github.com/Mohanasundaram-Mohi/-Customer-churn-Analysis/assets/168515064/180949dc-a1ce-462f-822c-9e18361fcdf5)



 
