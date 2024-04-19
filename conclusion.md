TICKET-101

- fixed the frontend not correctly displaying the loan amount that was sent from the backend
- slider division amount was 40, which did not make sense, as there were only 9 options to choose from
- slider was also sending the same request multiple times due to the division amount being 40, as it would send a request for each division
- changed the slider division amount to 48 and removed the 6 month constraint, to allow the user to have more flexibility in terms of a loan period
- the text for the minimum value said 6 months, when the allowed minimum was 12
- made it so the approved loan amount and period text elements don't show up if there is an error message, to make the result less cluttered
