# Support

This article broadly covers the anticipated support issues that may result in using the repository or platform.

## Errors

This is a reference of all Error instances found within the source code to reflect and notate known Error instances that might occur.

### Unknown Error Handling

What additional parameters might we need to report to error logging.

#### Knockers Error Lexical Syntax

To reference an error code for the Knokers platform, will utilize the following syntax structure.

{End Point Instance}-({Error Constructor}-{Function/WorkFlow}){Type:Number}

Error codes will be logged under the following directory:

functions>src>errors>[errors.json](./functions/src/errors/errors.json)

##### End Point Instance

What is the user end that is utilizing the program when the error occurs.

| User Instance  | Symbol/ Acronym | Notes |
| -------------- | --------------- | ----- |
| Cloud Function | CF              |       |
| Knocker        | KN              |       |
| Door Keeper    | DK              |       |
| Guest/Visitor  | GV              |       |
| Door Lord      | DL              |       |
| Admin          | AD              |       |
| Other          | OT              |       |

##### Error Constructor

What is the platform or section that is generating the error?

| Error Constructor | Symbol/ Acronym | Notes |
| ----------------- | --------------- | ----- |
| Third Party       | TP              |       |
| Core Function     | CF              |       |
| Door Portal       | DP              |       |

##### Function/WorkFlow

What is the function or workflow that the end user was attempting to call?

| Function/WorkFlow | Symbol/ Acronym | Notes                                              |
| ----------------- | --------------- | -------------------------------------------------- |
| User Start        | UserStart       | Error associated with linking a thirdparty profile |

##### Type

What type of error is being produced?

| Type        | Acronym/ Symbol | Emoji | Notes                                                                                                                                                             |
| ----------- | --------------- | ----- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Evaluation  | EVAL            | 💭🔍  | Creates an instance representing an error that occurs regarding the global function eval().                                                                       |
| Range       | RANG            | 🔚↔   | Creates an instance representing an error that occurs when a numeric variable or parameter is outside of its valid range.                                         |
| Reference   | REF             | 🔀🔄  | Creates an instance representing an error that occurs when de-referencing an invalid reference.                                                                   |
| Syntax      | SYN             | 🔣✔   | Creates an instance representing a syntax error.                                                                                                                  |
| Type        | TYPE            | 🔠🔢  | Creates an instance representing an error that occurs when a variable or parameter is not of a valid type.                                                        |
| Uri         | URL             | 🔗⤴   | Creates an instance representing an error that occurs when encodeURI() or decodeURI() are passed invalid parameters.                                              |
| Aggregate   | AGG             | ➕📈  | Creates an instance representing several errors wrapped in a single error when multiple errors need to be reported by an operation, for example by Promise.any(). |
| Internal    | IN              | 🔒🙏🏻  | Creates an instance representing an error that occurs when an internal error in the JavaScript engine is thrown. E.g. "too much recursion".                       |
| Permissions | PERM            | ⛔🚦  | Creates an instance representing an error that occurs when a user attempts to performan an action that results in denial due to permissions.                      |
| Finance     | FIN             | 💲💱  | Creates an instance representing an error that occurs when a function/workflow is unable to process due to a financial status.                                    |
| Expiration  | EXP             | ⏳⏲   | Creates an instance representing an error that occurs when a set time frame has expired either due to policy or other limitations.                                |
| Other       | OTH             | ❔⚠   | Creates an instance representing an error that is labeled as miscellaneous.                                                                                       |

##### Number

What is the instance number that the error is being formally recognized?

Will start iterating the log of Error codes in the [errors.json](./functions/src/errors/errors.json)

### Error Handling Structure

Will need to reference a shared function I will likely publish to npm for reference. Want to be able to return the error object but also a more customizable display.

1. Pass in Error object & known Error Code

2. Log the Error Object

3. Return Customizable Reference

4. If we know the Error Code and object isn't needed then will simply return the Error Code Reference.

Might need to see if I should implement a global try, catch, finally process.

Extend Error Class

## Pending Firebase Crashlytics Implementation

This will need to be put on hold briefly until I can confirm how Crashlytics will need to be implemented.
