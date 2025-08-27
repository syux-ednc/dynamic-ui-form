# dynamic-ui-form
This repo stores a sample JSON form ui config.

## Field Explanation

id
- TYPE: string
- represents the "id" in HTML syntax
- can be used for SELENIUM for Web Testing

name
- TYPE: string
- represents the "name" in HTML syntax

title
- TYPE: string
- The header of the form field

desc
- TYPE: string
- Desciption of the form field
- Usually used to provide more context about the title

tooltip
- TYPE: string
- Provide additional information (not as impt as "desc") about the form field
- Usually a info icon that is hoverable

placeholder
- TYPE: string
- Provide some context on how to use the form field
- Usually found in TEXTFIELD, DROPDOWN etc...
- Usually a grey descriptive text in the form field, disappear when "onTouch"

type
- TYPE: enum
- Indicates what type of form field
- Example values: TEXTFIELD, CHECKBOX, RADIO, TIME_PICKER, CURRENCY, FILE_UPLOAD etc...

value
- TYPE: depends...
- Actual value of the form field
- May vary depending on "type" field
- E.g. In the case of CHECKBOX, it is an "array of string"
- E.g. In the case of RADIO, it is either "true" or "false"

readOnly
- TYPE: boolean
- Indicates whether form field is for display / view purposes only, non-editable

disabled
- TYPE: boolean
- Shows up in the UI as "greyed-out", implies "temporary" non-editable form field

visible
- TYPE: boolean
- If true, the form field is visible in the UI screen.
- If false, this form field will not show up at all in the UI screen.
- Usually used to remove certain form fields if they are not in use but planning to put back in the future.

options
- TYPE: Array of string
- Usually used for DROPDOWN, CHECKBOX, RADIO "type" to indicate the available choices to choose from.

validations
- TYPE: Array of Object
- Indicators the number of validations the form field needs to pass before "submission"

-----------------
Validation Object
-----------------

validator
- TYPE: enum
- Indicates the type of validator
- E.g. REQUIRED, LIMIT, FILE_SIZE, FILE_TYPE, REGEX etc...

value
- TYPE: depends...
- Indicates the validator value (if required)
- E.g. For LIMIT, it could be "50", which indicates the value should not exceed 50.
- E.g. FILE_TYPE, it could be ["JPG", "PNG"], which means only allowed file types during file upload.

message
- TYPE: string
- The error message to display in red text in the UI.
- E.g. "File size exceeds 50MB! Not allowed!"
