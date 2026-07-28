# MORGAN-STANLEY-Financial-Risk-Analysis-with-Python   
## Project Overview    
Digital banking generates a constant stream of transactional data, but raw transaction logs on their own don't tell a bank's leadership team much. This project simulates the role of a Financial Data Analyst at a global banking institution, tasked with turning raw account and transaction records into a structured view of how customers actually use their accounts, where financial risk is concentrated, and what patterns predict low balances or overdraft activity.              
The project covers the full analyst workflow: cleaning messy real-world-style transactional data, building descriptive summaries, segmenting customers into behavioral profiles, flagging risk using statistical methods, visualizing findings, and validating a hypothesis about the relationship between transaction volume and account balance — all in Python.           
## Objective          
- Build a complete Customer Financial Behavior and Risk Analysis Report that:         
- Cleans and consolidates raw customer account and transaction data.                          
- Uncovers behavioral and transactional insights across account types and customer segments.                      
- Identifies accounts with elevated or inconsistent financial risk.       
- Statistically tests assumptions about the drivers of account balance.                                  
- Translates findings into concrete, data-backed recommendations for customer engagement and monitoring.       
## Dataset Used             
Source: Morgan Stanley Financial Transactional Data.Contains 800 transactions across 8 customers/accounts, spanning January 2023 to June 2024, covering transaction type, amount, account balance, risk score, credit rating, and account tenure.            
## Tools and Technologies             
- Pandas
- Numpy
- Matplotlib
- Seaborn
- Scipy
- Statistcs                    
## Key Business Metrics             
- Total credits in 2023 were about ₹3.09 crore, with debits of roughly ₹2.06 lakh — credits dominate this dataset.         
- 167 of 189 account-transaction records showed a gap of two or more months between transactions, meaning most accounts pattern as dormant under that rule.    
- Accounts split into 71 High-activity, 32 Medium-activity, and 86 Low-activity, based on transaction frequency.     
- No account had a negative or near-zero average balance.    
- 5 of 800 transactions (0.6%) were statistical anomalies by the IQR method; 10 of 189 accounts (5.3%) were flagged Suspicious overall.  
- Neither hypothesis test came back statistically significant: transaction volume and activity level do not reliably predict account balance in this dataset (p = 0.096 and p = 0.168, both above 0.05).            
## Key Insights & Business Recommendations           
- Most accounts show long gaps between transactions, which may reflect either genuine dormancy or simply a sparse transaction history — this should be validated before triggering automated re-engagement campaigns.                 
- 31 accounts are high-frequency but low-balance, meaning they're active customers with thin cash buffers. These are good candidates for overdraft protection or short-term credit outreach.                
- 10 accounts were flagged Suspicious by combining large-withdrawal frequency, balance volatility, and statistical anomaly detection. These should go to manual risk review rather than automated action, since the flags are heuristic.               
- Transaction frequency does not statistically predict account balance in this data, so it shouldn't be used alone as a proxy for financial health in decisions like credit limits.                
- No accounts carry negative or near-zero balances, suggesting the customer base is broadly stable — risk monitoring should focus more on volatility and anomaly flags than on raw balance thresholds.            
## Screenshots             
1. Monthly net transaction volume showing credits far exceeding debits across the observed period:
![image](https://github.com/rajatgusain17/MORGAN-STANLEY-Financial-Risk-Analysis-with-Python/blob/main/Monthly%20Net%20Transaction%20Volume.png?raw=true)

2. Accounts split by activity level, showing Low-activity and High-activity as the largest groups:
![image](https://github.com/rajatgusain17/MORGAN-STANLEY-Financial-Risk-Analysis-with-Python/blob/main/Activity%20Level.png?raw=true)

3. Transaction amounts with statistical outliers flagged using the IQR method:
![image](https://github.com/rajatgusain17/MORGAN-STANLEY-Financial-Risk-Analysis-with-Python/blob/main/Transaction%20Amount%20Distribution.png?raw=true)

4. Balance volatility plotted against average balance, colored by risk status:
![image](https://github.com/rajatgusain17/MORGAN-STANLEY-Financial-Risk-Analysis-with-Python/blob/main/Balance%20Votality%20Vs%20Average%20Balance.png?raw=true)

5. Correlation heatmap showing weak relationships between transaction amount, balance, risk score, credit rating, and tenure:
![image](https://github.com/rajatgusain17/MORGAN-STANLEY-Financial-Risk-Analysis-with-Python/blob/main/Correlation%20Heatmap.png?raw=true)

6. Boxplots comparing average balance across transaction-volume and activity-level segments for the hypothesis tests:
![image](https://github.com/rajatgusain17/MORGAN-STANLEY-Financial-Risk-Analysis-with-Python/blob/main/Boxplots%20comparing%20average%20balance%20across%20transaction-volume%20and%20activity-level.png?raw=true)
## Learning Outcomes              
Through this project I practiced cleaning real-world-style financial data and catching a hidden data quality issue — the TransactionID field wasn't actually unique despite being documented as one. I built time-based aggregations to summarize transaction trends, created rule-based customer segments with clearly documented thresholds, used statistical methods (IQR, z-score, coefficient of variation) to detect financial risk objectively, and applied hypothesis testing to check a business assumption rather than relying on intuition.         
## Conclusion               
Across 800 transactions and 8 accounts, the overall picture is financially stable — no account shows a negative or near-zero balance, and only 5.3% of accounts are flagged as high risk. The more important finding is behavioral, not risk-based: a meaningful group of accounts are active but low-balance, and transaction frequency doesn't statistically predict account balance. The recommendation going forward is to focus monitoring on volatility and anomaly detection rather than balance thresholds, and to support the high-frequency, low-balance segment proactively rather than reactively.
