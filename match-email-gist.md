# Bees Regex : Matching Email Tutorial

Come check out my tutorial on matching email regex style.

## Summary

Regex is a fancy term for regular expression. It is a way to search for patterns and return the information you are looking for. You tell the computer what type information or specify a pattern you are looking for. The result will be anything that matches the regex string you created.

I will explain how the regex expression below will return an email address :
````````````````````````

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

````````````````````````
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

- Anchors help by specifying where the expression starts or ends as well as what is between start and end.
  - `^` - can be referred to as hat or caret marks the start of the expression
  - `$` - marks the end of the expression
  
  `````
  It is freezing in North Carolina
  `````
  using regex `/^\w+/`
  
  would match the word `It` because the regex expression starts with a hat `^` which searches for the first word in a string.
  
  `````
  /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
  
  ```````
  As you can see in our email regex above it starts with a hat ^ and ends with a $. This is telling us that what we are searching for is confined between these expressions, hence anchor!


### Quantifiers

- Quantifiers are used to find a pattern and then specify what comes after that pattern.
  `*` - stands for 0 or consecutive more of the same
  `+` - stands for 1 or consecutive more of the same
  `?` - matches the character you specified or nothing
  
   ``````
  
  Every one is getting a pool.
  
  ``````
  using regex `poo?l`
  
  would match `po` and `o` and `o` `l`  
  
  ``````````
  bb cc ca c
  
  using regex `ca?`
  
  would match `cc` `c` `a` `c` 
  
  side note - `?` is a greedy regex meaning it will return every instance that matches.
  
  ````````
  
  /^([a-z0-9_\.-]+)@(
  
  ```````
  
  from our email address we can see the `+` quantifier has been used. 
  
  In this instance, `+)@(` is telling us following the initial pattern is an `@` sign followed by another pattern. Basically, it marks where the @ is located in the string and returns those matches.

### OR Operator

- Operators searches for alternates
  `|`- searches for a string that has a this or that and captures it 
  `[]` - searches for a string that has either/or
  
  ```````````
  This is the best time of the year!
  ```````````
  
  using regex `t|h` would match `Th` in This.
  using `[th]` would match `Th` in this, `th` in the, `t` in best, etc. Remember, [] means we are looking for th, t, or h!
  
  ```````
  /^([a-z0-9_\.-]+)@([\da-z\.-]
  ````````
  
  Using our email address example, we can see the operator []. In this expression it means we are searching for unspecified information grouped together followed by the @ symbol followed by another group of unspecified characters.

### Character Classes
- Character Classes look for specifics unless specified otherwise. I'll explain below.
  `\d` - searches for a single digit
  `\w` - matches a word character - get it? w for word? d for digit? Easy-peesey. 
  `\s` - matches whitespace - a space or tab would do the trick!
  `.` - careful with this one - it matches any thing! Think of it as a wild card. 
  
  `````
  2 plus four equals 6
  ```````
  using `\d` would match `2` and `6`
  using `\w` would match everthing - `2` `plus` `four` `equals` `6`. If we added an explanation mark at the end of the string - the explanatation mark would not match because it is not a letter, digit or underscore.
  
  ```````
  using our email address example : random email - britt01@email.com
  ````````
  using `\d` would match 19
  using '\w` would match `britt` `01` `email` `com`
  
### Flags
- Flags are used to tell the search what to do after it has found a match.
  `g` - finds a match and then continues looking for matches after that one until no more are found
  `i` - is case insenstive - meaning it will search for a capital `A` and a lower case one `a`.

### Grouping and Capturing
- Exactly like it sounds when searching it will capture groups
  `()` - captures part of a group with that specific pairing for an ID
  `?:` - allows you to add quantifiers to the search and matches everything enclosed 
  
  An email address is separated into 3 groups : 
  `([a-z0-9_\.-]+)` is group one capturing a username
  `([\da-z\.-]+)` capturing the email service
  and `([a-z\.]{2,6})` capturing the `.com`

### Bracket Expressions
- searches for character sets
  look at the examples of bracket expressions being used in an email address below
  `[a-z0-9_\.-]` is searching for a set that matches any letter a-z, any digits 0-9, including "_", "-", is case-sensitive, and has a ".".
  `[\da-z\.-]` is matching a single digit from 0-9, any character a-z (case senstive), and the characters "." and "-".; 
  `[a-z\.]` matches any character a-z(case senstive) and the character "."
  
#### Sites Used
- https://regex101.com
- https://youtu.be/7DG3kCDx53c
- https://medium.com/factory-mind/regex-tutorial-a-simple-cheatsheet-by-examples-649dc1c3f285

#### Author

To anyone who finds this Gist - nice to e-meet you! Brittany here. I've always been a stickler for details and up for a challenge so when the opportunity to change careers arose - I jumped all in. Coming to a close soon on my coding bootcamp I can confidently say I know I made the right decision. Hopefully, by the time you read this I've gotten my feet wet in the wide world of Coding. I hope you enjoy my tutorial. For more from me check out, [GitHub Link](https://github.com/bdiaz28).