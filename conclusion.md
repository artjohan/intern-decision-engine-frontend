# Overview of the implementation of TICKET-101

## What was good

- The design is simple, clean and easy to understand
- Thanks to the sliders there is not much room for user error
- The page renders errors well, giving instant feedback to the user

## Places for improvement

- The biggest shortcoming of the frontend design was the displaying of the approved loan amount, as due to how the code was written, the correct data that was being sent from the backend was not being displayed correctly. This meant that the program did not tell the person the highest amount that we would approve, but would instead only show the amount that they were requesting. This did not seem to be a problem if the amount the person was requesting was too high. In that case the correctly adjusted amount would be displayed
- The slider division amount was 40, which is unnecessay considering that there were only 9 options of 6 month increments to choose from
- The slider was sending the same request multiple times due to the division amount being 40, as it would send a request for each division. A better solution would be to make as many divisions as there are options
- The live updates via server requests every time an input was changed could be taxing on the backend in the long run. Consider implementing a calculation button in the future which would then send the request with the chosen data. However the program works fine currently so this is not a major problem
- The text for the minimum value displayed "6 months", when the allowed minimum was 12
- Whenever there is an error message, the approved loan amount and loan period text elements still show up, which could make the result a little cluttered

## Changes that were implemented

- Fixed the main functionality issue of the frontend not displaying the correct information that was sent from the server
- Changed the slider division amount to 48 and removed the 6 month increment constraint. This allows the user to have more flexibility when choosing their loan period, as they have 48 different month options to choose from
- Fixed the minimum value text element so it now correctly displays "12 months"
- Removed the loan amount and period text elements if there is an error message 
