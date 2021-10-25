Mortgage Calculator with Zillow API

Task:

Create a Custom Mortgage Calcualtor that would display the potential savings if the user were to refinance their home in today's market.

As an added tweak, we will also be assuming the user is refinancing their home and purchasing a brand new solar system that should be included in the new loan total.
For this project, we will use Zillow's API to pull their listed mortgage rates.

To start, the user would need to fill out a form with the following fields: 

Current Home Value, Current Mortgage Balance, Monthly Mortgage Payment, Monthly Energy Bill, and Current Credit Score.

From those values, we will need to display the users new interest rate, monthly mortgage payment (including the solar system installation expenses), Solar System 

Size, Solar System Cost, Out of Pocket Expenses, New Loan Total, Potential Monthly and Yearly Savings, Tax incentives, and Cash Rebates.

All of these results should be calculated in real time and displayed to the user as they enter their data.

The displayed Values will need to update everytime the user changes a field within the form.

Form Input Fields:
1.	Value of Home
2.	Current Mortgage Balance
3.	Monthly Mortgage Balance
4.	Montghly Energy Bill
5.	Credit Score
6.	Add a Solar Battery (Boolean)
- If true, add $13,500 to Totala System Cost
- If true, add $2,780 Cash Rebate to Savings

Calculated Fields:
1.	Interest Rate:
- pulled from Zillow API from user-inputed data
2.	New Monthly Mortgage Payment:
- (Loan Total * (Interest Rate / 1200)) /(1 - Math.pow(1 / (1 + Interest Rate / 1200), 30 * 12))
3.	Property Tax Fees:
- (Value of Home * 0.01) / 12;
4.	System Size:
- ((Monthly Energy Bill/.11) * 12)/2190
5.	System Cost:
- (Sytem Size * 3.5 * 1,000) + Solar Battery($13,500)
6.	Out of Pocket Costs:
- $0.00 (Constant: assume no out of pocket costs)
7.	Loan Total:
- System Cost + Current Mortgage Balance
8.	Tax Incentive Credit:
- 26% of System Cost
9.	Cash Rebate:
- $2,780.00 (Constant: included if user opts to purchase Solar Battery)
10.	Current Monthly Savings:
- Current Monthly Expenses - New Mortgage
- Assumes there is no energy bill due to Solar Installation
11.	Current Yearly Savings:
- Current Monthly Savings * 12

