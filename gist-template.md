# Title: A Beginner's Guide to Regular Expressions

This tutorial aims to understand Regular Expressions (Regex) and their applications comprehensively. Regex is a powerful tool in various programming languages for pattern matching and data validation. This tutorial will explain the fundamentals of Regex and demonstrate its usage through detailed examples.

We will focus on a specific Regex pattern, summarizing its functionality and practical examples to help you understand how to apply it in your code. By the end of this tutorial, you will have a solid understanding of Regex and be equipped to use it in your programming projects.

## Summary
Regular Expressions, commonly called "Regex," is a powerful tool that allows you to define specific search patterns using a sequence of characters. With Regex, you can effortlessly search for and extract specific patterns of characters from a given string. However, its most common application is input validation, which helps ensure that user input meets particular criteria.

For instance, consider the following example Regex provided below.
```/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/```

This is a regular expression pattern that matches an email address. Here's what each part of the pattern means:

^: Matches the start of the string.
([a-z0-9_.-]+): Matches one or more characters that are either lowercase letters, digits, underscores, periods, or hyphens. This is the username part of the email address.
@: Matches the "@" symbol that separates the username from the domain name.
([\da-z.-]+): Matches one or more characters that are either digits, lowercase letters, periods, or hyphens. This is the domain name (excluding the top-level domain) part of the email address.
.: Matches a period character.
([a-z.]{2,6}): Matches between 2 to 6 characters with lowercase letters or periods. This is the top-level domain part of the email address (e.g., com, org, net).
When combined, this regular expression pattern matches an email address in the format of "username@domain.tld".

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
In regular expressions, an anchor is a unique character matching a specific position within the searched string. There are two main types of anchors:

Start of string anchor (^): This anchor matches the beginning of the searched string. It is often used to ensure that a pattern only matches at the beginning of the string.
For example, the regular expression pattern /^hello/ would only match strings that start with the word "hello".

End of string anchor ($): This anchor matches the end of the searched string. It is often used to ensure that a pattern only matches at the end of the string.
For example, the regular expression pattern /world$/ would only match strings that end with the word "world".

Both anchors can be used together to ensure that a pattern matches the entire string from start to finish. For example, the regular expression pattern /^hello world$/ would only match strings containing the exact phrase "hello world", with no other characters before or after.

### Quantifiers
Quantifiers are special characters in regular expressions that specify how often a character or group of characters should be matched. In the example regular expression "^([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})$", the following quantifiers are used:

"+" quantifier: Matches the preceding character or group of characters one or more times. For example, the expression "[a-z]+" matches one or more lowercase letters.

"{2,6}" quantifier: Matches the preceding character or group of characters between 2 and 6 times. For example, the expression "[a-z]{2,6}" matches between 2 and 6 lowercase letters.

These quantifiers help to make regular expressions more flexible and powerful by allowing for more complex patterns to be matched.


### Grouping Constructs
In the regular expression ```^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$```, the parentheses (( and )) are used as a grouping construct.

Grouping constructs are used to group parts of a regular expression, allowing you to apply a modifier or quantifier to the entire group instead of just a single character. In this case, we have three groups separated by parentheses:

```([a-z0-9_\.-]+)```: Matches one or more lowercase letters, digits, underscores, dots, or hyphens, capturing the match into the first group.

```([\da-z\.-]+)```: Matches one or more digits, lowercase letters, dots, or hyphens, capturing the match into the second group.

```([a-z\.]{2,6})```: Matches two to six lowercase letters or dots, capturing the match into the third group.

These groups allow us to extract specific parts of the email address matched by the regular expression. For example, we can access the username portion of the email address by referencing the first group or the domain portion by referencing the second and third groups combined.

### Bracket Expressions
Bracket expressions in regular expressions match a set of characters within a single position in the string. In the given regular expression, the square brackets are used to define sets of allowed characters for each email address section.

For example, [a-z0-9_\.-] matches any lowercase letter, digit, underscore, period, or hyphen. [\da-z\.-] matches any digit, lowercase letter, period, or hyphen. And [a-z\.]{2,6} matches any lowercase letter or period, with a minimum of 2 and a maximum of 6 repetitions.

### Character Classes
In regular expressions, character classes match specific sets of characters. They are denoted by enclosing a set of characters inside square brackets []. For example, [a-z] matches any lowercase letter, [0-9] matches any digit, and [\da-z] matches any digit or lowercase letter.

The given regular expression is a pattern for matching email addresses. It consists of three character classes:

[a-z0-9_.-]+ matches one or more lowercase letters, digits, underscores, dots, or hyphens in the username portion of the email address.
[\da-z.-]+ matches one or more digits, lowercase letters, dots, or hyphens in the domain name portion of the email address.
[a-z.]{2,6} matches two to six lowercase letters or dots in the top-level domain portion of the email address.

### The OR Operator
The characters represent the OR operator | and [], matching the characters within the tokens. For example, the regular expression /^([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})$/ uses the OR operator to match specific tokens within the email address pattern.

### Flags
Flags are special characters that can be added to regular expressions to modify their behaviour. In the regular expression, you provided, "/^([a-z0-9_.-]+)@([\da-z.-]+).([a-z.]{2,6})$/" is a regular expression pattern that matches an email address.

The flags in this regular expression are:

"^" - This is a start anchor that indicates the start of the string.
"$" - This is an end anchor that indicates the end of the string.
"+" - This quantifier matches one or more occurrences of the preceding character or group.
"@" is a literal character that matches the "@" symbol.
"[]" - This character set matches any character within the brackets.
"." - This special character matches any character except for newline characters.
"\d" - This is a shorthand character class that matches any digit (equivalent to [0-9]).
"{n,m}" - This quantifier matches between n and m occurrences of the preceding character or group.
"" - This escape character allows special characters to be matched literally.
These flags define the specific pattern for an email address that should be matched. The "^" and "$" anchors ensure that the pattern matches the entire string, while the character sets and quantifiers ensure that the pattern matches the correct characters in the correct order.

### Character Escapes
Character escapes are special sequences of characters used to represent a character with a special meaning in a programming language or regular expression syntax. In the given regular expression, "\d" is a character escape that matches any digit from 0 to 9. Similarly, "." matches a period (.) character, which would otherwise be interpreted as a special character in regular expression syntax.

## Author
Hamze Mohamed is a skilled programmer and is currently attending a Coding Boot Camp at Toronto University. Hamze is passionate about developing software solutions and contributing to the programming community. To learn more about Hamze and his work, visit his GitHub profile: 
- [Github](https://gist.github.com/mhamze23/)
