# Regex Tutorial

Regex is short for regular expression, which is sequence of characters that searches for matching values/patterns within a string.

## Summary

This tutorial will describe how a regex (regular expression) is used to confirm that the information entered is an email. This can be useful when validating emails in applications/technologies. For example, if a user is filling out a form online or utilizing a technology that requires email information, this regex could be used to make sure they enter an email address when asked for one. Essentially, the regex is defining a search pattern.
Matching an email uses the expression shown here:
`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`
In this regex, each component has a specific responsibility to make sure or verify that the user enters an email address in the correct format which in this case begins with characters followed by @ symbol and then the domain.

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

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`
Slashes /.../ means we are creating a regex using a regex literal which consists of a pattern enclosed between slashes, it has the same role as quotes for strings.
The most common pattern of an e-mail address is composed of 4 main groups :
String of characters and/or digits and/or dots, hyphens and/or underscores
The at symbol `@`
A domain name that can be a string of characters and/or digits
The domain name is preceeded by a dot `.`


### Anchors

Anchors match a position before, after, or between characters. The caret, `^` matches the position before the first character in the string and the dollar symbol `$` matches after the last character of the string. So, as in the snippet above, the `^` and `$` basically contain the parameters of the regex.


### Quantifiers

Quantifiers specify how many instances of a character, group, or character class must be present for a match to be found. In a regex that is meant to match an email address, you would want to use the plus sign `+` operator. The `+` on it's own will match as many occurances as possible. In `[a-z0-9_\.-]+@` from our email matching regex, the expression will look for at least one or more instances of everything within the brackets: "lowercase a through z" and/or "zero through nine", a dot, and a dash. After the `+` is the `@` so it will stop this part of the search once it gets to the `@`.

The `{2,6}` at the end will looks for a range of 2-6 characters. Which works for an email address because they end in something like .com or .net which is between 2 and 6 characters long.


### Grouping Constructs

Parentheses `()` are used to group parts of the expression together. In `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/` the username is grouped, then the provider name is grouped, but between them is an `@`symbol so nothing affecting those groups affects the `@` symbol and the regex will just look for a single `@` character between those two groups.


### Bracket Expressions

Brackets '[]` allow a regex to match specific characters in a range. Therefore `[a-z]` is not looking for a or - or z, but actually looking for any letters a through z. Just as, within the brackets, the `-` is not taken literally in the cases of a-z or 0-9. 


### Character Classes

The `\d` used in the email matching regex is looking for any single digit. Since it is wrapped in brackets followed by the `+` sign, it can be one or more digits. If it was just on its own, it would only allow a single digit, or something like `\d\d\d` that would mean only three digits.


### The OR Operator

An OR character `|` is not present in the regex for matching an email. However it is used to match one of multiple patterns such as this OR that. Example, `hi|hello` is a string that refers to  either hi or hello.

### Flags

The `/` is used to delimit the expression. And would come before the caret and after the dollar sign. After the closing `/` `g` = global search, `i` = case sensitive search, `m` = multi-line search, are some flags that may be used.


### Character Escapes

The `\` before the dot `.` “escapes” this character indicating that the dot is not a regex special character. The dot is then recognized as a literal `.` when placed after the `\`.


## Author

Nicole Lucena
(https://github.com/nolimarie)

