Model Overview: This dynamic model prices level term insurance using expected present value methodology. Gross premiums are derived from the equivalence principle, including fixed and variable expenses, and profit margin. All outputs update automatically based on a single assumptions panel. Gross reserves are calculated recursively. Sensitivity analysis and Monte Carlo simulation are performed on key assumptions.
Product Assumptions: Level term life insurance with variable issue age, term length, face amount, and risk classification (Male/Female x Smoking/Non-smoking). 
Financial Assumptions:
Assumption	Value
Interest rate	5%
Expense load	15%
Fixed expense	$50/yr
Profit margin	5%
	
Model Structure:
•	Assumptions – contains product inputs (issue age, term length, face amount, risk class) and financial assumptions (interest rate, expenses, profit margin)
•	Mortality – stores the four tables and retrieves rates based on risk class, issue age, and policy duration
•	Pricing model – performs calculations for the annuity factor, premiums, profits, and reserves
•	Sensitivity – shows graphics for gross premium based on risk class and issue age, reserve profile for a policyholder, and the effect of profit margin and expense load on gross monthly premium
•	Simulation – performs a Monte Carlo simulation, assuming interest rate ~ N(.05,.012) and mortality load ~ N(1,.12) 
Example scenario: For a 35-year-old non-smoking male with a $500,000 20-year term policy , the gross annual premium is: $697.16, and each policy is expected to net $454.28 In present value profit.

Methodology:
•	Mortality: rates are sourced from the 2015 VBT select and ultimate tables, age nearest birthday. A 25-year select period is used, after which ultimate rates apply. Four different tables are used based on the policyholder’s demographic.
•	Payment timing: Premiums are assumed to be paid monthly, using the uniform distribution of death assumption. Death benefits are assumed to be paid at the end of year of death. Expenses are applied annually as a fixed expense plus a percentage of premium
•	Reserves: Gross reserves are recursively calculated using the prospective method.
•	Sensitivity analysis: Key assumptions are individually stressed to illustrate their impact on gross premium, and profits. Gross premium is varied on Issue age and risk class, as well as expense load and profit margin. Profits are varied on interest rate and mortality load. 

Limitations:
•	No lapse rates – The model assumes all policies will remain in force until death or expiry. This simplifies the framework at the expense of real-world behavior
•	No substandard rating – Only standard smoking and non-smoking risk classes are modeled
•	Level premiums only – No different pay structures are included
•	No regulatory constraints – reserve requirements and other state regulations are ignored
•	Purely deterministic – Base assumptions are deterministic. Monte Carlo simulation is provided for illustrative variability analysis only. 

Data source: 
Society of Actuaries. (2015). 2015 Valuation Basic Table (VBT) Smoker Distinct. Retrieved from https://www.soa.org/resources/experience-studies/2015/2015-valuation-basic-tables/
