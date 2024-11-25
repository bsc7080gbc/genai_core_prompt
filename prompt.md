a good prompt is highly subjective. a better prompt is more appropriate as often people ask questions as they would a web search engine assuming the experience will magically be correct on the first go. even search engines don't work like that. this usually ends in frustration. we see a lot of it at work. we then take their inquiry and refactor it with additional context and framework or structure. then share and explain and often hear them respond this new result is what they were expecting. from there it simply became a learning lesson that changed how they work with AI from then on.

my typical approach is to use markdown to structure my prompt. here is an example model and example usage:

# EXAMPLE TEMPLATE

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
