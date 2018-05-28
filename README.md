# finance-logic-js

### Installation
```
npm install finance-logic-js

```

### Usage
```
const finance = require('finance-logic-js')

finance.GenAmortizationSchedule()

or (ES6)
import { GenAmortizationSchedule } from 'finance-logic-js'

```


GenAmortizationSchedule
-----------------------
This function generates an amortization schedule. The schedule is returned as a Javascript object.

The function accepts the following arguments:
* amount (required): the starting principal amount of the loan
* months (required): the number of whole months over which the loan extends
* rate (required): the annual interest rate of the loan expressed as a percentage, e.g., 10.5
* firstPaymentDate (optional): the date the first payment will be made
* frequency (optional): the payment frequency, which can be any of the following:
    12 - monthly
    6 - half yearly
    none or one - only one payment at the end of the loan - typically don't mix this with balloonDate
* balloonDate (optional): the date a balloon payment will be made. This date will be forced to earliest
corresponding payment date. This date will be ignored if it is greater than the term (months) of the
loan.
* balloonPercent(required): The percentage of the principal amount that will be used as the balloon value

The return object contains an array, with each array element containing the following fields:
* paymentNumber - the number for a payment
* principle: the principal balance remaining at the end of the period
* accumulatedInterest: the interest accumulate from all previous periods through this period
* payment: the periodic payment the borrower is required to pay
* paymentToPrinciple: the amount of the payment allocated to paying down the principal
* paymentToInterest: the amount of the payment allocated to paying interest
* date: the date of the payment for the period
