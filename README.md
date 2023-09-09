# Regex-Tutorial

## Summary:
JavaScript offers various methods for checking if a string contains specific letters or phrases, such as startsWith, endsWith, and includes. While these methods are handy for direct matches, sometimes you need more dynamic and comprehensive search capabilities. This is where regular expressions (regex) come into play.

## Table of Content
- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operators](#or-operator)
- [Character Classes](#character-classes)
- [Bracket Expression](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-matching)

## Anchors
In the provided regular expression /^#?([a-f0-9]{6}|[a-f0-9]{3})$/, let's start by dissecting the anchors. The highlighted components within the regular expression are referred to as anchors. Anchors are used to specify the beginning and end of a string or expression. In this context, ^ and $ indicate the start and end of the expression, respectively.

## Quantifiers
Moving on, let's delve into quantifiers. Quantifiers are employed to define how many characters are expected. They specify the required number of occurrences of a character, group, or character class for a match to be found. By default, quantifiers are greedy, meaning they match as many characters as possible. In the realm of regular expressions, characters such as *, +, ?, {} serve as quantifiers. The ? in the expression indicates that the preceding element should match either 0 or 1 time. As mentioned earlier, because we have two distinct formats, we use the OR operator (|) to differentiate between them. In our Hex Value regular expression, we have {6} (Hex Triplet Format) and {3} (Shorthand Hex Format), indicating that the preceding component's length should be 6 for {6} and 3 for {3}.

Hex Triplet Formats Include: #000000, #FFFFFFF, #0099CC
Shorthand Hex Format: #000, #FFF, #09C (the hex triplet format would just double each character: #09C -> #0099CC)

## OR Operator
The next element we'll explore is the "or" operator. Within a regular expression, the "or" operator is denoted by the | symbol. It signifies that either of the separated components can match. In our hex value regular expression, ([a-f0-9]{6}|[a-f0-9]{3}), the | operator separates these two components, indicating that our hex value can be either 6 characters [a-f0-9]{6} or 3 characters [a-f0-9]{3}.

## Character Classes
Character classes are components within our regular expression that specify the types of characters we expect. In our example, character classes are enclosed within square brackets []. We have two character classes: [a-f0-9] and [a-f0-9], both searching for the same values. Let's break down what these character classes are looking for. [a-f] searches for letters 'a' to 'f', while [0-9] searches for digits from '0' to '9'.

## Bracket Expressions
Bracket expressions in our regular expression mark the beginning of a character class or quantifier statement. In our example, we use parentheses to define our bracket expressions.

## Greedy and Lazy Matching
Lastly, we touch upon greedy and lazy matches. A greedy match attempts to match an element as many times as possible, while a lazy match aims to match it as few times as possible. In our example, the ? signifies a lazy quantifier. It instructs the regular expression engine to match as few occurrences as possible. To make this a greedy match, we can simply remove the ?.