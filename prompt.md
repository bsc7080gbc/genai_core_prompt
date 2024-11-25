a good prompt is highly subjective. a better prompt is more appropriate as often people ask questions as they would a web search engine assuming the experience will magically be correct on the first go. even search engines don't work like that. this usually ends in frustration. we see a lot of it at work. we then take their inquiry and refactor it with additional context and framework or structure. then share and explain and often hear them respond this new result is what they were expecting. from there it simply became a learning lesson that changed how they work with AI from then on.

my typical approach is to use markdown to structure my prompt. here is an example model and example usage:

<details>
  <summary>Example Template</summary>


```
# INQUIRY​ ​

{state core prompt here}

# ASSUMPTIONS​ ​

{state assumptions here}

# DATA_QUALITY

{specify your data quality elements here - good vs bad data}

# MENU

After each response display the following menu PRECISELY AS DISPLAYED HERE:
{adjust menu as desired}

"

Please choose an option by typing 'D', 'S', 'V', 'F' or any combination, e.g. SF. Please choose 'Q' to quit.

(D)isplay Code, (S)ummary, (V)alidation, (F)eedback, (Q)uit

"

# REQUIREMENTS​ ​

{specify your requirements here}

# INSTRUCTIONS

{adjust menu instructions to match menu above}

Process [REQUIREMENTS] but only display [MENU] and {pause} for user response. If user selects 'D' then show code.
If user selects 'S' then show summary explanation of work. If user selects 'V' then show validation.
If user selects 'F' then show feedback. User can show any combination as well, e.g. SVF would show summary
explanation plus validation plus feedback. then show [MENU] again and {pause} for user response.
If user selects 'Q' then respond with "Thank you. Goodbye."

# VALIDATION​ ​

Work backwards from your answer and provide supporting explanation that justifies your response.​ ​

# FEEDBACK​​

Provide recommendations on how I can improve my original inquiry to ensure you have a clear understanding and can provide an appropriate and accurate response consistently.​​

```
</details>


<details>
  <summary>Example Usage</summary>

https://chatgpt.com/share/67444511-82fc-800c-8d66-669ea92f493c

```
# INQUIRY​ ​

split a pandas dataframe column into multiple columns delimited by comma​ ​

# ASSUMPTIONS​ ​

* I know how to install pandas​
* I know how to import pandas​
* Software from outside our corporate network is against our company policies.
  Software can only be installed from go/shopping and go/software​ ​
* All operations should be performed with available tools and/or libraries

# DATA_QUALITY

* All date fields must be formatted 'YYYY-MM-DD'
* All member numbers must be prefixed with AIN followed by a 6 digit number padded by zeroes (0)
* All customer names require at least one alpha character
* All purchase order numbers are prefixed with PO followed by a 5 digit number padded by zeroes (0)
* Y/N flags should only be uppercase values of Y or N

# MENU

After each response display the following menu PRECISELY AS DISPLAYED HERE:

"

Please choose an option by typing 'D', 'S', 'V', 'F' or any combination, e.g. SF. Please choose 'Q' to quit.

(D)isplay Code, (S)ummary, (V)alidation, (F)eedback, (Q)uit

"

# REQUIREMENTS​ ​

1. dataframe is called 'df' with a column 'data' that contains comma-separated values
2. add escape character for values with quotes in them or other special characters that cause malformed dataframe
3. include date formatting of 'YYYY-MM-DD'
4. populate dataframe with good sample data
5. append dataframe with bad data
6. ensure five (5) columns are generated after splitting the 'data' column
7. column names are to be as follows and in order:
    'ORDER_DATE','MEMBER_NUMBER','CUSTOMER_LAST_NAME','PURCHASE_ORDER','PROCESSED_YN'​
8. additional column added called 'RECORD_MSG' to hold any notations regarding record quality
9. identify incorrect data and add text to 'RECORD_MSG' column that indicates what is bad
10. ensure missing values have LOCF applied across all columns
11. do not retain the original data column after the split is performed
12. provide exception handling assuming this block is to be wrapped in a try-except for a real scenario
13. provide code in a single formatted python code block​

# INSTRUCTIONS

Process [REQUIREMENTS] but only display [MENU] and {pause} for user response. If user selects 'D' then show code.
If user selects 'S' then show summary explanation of work. If user selects 'V' then show validation.
If user selects 'F' then show feedback. User can show any combination as well, e.g. SVF would show summary
explanation plus validation plus feedback. then show [MENU] again and {pause} for user response.
If user selects 'Q' then respond with "Thank you. Goodbye."

# VALIDATION​ ​

Work backwards from your answer and provide supporting explanation that justifies your response.​ ​

# FEEDBACK​​

Provide recommendations on how I can improve my original inquiry to ensure you have a clear understanding
and can provide an appropriate and accurate response consistently.​​

```  
</details>
