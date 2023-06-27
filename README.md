# Regex Tutorial

This is a tutorial walking through different parts of regular expressions or regex. With in this document there will be given an example expression, a walk through of its components, and summary of the expression.  

## Summary

Below is a regex that validates an email. 

```regex

/^\w+([\.-]?\w+)*@\w+([\.-]?\w+)*(\.\w{2,3})+$/gm

```
The above regex looks and matches different parts of an email. It can be used to validate emails on a website. I will be referencing this expression and 


## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components

### Anchors

Anchors start and end lines in a multiline-pattern. The  ^ character denotes that it should match at the beginning of a line. The $ denotes the that the pattern should be the end of a line. 

### Quantifiers

Quantifiers specify how many instances a character class must be present in the input for a match to occur. * operator  denotes zero or more to match, while the + operator requires one or mre to match. In the example expression  /^\w+([\.-]?\w+)*@\w+([\.-]?\w+)*(\.\w{2,3})+$/gm, the + operator after the \w signifies a match to any word the contains alphanumeric characters and the _ will match if one or more is present. Where /w{2,3} signifies that the word should be between 2-3 characters.

### OR Operator
    
The or operator | defines that a pattern could be one or another words to match. It is not in my chosen example, but I'll provide one below.

```regex
eat|ull

``` 
In the above example it will either match eat or ull. 

### Character Classes

Character Classes are groups of characters for which are used in queries. They are signified by characters between []. A range of characters can be signified by using a hyphen for example [A-Z] will match capitol letters from a-z. 

### Flags
    
Flags are parts of th end that specify the scope for which it will search for a match. In the above example the /gm are the flags. The g indicates a global search, while the m signifies that that it will match where the line ends.   

### Grouping and Capturing
    
Grouping and Capturing  for the grouping of characters to match. Grouping is signified by the (). In the above example it is used in the ([\.-]?\w+) section. This searches for a group with either a starting . or - and then includes any alphanumeric characters including _.

### Bracket Expressions

Bracket expressions are used to define a set or range of characters that can match a single character at a particular position within a string. They allow you to specify a list of characters from which the regex engine will match any single character. For example, gr[ae]y will match both gray and grey, but not graey. One can set a range as [A-Z] ot [0-9].  

### Greedy and Lazy Match

In Regex matching can be either greedy or lazy. By default, quantifiers in regular expressions are greedy, which means they try to match as much of the input as possible while still allowing the overall pattern to match. When a quantifier is greedy, it matches as many occurrences of the pattern as it can, consuming as many characters as possible. On the other hand, lazy (or non-greedy) matching reverses the default behavior of greedy matching. It causes the quantifier to match as little as possible while still allowing the overall pattern to match. To make a quantifier lazy, you simply append a question mark (?) to it. In the above example at ([\.-]?, shows an example of a lazy reading. This query specifies for a . or a = , but not repeated because it is lazy.


### Boundaries

Boundaries are used to define specific positions within a string where matches can occur. They allow you to specify conditions that restrict where a pattern can be found or provide anchor points for matching. Boundaries are not actual characters but rather positions within the string. The anchors ^ and $ were described in anchors. The other boundary notation /b is used to define "non-character-space" as part of the search. For example /bcat/b will match cat but no catastrophe. 

### Back-references

Back-references are used to refer to and match previously captured groups within the same regex pattern. This is accomplished with th nomenclature /n where n is a number 1-9. An example of this is 
b/(\w+)\s\1\b. This expression will search for a word repeated twice. This is accomplished by first setting the grouping (\w+) and then referencing it with the \1 with 1 referencing the first group. 

### Look-ahead and Look-behind

Look-ahead and Look-behind assertions are used to define conditions that must be met by the characters ahead or behind a particular position within a string. The look-ahead you use the ?= operator; to look behind you use the ?<= operator. In the below example;

```regex
q(?=u)
```
In this example the regex expression is looking for q followed by the letter u. 

## Author

Grant Ellington is currently attending the coding boot camp. Other interest include playing the saxophone and taking walks. YOu can find him on git hub at[https://github.com/Grant-Ellington](https://github.com/Grant-Ellington)