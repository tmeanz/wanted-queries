<img src="https://devmounta.in/img/logowhiteblue.png" width="250" align="right">

# Wanted Queries

This project is to create a web form that will generate the text as if to submit to the NCIC to add, edit, or delete a warrant.

It is assumed that if incorrect entry occurs, the proper error message will be displayed to assist the user in correcting their mistakes.

### Menu

There should be a popout menu at the top left to navigate between the Home, Enter, Modify, and Cancel screens.

### The requirements are as follows for each screen, and the results:


<details>

<summary> Home </summary>

#### Screen Summary

This screen exists to give a brief description of what each of the other screens is intended for.

</details>


<details>

<summary> Enter Wanted Requirements </summary>

<br />

#### This screen exists to generate the text string which will be sent to the state or federal government, who will register a warrant using the supplied information.

##### Entry Requirements
*alpha*: any alphabetical characters, upper or lower case

*numeric*: numbers only, 0-9

*special*: these are any characters other than numbers and letters, including blank spaces ' '.  Also, periods '.' should not be allowed as they can break message parsing.

##### Field Requirements
* Header: Required, 9-19 characters in length, any allowed
* MKE: Required, 2-4 alpha/special characters in length
* Originating Agency Identifier: Required, 9 alphanumeric characters in length
* Name: Required, 3-30 characters in length, any allowed
* Sex: Required, Dropdown where Female, Male, Other, and Unknown are the only accepted entries, reflected by 'F', 'M', 'O', and 'U' respectively in the assembled query
* Race / Ethnicity: Required, Dropdown where Asian/Pacific Islander, Black, Hispanic, American Indian / Alaskan Native, White, and Unknown are the only accepted entries, reflected by a 'A', 'B', 'H', 'I', 'W', and 'U' respectively in the assembled query
* Height: Required, 3 characters in length, numeric only in FII format, where F is feet and I is inches
* Weight: Required, 1-3 characters in length, numeric only in lbs, leading zeros to be entered systematically as necessary to change the length to 3 characters in the assembled query.
* Hair: Required, 3-10 characters in length, alpha only
* Offense: Required, 5-15 characters in length, any allowed
* Date of Warrant/Violation: Required, Date Picker or Freeform entry, 10 characters in length, numeric in MM/DD/YYYY format (allows dates from 1900 to today +1 day, to account for time zone differences)
* Drivers License: Optional, 1-20 characters in length, any characters allowed, if included requires DL State & DL Expiration Year
* DL State: Optional, 2 characters in length, State Abbreviations only, if included requires Drivers License & DL Expiration Year
* DL Expiration Date: Optional, 10 characters in length, numeric in MM/DD/YYYY format, if included requires Drivers License & DL State, can be future dated, but still cannot preceed 1900.
* License Plate: Optional, 5-8 alphanumeric characters in length, if included requires License State & License Year
* License State: Optional, 2 characters in length, State Abbreviations only, if included requires License Plate and License Year
* License Expiration Date: Optional, Date Picker or Freeform entry, 10 characters in length, numeric in MM/DD/YYYY format, if included requires License Plate and License Year, can be future dated, but still cannot preceed 1900.

##### Results
Upon successful entry, a text message will be created, which consists of each of the values entered, separated by a '.' - any optional fields left blank will still be denoted in the message by an additional '.'

</details>

<details>

<summary> Modify Wanted Requirements </summary>

#### This screen exists to generate the text string which will be sent to the state or federal government, who will use the Warrant ID to find an existing warrant which will be modified with any other supplied information.

