## Issuance period:

During this time, the stable coin issuer(the lender, admin) deploys the Morgage contract on the etherium blockchain. Following this, the borrower deposits their collateral(OST tokens ) using **pledge(...). **

Pledge(...) examins the deposit amount of assets and issues the equal value in USD of FAN. Then transfer the LTV(Load To Value) amount of FANs to borrower's address and the discount to the Morgage contract address. The colleteral is locked in the Morgage contract till the borrower repays the sufficient FAN (the FAN borrowed plus interest in this period). 


## Loan Period 

Once the borrower has accepted the loan(FAN) amount, the Loan Period begins. Once the Loan Period is finished, the borrower is expected to repay the loan. If he does, he calls **repayment(...)** that can accept the repayment, unlocks the assets(OST) and then refunds the borrower's collateral amount. The repayed stable coins(FAN) are burned.

In the case that the borrower defaults or does not repay the full principal plus interest amount, the lender can choose to not accept the loan repayment, and the parties can opt for liquidation of the collateral in the Selling Period.
