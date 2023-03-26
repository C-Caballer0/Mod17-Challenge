# Regex's - Email Validation

Regex's are useful methods of validating user input to enusre compatibility with backend data structures. They provide great value in avoiding incomapibilites or errors in are code, and are fairly easy to implement and use for the value they provide.

## Summary

This file will overview trhe basics regarding email validation using regex, which are often used 
when validating users emails for the purpose of user accounts or profiles, which often use emails 
as identifires or in place of usernames. and example of a basic email validation regexs could look
like:

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

Important to note is that the regex will NOT validate that the data provided to it is, in fact, a valid email address, only that the provided data is in the correct format of an email address.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components

### Anchors

Anchors are characters used for bookmarking importan sections within the regex, used both by the 
computer and the programmer to help readability.

In the above example expression, we can see that the character `^` is used to indicate the beginning of a string, and the character `$` is used to indicate the end of a string.

### Quantifiers

Quantifiers are used to specify if and how many of a certain character is required for the data to be considered valid.

The `+` operator is included and is used so that multiple criteria must be met for the data to be valid. It also makes use of `{}`, in the example `{2,6}` which provides a matching range of 2-6 characters for the linked character set

### Grouping Constructs

Grouping constructs are used to check individual parts of the data independetly in addition to the whole data as a whole.

The example utilizes 3 capture groups, as follows:

- ([a-z0-9_\.-]+) which will validate the users email username section 
- ([\da-z\.-]+) which will validate the email provider section
- ([a-z\.]{2,6}) which will check for a valid domain code (between 2 and 6 characters)

### Bracket Expressions

Bracket expression are expression that validate the values of characters within the provided data.

In the example, there are 3 different bracket expressions, as follows:

- [a-z0-9_\.-] which will allow any lowercase letter, any number, and the characters `_`, `-`, and `.`
- [\da-z\.-] which will alow any single digit
- [a-z\.] which allows any lowercase letter

### Character Classes

Character classes identify certain classes of commonly used characters for convenience.

In our example expression, the only charcter class used is \d, which is used to validate for a single digit (`2` = valid, `25` = invalid) from 0-9 (any other character = invalid).

### The OR Operator

OR operators are used when various different formats of data may all be considered valid and the regex must accept all of them.

The OR Operator is denoted by `|` in code, however, our provided example does not provide any examples.

### Flags

Flags are parameters used to control how the regex evaluates the data provided to it, such as ignoring case status for alphabetical characters or continuing a regex expression on a new line.

Our example does not include any flags.

### Character Escapes

Character escapes are characters that are excepted from normal character validation. Denoted by a `\`, they are often used with characters suech as `.`, `-`, `=`, where without these character escapes, the characters may influence the rest of the regex and cause it to behave abnormally. 

We seee one example of this between the second and third bracket expressions:

([\da-z\.-]+)\.([a-z\.]{2,6})

the `\` before the `.` allows the `.` to be placed their without causing problems with either of the neighbouring expressions.

## Author

Written by Carlo Caballero, an aspiring web developer. His profile can be found at https://github.com/C-Caballer0
