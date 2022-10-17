# Regex: Filter Through these Strings 

Introductory paragraph (replace this with your text)

## Summary

Regular expression, or regex, is a character pattern that matches strings or pieces of a string. Programmers equipt regexes for a variety of reasons. They can be used to validate text that matches a specified pattern. They can be used to search a text to see if any part of the text matches a specified pattern. Lastly, regexes can be used to replace sections of text with other text. Ultimately regexes help programmers efficiently sort through text for speedy validation, examination and replacement. Regexes can utilize quantifiers, or/and operators, and particular character classes. 


What do regexes look like? Well let’s examine one example: 

```a(b|c) ```

In this regex, the or operator is used ( | ). Let’s translate these characters: 

The a, is outside of the parenthesis, which capture both a b and a c separated by a vertical bar. This means that the regex is matching any string that has an a, and is followed by a b or c. 


Let's try a more complicated example. 


``` (\W|^)[\w.\-]{0,25}@(yahoo|hotmail|gmail)\.com(\W|$) ```

In this example, the regex searches for emails from three different sites, yahoo, hotmail and gmail. 

The ``` \\W ``` at the beginning filters for any character that doesn’t fit in typical email configurations (anything that isn’t a number, letter or underscore). 

This is followed by a vertical line and a ^ symbol. This symbol searches for any email address that starts at a new line with no characters before it. 

``` [\w.\-] ``` searches for any characters that are email compatible (letters, numbers, underscores, periods and hyphens).


``` {0, 25} ``` represents 0 to 25 characters that exist before the @ symbol.  


Here is a visual of how regexes could be viewed like a water filter, grabbing what fits, and leaving behind what doesn't: 

![Untitled_Artwork 6](https://user-images.githubusercontent.com/105015206/196262002-d8e39c00-b2bc-41ac-b72a-4c5398747c30.png)



## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components

### Anchors
In comparison to other regex tokens, anchors do not search for any specific characters, but instead filter for position. 

For example: 

The caret anchor ( ^ ) matches for the beginning of text 

The dollar achor ($) matches for the end of the text. 


Let’s see this in action: 


const brks = ‘Brookson’; 
console.log(/^B/.test(str));

The output of this example would be true, as it is testing for whether the beginning of the string starts with the letter B. The output would be false if the string didn’t start with a B, or if the regex was checking if there was a different letter at the beginning of the string. 

Let’s see the dollar anchor in action: 

``` const brks = ‘Brookson’; ```

``` console.log(/n$/.test(str)); ```

This output would also be true, as it is testing for whether the beginning of the string ends with the letter n. 


You can use both dollar and caret anchors in a single line. 


To enable multiline anchors, you have to use the m flag at the end (ex: /^\d/tm;)

### Quantifiers
Quantifiers determine how many times a character or a group of characters must be tracked in order for the string to be recognized. 


These quantifiers are split into two categories: greedy and lazy. 

Default quantifiers are greedy. These quantifiers are greedy as they are filtering every possible match. Adding a ? mark to a quantifier will make it lazy, and cause for the search to match as few correlating strings as possible. 

Here are some examples of quantifiers 

* start (*) → Matches 0+ times 
* question mark (?) → Matches 0 or 1 time 
* plus (+) → Matches 1+ times
* { x } → Matches x times 
* { x, } → Matches at least x times 
* { x, y } → Matches from x to y times 

### OR Operator
A vertical line | , serves as an or operator. 

For instance ``` a(b|c) ``` matches instances where a is followed by b or a is followed by c. 
### Character Classes

Character classes refer to specific types of characters. For example, you can differentiate between letters and numbers. 

In practice, one common use is /d which matches any number 0-9. 

### Flags

Flags can also impact what additional restrictions can be placed.

In JavaScript there are 6 types of flags: 

* i : will ensure that the search is not case sensitive (finding no difference between a and A)
* g : will search for all matches (vs the default of only returning the first match)
* m : allows for multiline anchors 
* s : allows a dot to match newline characters \n
* u : enables unicode support 
* y : searches for exact position in text 

### Grouping and Capturing

Adding parenthesis to your regex search will create a subpattern. Subpatterns allow for groups of characters to be searched for, and can search for those characters in relation to those outside of the parenthesis. 

For instance in the ``` a(b|c) ```example, both b and c are captured, and can be searched in combination with the a outside of the parenthesis. 

It functions almost like order of operations. 
### Bracket Expressions

Bracket expressions matches characters within the character, or excludes those characters from the search. 

An example: 

``` [a-d] ``` would search and match any character within the range of a to d, (a,b,c and d).

### Boundaries

There are three positions that a referred to as boundaries. 
* The first character of a string 
* The last character of the string 
* Between two characters (if one is a letter character and the other isn't)

For example: 

``` \bword\b ```

in reference to the string 

"Hi, Teddy!" Would return Teddy.

### Back-references

Backreferences searches for a previous match group, and tries to replicate the same string again. 

You can utilize backreferences to find repeated or adjacent strings of text. 

### Look-ahead and Look-behind

Look-aheads and look-behinds, or together referenced as lookaround -- searches for patters that are followed or preceded by another pattern.  

## Author

Aliyah Musaliar (they/them, she/her) is a student learning full-stack webdevelopment, and presently works in survivor advocacy and visual arts. 

Their github is: 

https://github.com/musaliyah

and their email is

asmusaliar@gmail.com