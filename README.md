You may download the file Telecom.pbix to review the dashboard.

Key questions:
1. What's the current churn rate?
2. What's motivating our users to leave or discontinue their subscription to Telecom?
3. Is there a difference between user groups if we consider categories such as age group or subscription category?


DAX formulas used:
Churned = IF('Databel - Data'[Churn Label] = "No", 0, 1)
Churn Rate = [Number of Churned Customers] / [Number of Customers]
Avg Customer Service Calls = SUM('Databel - Data'[Customer Service Calls])/[Number of Customers]
AVG Extra Data Charges = SUM('Databel - Data'[Extra Data Charges])/[Number of Customers]
Avg Extra International Charges = SUM('Databel - Data'[Extra International Charges])/[Number of Customers]
Contract Category = SWITCH( 'Databel - Data'[Contract Type],
    "One Year", "Yearly",
    "Two Year", "Yearly",
    "Monthly"
Demographics = IF('Databel - Data'[Senior]="Yes", "Senior", IF('Databel - Data'[Under 30]="Yes", "Under 30", "Other"))
Number of Churned Customers = SUM('Databel - Data'[Churned])
Number of Customers = COUNT('Databel - Data'[Customer ID])
Number of Unique Customers = DISTINCTCOUNT('Databel - Data'[Customer ID])


Insights
1. The current churn rate sits at 26.86%
2. Churn reasons: a significant number of users reported receiving a better offer from the competition and poor customer service as their primary reasons for leaving.
3. Churn rate by age group: senior users tend to leave much more than their younger counterparts
4. User categories: those with an unlimited data plan and a consumption rate of less than 5 gb have the highest churn rate

Some key suggestions
- We must revise pricing strategies to offer better alternatives for low-usage customers.
- User dissatisfaction must be addressed by enhancing the customer service experience.
- We require alternatives tailored for older users to bridge potential technology or service gaps.
