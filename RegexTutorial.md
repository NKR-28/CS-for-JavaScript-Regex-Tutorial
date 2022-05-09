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
    - [Grouping Constructs](#grouping-constructs)
    - [Bracket Expressions](#bracket-expressions)
    - [Character Classes](#character-classes)
    - [The OR Operator](#the-or-operator)
    - [Flags](#flags)
    - [Character Escapes](#character-escapes)
  - [Author](#author)

## Regex Components

### Anchors

Anchors and, oftenly associated with it, boundaries allows the user to describe or find a term based on locations. For example, finding certain words that are the first or last on a line. Some examples:

^ = start of the string
$ = end of the string
\< = the start of the word

...and many more. The summary is that these anchors and boundaries affiliate with terms and the location they are located.

### Quantifiers

Similar to the anchors and boundaries but used in a different way, quanitifiers allow t he user to use quanitities as a way to find patterns. For example if one wants to have a certain character to string to appear in a certain pattern, quantifiers can be used. For more visual example:

`character\{m\}` = three characters get printed out
`character\{m,n\}` = the pattern starts at m and increases until it reaches n

There are many more of quantifiers.

### Grouping Constructs

When working in javacript or other lanaguages, there are various categories of data such as characters, operators and constructs that can be used to define regular expressions. However, it can be a bit confusing at times. Thus we use Grouping constructs. These constructs allow the user to describe basically take apart normal regular expressions and be used to match and catch substrings of a said string. For example:

`( subexpression ) = (\w)\1 = "ee" in "deep"`


### Bracket Expressions

Brackets, [], can be use to indicate a set of characters, whether it be a full string or a single character, that can be used to match and search for that specific character or string. Any character or string placed in the bracket is then matched. For example:

`elephant.match(/[abcd]/)` = matches a

How about you want a certain number of things to be matched? We use curly brackets, {}, for that. Any number placed in the brackets and the exact amount is searched. For example:

`'banana'.match(/na{2}/)` = matches 'nana' since there is to 'na'

### Character Classes

Character classes or character sets us a special notation that allows the user to match any symbol or character from a certain set.

### The OR Operator

When building an operator that uses logic, more than likely one will run into logics based on the concept of or. In javaescript. using or can tell the operator to perform one function or the other or some other operation based on the condition. The most common regular expression for the "or" Operator is ||. In fact one can add as many choices as long as they utilize the | expression. For example:

`"I like (dogs|penguins) but not (lions|tigers).`

^The above results can match any of the following:
I like dogs, but not lions.
I like dogs, but not tigers.
I like penguins, but not lions.
I like penguins, but not tigers.

### Flags

Flags, in a regular expression, are tokens that modify its behavior of searching. Basically, flags are a form of optional parameters that users can use in addition to plain expression to make it search in a different way. Each flag is denoted by a single alphabetic character, and serves different purposes in modifying the expression's searching behaviour. For exampole:

The flag 'i' ignores casing, which ignores any case-sensitive
`/hello/i` ==> ignores all case-sensitives

the flag 'g' stands for global, it makes the expression look for all its matches instead of stoppin gat the first one.
example string "cats love cats'
`/cats/` only matches the first 'cats'
`/cats/g` matches all 'cats'

### Character Escapes

In Javascript and computation in general, an escape character is a character that invokes an alternative interpretation on the following characters in a character sequence. What  this means is a character that is attached to following sequence of characters, the sequence can be seen in a different way. An escape character is a particular case of metacharacters. Generally, the judgement of whether something is an escape character or not depends on the context of the code that follows it.

In regex, the "\" character is the expression that denotes a specific character is a escaped character. For example:

`\d` => matches any digit
`\D` => matches any non-digit
`\f` => matches a form feed

## Author

Author: Nita Roberts

Github Account: https://github.com/NKR-28