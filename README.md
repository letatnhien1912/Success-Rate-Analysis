# Transactions Low Success Rate Diagnostic Analysis
Hello! My name is Nhien Le, and this is a practice analysis project in my portfolio. This project is an analysis of the low success rate of transactions in Paytm's wallet service. Paytm is an Indian financial technology company that specializes in digital payments, e-commerce, and financial services. Its wallet service allows customers to top up their account, transfer money to a bank account, or another Paytm wallet, and make payments using different payment channels and platforms.

After calculating the success rate by transaction type, the finding is that the rate of "Top-up account" type is the lowest compared to other types. The objective of this project is to analyze the possible reasons for this low success rate and suggest solutions to improve it.

<img src="image/Success Rate by Transaction Type.png" alt="Success Rate by Transaction Type" width="500"/>

### Dataset Description
The project is based on a small database of payment transactions from 2019 to 2020, which includes 6 tables, namely:
- fact_transaction: Store information of all types of transactions: Payments, Top-up, Transfers, Withdrawals
- dim_scenario: Detailed description of transaction types
- dim_payment_channel: Detailed description of payment methods
- dim_platform: Detailed description of payment devices
- dim_status: Detailed description of the results of the transaction

The Paytm wallet dataset contains information about all types of transactions made by Paytm's customers, including Payments, Top-up, Transfers, and Withdrawals. It also includes detailed descriptions of transaction types, payment methods, payment devices, and transaction results.

### Analysis Process
To effectively analyze the low success rate of transactions, we created a comprehensive brainstorming logic chart. Our thought process began with a thorough examination of the potential objects. This includes analyzing customer segments and demographics to gain insight into customer behavior. Additionally, we evaluated different transaction scenarios to determine if there is any correlation between specific transaction types and success rate. Timing is also a critical factor, as we examined differences in transaction success rates based on month/year, weekday, and time of day to identify any patterns.

To determine the root cause of the low success rate, we analyzed both internal and external issues. On the internal side, we considered system errors, including payment channel issues such as local card, debit card, credit card, bank account, and balance, as well as the payment platform, including iOS, Android, and Web. On the external side, we evaluated the potential impact of customer ignorance of the process or incorrect password entry.

### We prioritized the analysis into two tasks, analyzing the factors of internal and external issues.

1. Internal Issues Analysis
<br> 1.1 Is there any difference in success rate and volume ratio between payment channels? Are there any changes over time (by month)?
<br> 1.2 Is there any difference in success rate and volume ratio between payment platforms? Are there any changes over time (by month)?
<br> 1.3 Is there any difference in success rate and volume ratio between scenario IDs?
<br> 1.4 Which are the main errors of failed transactions? Are there any changes over time (by month)?

2. External Issues Analysis
<br> 2.1 What percentage of the total number of failed transactions were the transactions that occurred before the customer's first successful Top-up time?
<br> 2.2 Percentage of error reasons coming from customers in the total error messages?
<br> 2.3 Does the promotion factor affect the success rate result?
   
### Results
Although Top-up account has low success rate overall but the number of failed transactions decreased significantly by time, so it might not an urgent and impactful problem. Instead, "Payment" type has dramatical increase over time, speacially recently, so it is neccessary to address its problem by another analysis.

**For internal issues analysis**, I have defined that there are some technical issues needed the IT team to check, including "Local card" and "Debit card" for Payment Channel as fluctuating success rate over time. Besides, web platform also got a problem of low success rate over time and stop recording in April 2020, but the volume is too low so it is not a significant problem.

**For external issues analysis**, I addressed that the responsibility of the majority of failed transactions (more than 90%) belongs to customers, mostly because of not having enough funds and incorrect password (without counting the ambigious description of "Payment failed" which is needed to be clarified later). In addition, most of failed transaction are made by new customers who did not know how to make transactions in a right way, and that is improved significantly after their first successful transaction. Therefore, my suggestion for the marketing/sales team is to improve in customers education in terms of making transactions awareness.