##### Screen Specific Requirements:
* Only the Warrant ID field is individually required
* At least ONE other field must be populated (any populated fields will overwrite the value in the recipients' database(s))

##### Entry Requirements
*alpha*: any alphabetical characters, upper or lower case

*numeric*: numbers only, 0-9

*special*: these are any characters other than numbers and letters, including blank spaces ' '.  Also, periods '.' should not be allowed as they can break message parsing.

##### Field Requirements
* Warrant ID: Required, 10 numbers - this ID is returned to the sending organization by the receiving organization when a warrant is entered.
* Header: Optional, 9-19 characters in length, any allowed
* MKE: Optional, 2-4 alpha/special characters in length
* Originating Agency Identifier: Optional, 9 alphanumeric characters in length
* Name: Optional, 3-30 characters in length, any allowed
* Sex: Optional, Dropdown, Female, Male, Other, and Unknown are the only accepted entries, reflected by 'F', 'M', 'O', and 'U' in the assembled query
* Race / Ethnicity: Optional, Dropdown where Asian/Pacific Islander, Black, Hispanic, American Indian / Alaskan Native, White, and Unknown are the only accepted entries, reflected by a 'A', 'B', 'H', 'I', 'W', and 'U' respectively in the assembled query
* Height: Optional, 3 characters in length, numeric only in FII format, where F is feet and I is inches
* Weight: Optional, 1-3 characters in length, numeric only in lbs, leading zeros to be entered systematically as necessary to change the length to 3 characters in the assembled query.
* Hair: Optional, 3-10 characters in length, alpha only
* Offense: Optional, 5-15 characters in length, any allowed
* Date of Warrant/Violation: Optional, Date Picker or Freeform entry, 10 characters in length, numeric in MM/DD/YYYY format (allows dates from 1900 to today +1 day, to account for time zone differences)
* Drivers License: Optional, 1-20 characters in length, any characters allowed, if included requires DL State & DL Expiration Year
* DL State: Optional, 2 characters in length, State Abbreviations only, if included requires Drivers License & DL Expiration Year
* DL Expiration Date: Optional, 10 characters in length, numeric in MM/DD/YYYY format, if included requires Drivers License & DL State, can be future dated, but still cannot preceed 1900.
* License Plate: Optional, 5-8 alphanumeric characters in length, if included requires License State & License Year
* License State: Optional, 2 characters in length, State Abbreviations only, if included requires License Plate and License Year
* License Expiration Date: Optional, Date Picker or Freeform entry, 10 characters in length, numeric in MM/DD/YYYY format, if included requires License Plate and License Year, can be future dated, but still cannot preceed 1900

##### Results
Upon successful entry, a text message will be created, which consists of each of the values entered, separated by a '.' - any optional fields left blank will still be denoted in the message by an additional '.'

</details>

<details>

<summary> Cancel Wanted Requirements </summary>

#### This screen exists to generate the text string which will be sent to the state or federal government, who will use the Warrant ID to find and cancel an existing warrant.

##### Entry Requirements
*alpha*: any alphabetical characters, upper or lower case

*numeric*: numbers only, 0-9

*special*: these are any characters other than numbers and letters, including blank spaces ' '.  Also, periods '.' should not be allowed as they can break message parsing.

##### Field Requirements
* Warrant ID: Required, 10 characers in length, numeric only - this ID is returned to the sending organization by the receiving organization when a warrant is entered.
* Reason for Cancellation: Required, 10-150 characters in length, any allowed - this is a free text field to explain why a warrant is being cancelled.
* Date of Cancellation: Required, Date Picker or Freeform entry, 10 characters in length, numeric in MM/DD/YYYY format - this is the date the cancellation is to take effect, can be future dated, but still cannot preceed 1900.

</details>


### Error Handling

Any error in entry should have a contexcualized error displayed in a bulleted list the same area a valid query would have appeared.  No assembled query will appear, instead you will see a message 'No results generated due to error.'  Any field that has an incorrect entry will also be highlighted in red until emptied out or resubmitted.

See below for an example of each error message.

<details>

<summary> Required field missing </summary>

* The "Header" field must be included.
* If one of the following are present, all must be present: Drivers License, DL State, DL Expiration Date.

Empty required fields are also hilighted in blue.

</details>

<details>

<summary> Invalid characters entered </summary>

* The "Originating Agency Identifier" field can only include characters from the English Alphabet or numeric characters.
* The "MKE" field has one or more periods, which are unacceptable in any field.
* The "Weight" field needs to have a value greater than 0.

</details>

<details>

<summary> Invalid length </summary>

* The "Height" field should be 3 characters long.

</details>

<details>

<summary> Invalid date </summary>

* The "Date of Warrant/Violation" field must be entered as a date, MM/DD/YYYY, no earlier than 01/01/1900 and no later than today's date.
* The "DL Expiration Date" field must be entered as a date, MM/DD/YYYY, no earlier than 01/01/1900 and no later than today's date.

</details>

<br />

Current Version: **1.1**

<details>

<summary> Change Log for 1.1 </summary>

**Updated readme for:**
* Date fields - updated to date picker, no date before 1900, even on expirations
* Sex - details on the dropdown added
* Race - changed to 'Race / Ethnicity' and details on the dropdown added
* Special Characters - clarification in rules
* Error Handling - examples of error messages and how errors as a whole are handled
* Typos

**Added Validation for:**
* Periods in any field will now generate a field specific error message - for example: "The "Name" field has one or more periods, which are unacceptable in any field."

**Bug Fix:**
* The "Modify" screen now will enforce that at least one optional field has to be entered
* The weight field will no longer autofill with 000s.

**Improvements:**
* Placeholder text added to all fields.
* Empty required fields and fields in error are now highlighted, blue and red respectively.

</details>

## Contributions

If you see a problem or a typo, please fork, make the necessary changes, and create a pull request so we can review your changes and merge them into the master repo and branch.

## Copyright

© DevMountain LLC, 2018. Unauthorized use and/or duplication of this material without express and written permission from DevMountain, LLC is strictly prohibited. Excerpts and links may be used, provided that full and clear credit is given to DevMountain with appropriate and specific direction to the original content.

<p align="center">
<img src="https://devmounta.in/img/logowhiteblue.png" width="250">
</p>