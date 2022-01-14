Guide to Regular Expressions(Regex)

Regular Expressions are a string of characters that express a search pattern. Often abbreviated as RegEx or RegExp. It is especially used to find or replace words in texts. In addition, we can test whether a text complies with the rules we set.

For example, let's say you have a list of filenames. And you only want to find files with the pdf extension. Following typing an expression ^\w+\.pdf$ will work. The meaning of the definitions in this expression will become clearer as the steps progress.

## Summary

The URL matching regex ```/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/ ``` is used and below we will break down it down and 

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
Anchors of regualr expressions are the `^` and `$` symbols either at the beggining or end of a string. 
Defining `^` & `$`: 

`^` - this symbol is known as the "carrot" and is at the begining of the sequence.

`$` - this symbol is known as the "dollar" and is at the end of the seqence. 

The action that take place between these two symbols is what matches the URL dependent on the restrictions inside the `^` and `$`.


### Quantifiers
Quantifiers of regular expressions match a number of instances of charcter(s), groups pr chracter class in a string. 
List of Quantifers: 

`{1,3}` - this quantifier expreses instances that have a certain range between 1 and 3.

`*` - this symbol known as the "asterik" matches NONE or all times.

`+` - this symbol known as the "plus" to indicate that a character can occur one or more times.

`?` - this symbol known as the "question mark" means ZERO or one instance to  indicate that a character is optional. 


`|` -  this symbol known as the "pipe character" to match a single regualr expresion out of several possible regualar expressions.

For Example in the URL give above we will now break it down in sequence: 

`https?` - will MATCH `https`

`[\da-z\.-]+` - will MATCH a single digit (`d`), group of letters from `a-z`, or (`.`), literal hypen `-`, one or more times `+`

`[a-z\.]{2,6}` - will MATCH a group of letters from  `a-z`, or `.`, and matches the pattern form a minimum of 2 to a maximun of 6 times(`{2,6}`).

`[\/\w \.-]*` - will MACTH the the literal forward slash (`/`) by first escape (`\`), then any alphanumeric character including any underlines by (`\w`), escpae (`\`) to record literal `.` and `-`, lastly (`*`) to select each word .

### Grouping Constructs
Grouping Constructs allows to group an expression and use these groups to reference or enforce some rules. 
How to Group: 
To group an expression, we enclose it in parentheses(`()`). 

`(https?:\/\/)`- will MATCH `htttps://` or `http://`

`([\da-z\.-]+)` - will MATCH  a single digit (`d`), group of letters from  `a-z`, or (`.`), literal hypen `-`, one or more times `+`

`([a-z\.]{2,6})`  - will MATCH letters through `a-z` or (`.`) and matches the pattern form a minimum of 2 to a maximun of 6 times(`{2,6}`). 

`([\/\w \.-]*)` - will MATCH `/`, a series of letters including underline `\w`, and `.` followed by literal hypen `-`, lastly (`*`) to select each word


### Bracket Expressions
Bracket Expressions are anything isnde a set of square brackets that reprents a range of chracters that we want to match, also known as postive character group. (`[]`)
For example: 

`[\da-z\.-]`

`[a-z\.]`

`[\/\w \.-]`

### Character Classes
Chracter Classes define a set of chracters, any one of which can occur in an input string to fulfill a match.
For Example: 

`[abc]` - will  MACTH any character in the set

`[^abc]` - will NOT MATCH any character in the set 

`[a-z]` - will MATCH ALL chratcers between two chracters, including themselves

`.` - will MATCH any character except line breaks

`\w` - will MATCH any alphanumeric chracter including underline (`_`)

`\W` - will NOT MATCH any alphanumeric chracter including underline (`_`)

`\d` - will MATCH any numeric charatcer 

`\D` - will NOT MATCH any numeric charatcer 

`\s` - will MATCH any whitespace character 

`\S` - will NOT MATCH any whitespace 

### The OR Operator
OR operator (`|`) also known was the "Pipe Character" allows to specify that an expression can be in different expressions. All possible statements are wirtten seperated by the pipe sign (`|`). 

For Example: 
`(abc):(xyz)` matches `(a|b|c):(x|y|z)` but does NOT match `"xyz:abc"` does not 

### Flags
Flags alter the output of a given expresion. Flags are also known as modifiers. They determine if the typed expression text is treated as seperate lines, is case sensitiv, or finds all matches. 

For Example: 

`/g` - causes the expression to select all matches (global)

`/m` - to handle each line speatatley. RegEx sees all text as one line. (mulitline)

`/i` - will remove the case-sensitiveness of the expression we have written (case insensitive)

### Character Escapes
Character Escapes are used buy doing a backslash (`\`). The backslash in regex allows for sleceting the special chratcters. 
For example:

`\/\/` - will match  `//`

Author
Chanwoo Hwang 
https://github.com/Adipure