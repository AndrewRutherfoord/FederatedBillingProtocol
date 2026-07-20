

BP and CSP make a bilateral billing agreement. 
- Exchange keys used for mTLS
- Agree on billing details
    - Settlement frequency
    - Billing cycle
    - Trust method (Ie. guarantor or prepaid)
- Define communication channels 
- Agree on dispute resolution process

As a result of bilateral agreement, customers can only use supported BPs to pay for their resources with the CSP.

Customer Registers with the Billing Provider and goes through their KYC process. 
- BP decides on the customer's creditworthiness and assigns a credit limit
- The customer may also choose to prepay for services or use a guarantor.
- `BillingAccount` is created for the customer in the BP system. Account `ID` generated and provided to CSPs when creating resources.
- `BillingPeriod` is defined for the customer when the `BillingAccount` is created.
    - Usually monthly billing cycle but can be customized based on agreement with BP

Customer Registers with CSP and goes through their KYC process
- KYC is just for legal compliance and has nothing to do with billing credit worthiness

Customer links their `BillingAccount` with the CSP by providing the `BillingAccount ID` to the CSP (probably in some kind of token or credential format).

Customer creates resources with the CSP.
- Uses CSP billing account which is linked to the BP `BillingAccount` for billing purposes.
- CSP tracks resource usage and applies price table to calculate costs based on usage. These are called Cost Records.
- Periodically (e.g. every hour, or day. ) the Cost Records are aggregated into a Aggregated Cost Record and send to BP
    - Cannot be for the whole billing period otherwise the BP cannot accurately track balance.


