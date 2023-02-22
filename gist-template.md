# Title Here (replace with your title)

Intro to regex..

## Summary

Briefly summarize the regex you will be describing and what you will explain. Include a code snippet of the regex. Replace this text with your summary.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)
- [Author](#author)

### Regex Components

### Anchors
Anchors are a different breed. They do not match any character at all. Instead, they match a position before, after, or between characters. They can be used to “anchor” the regex match at a certain position. The caret ^ matches the position before the first character in the string. Applying ^a to abc matches a. ^b does not match abc at all, because the b cannot be matched right after the start of the string, matched by ^. See below for the inside view of the regex engine.

When using regular expressions in a programming language to validate user input, using anchors is very important. If you use the code if ($input =~ m/\d+/) in a Perl script to see if the user entered an integer number, it will accept the input even if the user entered qsdf4ghjk, because \d+ matches the 4. The correct regex to use is ^\d+$. Because “start of string” must be matched before the match of \d+, and “end of string” must be matched right after it, the entire string must consist of digits for ^\d+$ to be able to match.
### Quantifiers

### Grouping Constructs
By placing part of a regular expression inside round brackets or parentheses, you can group that part of the regular expression together. This allows you to apply a quantifier to the entire group or to restrict alternation to part of the regex.

Only parentheses can be used for grouping. Square brackets define a character class, and curly braces are used by a quantifier with specific limits.
Besides grouping part of a regular expression together, parentheses also create a numbered capturing group. It stores the part of the string matched by the part of the regular expression inside the parentheses.

The regex Set(Value)? matches Set or SetValue. In the first case, the first (and only) capturing group remains empty. In the second case, the first capturing group matches Value.
### Bracket Expressions

### Character Classes
With a “character class”, also called “character set”, you can tell the regex engine to match only one out of several characters. Simply place the characters you want to match between square brackets. If you want to match an a or an e, use [ae]. You could use this in gr[ae]y to match either gray or grey. Very useful if you do not know whether the document you are searching through is written in American or British English.

A character class matches only a single character. gr[ae]y does not match graay, graey or any such thing. The order of the characters inside a character class does not matter. The results are identical.

You can use a hyphen inside a character class to specify a range of characters. [0-9] matches a single digit between 0 and 9. You can use more than one range. [0-9a-fA-F] matches a single hexadecimal digit, case insensitively. You can combine ranges and single characters. [0-9a-fxA-FX] matches a hexadecimal digit or the letter X. Again, the order of the characters and the ranges does not matter.

Character classes are one of the most commonly used features of regular expressions. You can find a word, even if it is misspelled, such as sep[ae]r[ae]te or li[cs]en[cs]e. You can find an identifier in a programming language with [A-Za-z_][A-Za-z_0-9]*. You can find a C-style hexadecimal number with 0[xX][A-Fa-f0-9]+.
### The OR Operator
<!-- alternation -->
The alternation operator has the lowest precedence of all regex operators. That is, it tells the regex engine to match either everything to the left of the vertical bar, or everything to the right of the vertical bar. If you want to limit the reach of the alternation, you need to use parentheses for grouping. If we want to improve the first example to match whole words only, we would need to use \b(cat|dog)\b. This tells the regex engine to find a word boundary, then either cat or dog, and then another word boundary. If we had omitted the parentheses then the regex engine would have searched for a word boundary followed by cat, or, dog followed by a word boundary.
### Flags
<!-- g and m -->
Regular expressions have optional flags that allow for functionality like global searching and case-insensitive searching. These flags can be used separately or together in any order, and are included as part of the regular expression.
|Flag|Description|Corresponding Property|
|:---|:---------------------|----------:|
|d|Generate indices for substring matches.|hasIndices|
|g|Global search.|global|
|i|Case-insensitive search.|ignoreCase|
|m|Allows ^ and $ to match newline characters.|multiline|
|s|Allows . to match newline characters.|dotAll|
|u|"Unicode"; treat a pattern as a sequence of Unicode code points.|unicode|
|y||Perform a "sticky" search that matches starting at the current position in the target string.|sticky|

### Character Escapes
<!-- there no character escapes -->

### Author
Adem Sahil, junior Web Devoloper. You can review my profile [Here!](https://github.com/ademsahil274).
