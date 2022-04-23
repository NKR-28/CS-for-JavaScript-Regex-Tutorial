Regex Tutorial
This is a tutorial highlighting the use of regular expressions to validate an email address.

Summary
A regular expression, regex for short, is a sequence of characters that defines a search pattern. Regular expressions are often used to validate user input by finding patterns of characters within a string.

For example, the following regex can be used to verify that a user has input a valid email address:

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

Although it may look like a random assortment of characters, every part of this regex has a specific responsibility. We will go over each aspect in the following sections of this tutorial.

If you would like to go to a specific section of this tutorial, you may click the corresponding link in the Table of Contents.

Table of Contents
Anchors
Grouping Constructs
Bracket Expressions
Quantifiers
Character Classes
Character Escapes
Author
Regex Components
A regex is a literal, therefore it must be contained within two forward slashes /.

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

Note the / found on each end of the regex in the example above.

Anchors
The characters ^ and $ are anchors.

The ^ anchor signifies the beginning of a string, and the $ anchor signifies the end of a string.

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

As you can see in the example above, the ^ anchor is the second character, right after the opening /, and the $ anchor is the second to last character, right before the closing /.

Grouping Constructs
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

If you look carefully at this regular expression, you might notice there are several sets of parentheses enclosing different groups of letters, numbers, and symbols. These parentheses are being used to create grouping constructs or subexpressions.

For example, the expression (abc):(def) contains two subexpressions, "abc" and "def", each grouped within a set of parentheses.

Unless told otherwise, grouping constructs look for exact matches. The expression (abc):(def) is meant to check if a string exactly matches “abc:def”. The string “bca:fde” would not be a match.

Take another look at our regex for matching an email.

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

You can see the three subexpressions within our regex delineate the three parts of an email address:

([a-z0-9_\.-]+)
This subexpression is matching the part of an email address that comes before the @ symbol.
([\da-z\.-]+)
This subexpression is matching the characters after the @ symbol and before the . in an email address.
([a-z\.]{2,6})
This subexpression is matching the characters after the . in an email address.
Bracket Expressions
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

You might have noticed there are also several sets of brackets enclosing different groups of letters, numbers, and symbols within the subexpressions of this regex. These brackets are being used to create bracket expressions.

Bracket expressions represent the range of characters beinged matched by a regular expression. Bracket expressions do not have to find an exact match, so the expression [xyz] would match “yyy”, “zyx”, “xyzxyzxyz”, and so on, as long as the string only includes the specified characters within the bracket expression.

The hyphens between the letters and numbers within a bracket expression represent the range held between those characters. For example [a-z] will match all lowercase letters in the alphabet. The bracket expression [a-zA-Z] will match all lowercase and uppercase letters.

Take another look at our regex for matching an email.

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

You can see the bracket expressions within our regex are:

[a-z0-9_\.-]
Matches lowercase letters, all numbers, underscores, periods, and hyphens (I'll explain the backslash in the Character Escapes section).
[\da-z\.-]
Matches digits (\d), lowercase letters, periods, and hyphens.
[a-z\.]
Matches lowercase letters and periods.
These bracket expressions are all positive character groups, meaning the characters listed are ones that will be matched. Any bracket expression can be made a negative character group by adding ^ to the beginning of the expression. For example, [^aeiouAEIOU] will exclude all matches with lowercase or uppercase vowels.

Quantifiers
Quantifiers set limits for the strings matched by a regex. There are several ways to indicate these limits:

* matches a pattern zero or more times
+ matches a pattern one or more times
? matches a pattern zero or one time
{}
{ n } matches exactly n times
{ n, } matches at least n times
{ n, x } matches at least n times and at most x times
? can be added after any of the above symbols for the regex to be matched in as few occurrences as possible
Take another look at the regex for matching an email:

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

The quantifiers found in this regex are:

+
This quantifier is found in the first two subexpressions of the regex, ([a-z0-9_\.-]+) and ([\da-z\.-]+).
This quantifier indicates at least one match must be found.
{2,6}
This quantifier is found in the third subexpression of the regex, ([a-z\.]{2,6}).
This indicates this part of the regex must match a string between 2 and 6 characters long.
Character Classes
A character class defines a set of characters and can work as a shortcut to simplify a bracket expression. Some examples of character classes include:

.
This class matches any character except for the newline character (\n).
\d
This class matches any Arabic numeral digit, which is the same as saying [0-9].
\w
This class matches any alphanumeric character from the basic Latin alphabet and underscores, which is the same as saying [A-Za-z0-9_].
\s
This class matches a single whitespace character.
Making any of these character classes a capital letter indicates an inverse match. For example, where \d matches digits, \D will match non digits.
Take another look at the regex for matching an email:

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

The character class found in this regex is:

\d
This character class is found in the second subexpression of the regex, ([\da-z\.-]+), and will match any digit 0-9.
Character Escapes
Certain characters have a special meaning within a regex, therefore they should be preceded by a backslash \ when indicating them literally.

These characters are:

+ * ? ^ $ \ . [ ] { } ( ) | /

Note: Within character sets it is only necessary to escape \, -, and ].

Take another look at the regex for matching an email:

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

The character escape used in this regex is \., which can be found four different times to indicate the literal character ..