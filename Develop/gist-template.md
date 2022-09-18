# Matching an Email with a Regular Expression

A Regular Expression, also known as regex, is a sequence of characters that allows a person or program to indicate a specific patten they search for. As daunting as the collection of numbers, letters, and symbols can be, once you come to understand what each symbol means, the point of the whole sequence becomes clear. It is simply another language that coders should learn to help make their lives easier, and can even be created into a fun little game once you come to understand a majority of it.

## Summary

The regex that we will be going over in this tutorial helps to find and match a pattern for an email in whatever string you want to break down. From the starting point to the last piece of the sequence, we will be taking apart each piece and explaining it.

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

Before we get started on breaking them down, first you should become familiar with the sequence itself. 

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

### Anchors

There are two kinds of anchors we will be touching upon here. The first is the delimiter, a crucial part that indicates the beginning and end of an expression. For the email regex, the delimiter is a forward slash that provides you with a closed off expression between them. There are other types of delimites that can be used, even ones with parentheses and brackets, but this email regex makes the use of the forward slash.

After that come the anchors of the string itself. The ^ is used to indicate the start of the string as seen in the regex and the $ indicates the end. Unlike the delimiter which can include other characters that do its job, the ^ and $ are the common operators, if not the only, that tell you when the string has started and ended.

### Quantifiers

Quantifiers in a regex expression help determine the size of the expression, going so far as allowing however many characters you can fit or even limited it to zero times. The regex tends to be at the end of each individual straight brackets set, resting just outside of it and providing with how long the inner characters can go on for. For the first two quanitifiers used, the + sign indicates that the number of characters can be one or more with no limites placed upon them. At the end, before the finishing anchor, a different quantifier appears that limits the last piece of the expression to a specific number. {2,6} provides a match of no less than two characters and no greater than six in the expression. Even if there are more, it won't recognize and may even reject if there are fewer or greater than the amount given.

### OR Operator

Though this expression does not contain an OR operator, it is always something you should come to learn. The OR operator appears as | in a string, allowing some leniency when it comes to the choice of characters. ABC|XYZ means that either ABC or XYZ is acceptable, though not any combination of the two.

### Character Classes

Most expressions will contain characters that the regex is searching for, though the classes might not always be the same. For the email regex, there are a two classes that are used, a-z and 0-9. a-z searches for any letters in the string, though it will only accept those that are lowercased. The same can be said for 0-9 as it will accept all numbers provided in the string. They do not always have to allow such a broad acceptance, as there are expressions that can limit themselves to specific letter or numerical characters, putting them in between brackets without a dash in between the charcters, but the email regex accepts any that are lowercased.

### Flags

There do not appear to be any flags in this expression, but again that does not stop us from understanding what there are. A flag is a character placed in there that specifically does something the the search, such as i making the search case-insensitive where it usually is sensitive. When we say insensitive, we mean that if you were to search for go in the phrase "Go go boots", it would provide only the second go. But if you were to make the search go/i, it would pull up both go's.

### Grouping and Capturing

When it comes to grouping and capturing an expression, parentheses are used to break the expression into multiple parts. In the email regex, parentheses are used three times, one for the beginning ot the email address, once for what the receiving website would be, and once at the end. This makes sure that none of the searches the regex is going through blends any of the characters together, which would make it far more difficult in understanding the string it is trying to find matches in.

### Bracket Expressions

Inside the parentheses are bracket expressions, exactly what you will be looking for in the string regarding characters. The email regex makes use of bracket expressions within each grouping, making good use of the character classes we went over. Within the bracket there is a-z0-9, allowing the match to understand multiple classes and draw from it to provide with a more accurate search. Just as the grouping keeps things organized into sections, the brackets do a more specified job of sectioning.

### Greedy and Lazy Match

As mentioned with the quantifiers before, + is used to indicate that any number of characters from one onwards can be searched through with the provided string, enforcing no limits. It is because the quantifier will continue searching for matches and pull in as many as it can that it is considered Greedy. The only thing stopping it from pulling information from every part of the expression is the parentheses grouping, making sure that it only pulls from that inside the brackets that preface it. There is another kind of match called Lazy, with the most common quantifier being ?. That quantifier makes sure to go for the shortest string it can, stopping almost as soon as it satisfies the search it was put through. For example, a + would match 'hell' in hello but a ? would only extend the match to 'hel'.

### Boundaries

Boundaries exist to help make a search more precise when looking through a string. There aren't really any boundaries in the email regex, though an example of what a boundary in a regex is would be \b for a word boundary. If the match was searching for a word between two \b, it would look only for that word on its own. There are other uses for the backslash, but none regarding boundaries for the email regex.

### Back-references

Just as there are no boundaries in the email regex, there are no Backreferences either. It does make use of the backslash again, such as \1 is considered a backreference as it refers back to the first captured group in the string. 

### Look-ahead and Look-behind

There are different kinds of Look-aheads and Look-behinds, a positive and negative for each one. Just as the name says, the look aheads look for a character that prefaces whatever is followed by it and the look-behinds look for a character that comes after. The email regex does not have an example for them, but they are easy enough to remember. The positive look-ahead uses the symbols ?=, such as if you are looking for X in X(?=Y), you are only going to find X if it is immediately followed by Y. The negative look-ahead uses ?!, for if you are looking for X in X(?!Y), you will only find X if it is not followed by a Y. The same goes for the look-behinds, as the positive looks lik ?<= and the negative looks like ?<!. Look for X in (?<=Y)X and you will find X only if it follows Y. Look for X in (?<!Y)X and you will only find it if it does NOT follow Y.

## Author

This tutorial was written by [Caid Huber](https://github.com/ahuber25).