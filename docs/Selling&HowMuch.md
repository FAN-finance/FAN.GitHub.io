## Selling period:

In the case of a default, or the lender not accepting the borrower repayment, or when the asset's price plummits on the outside market and the value of assets is lower than the value of stable coins issued, the lender can opt for liquidation of the collateral through the process(sell(...)) selling out the collateral(OST). The selling period can only be initiated by the lender.

At the end of selling period, if the colleteral is not fully liquidated, the lender shall reduce(reduction(...)) the price, and list them for sale again. Any user can use buy(...) to buy the colleteral at a certain listed price, his FAN will be burned after he calls buy(...).

## How much is burned:

When borrower deposites 100 USD valued OST, the lender issues 100 FANs, transfers 80 FANs to the borrower and locks 20 FANs in the Morgage contract. In this case the loan to value is 80%. 

After borrower repays 80 FANs, the total 100 FANs will be burned. 

If on default, the lender opts to liquidate by selling out OST, he may only cut a deal on price 60,  because the OST's price plummits, then the lender can only burn 60+20 FANs. Their will be 20 FANs in lock.  
