# Title: Regex Tutorial

Regular expressions or more commonly refer to as regex or regexp are special strings representing a pattern to be used in a search operation. Basically, they are expressions or blocks of codes that can be used in various computing applications. One good example is using a regular expresison for Emails as this can be used to not only create but also check if email is properly created. In this gist, we will take apart a regular expression used in javascript and the componnents that make up the expression.

## Summary

A Regex or regular expression is a sequence of characters that define a search pattern. Usually such patterns are used by string-searching algorithms for "find" or "find and replace" operations on strings. It also looks for input validations. It is a technique commonly developed in theoretical computer science.

We will look a a string of code using regex, this code looks for a match HTML tag.

Example: /^<([a-z]+)([^<]+)*(?:>(.*)<\/\1>|\s+\/>)$/

The below content will explain what each section of this code does and more.

## Table of Contents

- [Title: Regex Tutorial](#title-regex-tutorial)
  - [Summary](#summary)
  - [Table of Contents](#table-of-contents)
  - [Regex Components](#regex-components)
    - [Anchors](#anchors)
    - [Quantifiers](#quantifiers)
    - [Grouping and Capturing](#grouping-and-capturing)
    - [Bracket Expressions](#bracket-expressions)
    - [Character Classes](#character-classes)
    - [The OR Operator](#the-or-operator)
    - [Flags](#flags)
    - [Character Escapes](#character-escapes)
  - [Author](#author)

## Regex Components

### Anchors

^abc$ -^start / $end of the string

^ Matches the beginning of the string, or the beginning of a line if the multiline flag (m) is enabled.This matches a position, not a character.
$ Matches the end of the string, or the end of a line if the multiline flag (m) is enabled. This matches a position, not a character.
\b\B -word, not-word boundary

\b Matches a word boundary position between a word character and non-word character or position (start / end of string). See the word character class (w) for more info.
\B Matches any position that is not a word boundary. This matches a position, not a character.
See Boundaries for more detailed Information

### Quantifiers

Similar to the anchors and boundaries but used in a different way, quanitifiers allow t he user to use quanitities as a way to find patterns. For example if one wants to have a certain character to string to appear in a certain pattern, quantifiers can be used. For more visual example:

`character\{m\}` = three characters get printed out
`character\{m,n\}` = the pattern starts at m and increases until it reaches n

There are many more of quantifiers.

### Grouping and Capturing

When working in JavaScript or other lanaguages, there are various categories of data such as characters, operators and constructs that can be used to define regular expressions. However, it can be a bit confusing at times. Thus we use Grouping constructs. These constructs allow the user to describe basically take apart normal regular expressions and be used to match and catch substrings of a said string. For example:

`( subexpression ) = (\w)\1 = "ee" in "deep"`


### Bracket Expressions

Brackets, [], can be use to indicate a set of characters, whether it be a full string or a single character, that can be used to match and search for that specific character or string. Any character or string placed in the bracket is then matched. For example:

`elephant.match(/[abcd]/)` = matches a

How about you want a certain number of things to be matched? We use curly brackets, {}, for that. Any number placed in the brackets and the exact amount is searched. For example:

`'banana'.match(/na{2}/)` = matches 'nana' since there is to 'na'

### Character Classes

\d is present in the given matching email code and what it will match a single letter character, a-z, after the @ sign in the email address. Basically ensuring that a letter is matched after the @ in the email and not a number or special character.

### The OR Operator

When building an operator that uses logic, more than likely one will run into logics based on the concept of or. In javaescript. using or can tell the operator to perform one function or the other or some other operation based on the condition. The most common regular expression for the "or" Operator is ||. In fact one can add as many choices as long as they utilize the | expression. For example:

`"I like (dogs|penguins) but not (lions|tigers).`

^The above results can match any of the following:
I like dogs, but not lions.
I like dogs, but not tigers.
I like penguins, but not lions.
I like penguins, but not tigers.

### Flags

A regex flag is not used in the matching email code that is being used for this tutorial. A regular expression typically comes in the form:

/regex/

Where the slashes denote where the regular expresssion starts and ends. A flag can be used after the slash to give more guidelines for our matching. The flags are:

g which stands for "global" which will allow for matching all the instances within a string that follow the matching guidelines set in the regular expression.
m which stands for "multiline" which will search line by line rather than searching through a string as a whole.
i which stands for "insensitive" will make the regular expression case-insensitive, so capitals and lower-case letters will not deture the matching.

### Character Escapes

In Javascript and computation in general, an escape character is a character that invokes an alternative interpretation on the following characters in a character sequence. What  this means is a character that is attached to following sequence of characters, the sequence can be seen in a different way. An escape character is a particular case of metacharacters. Generally, the judgement of whether something is an escape character or not depends on the context of the code that follows it.

In regex, the "\" character is the expression that denotes a specific character is a escaped character. For example:

`\d` => matches any digit
`\D` => matches any non-digit
`\f` => matches a form feed

## Author

Author: Nita Roberts

Github Account: https://github.com/NKR-28