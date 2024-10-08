# Regex-made-easy
# Validating an E-Mail This tutorial is copyrighted in 2022 by Claudia Chittim, - DO NOT COPY

>Validating an e-mail address is a very important process when it comes to validating HTML data that is put into templates by end-users. This typically happens when a user subcribes to a website product or service and has to be authenticated by another company. Luckily, regular expressions in Javascript enable the back-end programmer to validate e-mail addresses for new or existing clients everytime they login to a site or subscribe to a website application.

>The need to validate e-mails is even more important for as long as people have tools to create fake e-mails just for the purpose to subscribe to websites. There are also programs that confuse back-end programmers like bots that crawl websites just to enter invalid e-mail address in order to gain access to website content. 

## Summary

>The regular expression to validate e-mail addresses will be covered in this tutorial. All terms and definitions related to programming regular expressions in Javascript will be revealed for the purpose of educating anyone about the usefulness of regular expressions (or regex) in the world of validating e-mails. Regular expressions are integrated with string methods. The method `str.match(animals)` finds all matches of 'animals' on the string `str`. In sum, regular expressions provide a powerful way of doing searches and replacements in strings. 

>An e-mail is a string or subset of ASCII characters that is separated by the `@` character or "elephant ear". It has two parts: personal information and a domain. The length of the personal information section can by up to 64 characters long and the domain name may be up to 253 characters long.

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
- [Backreferences](#backreferences)

## Regex Components

### Anchors

>An anchor is a marked position in an HTML document, to which the user can jump from elsewhere. For example, the HTML command `<A NAME ='Elephants'> All about Elephants </A>` marks its position as an anchor named "Elephants," and if it resides in the file `http://www.vet.uga.edu/animals.html`, then the full address of the anchor is `http://www.vet.uga.edu/animals.html#Elephants`. 

>In terms of regular expressions in Javacript, the anchors `<^`> and `<$>` force the expression to find its match at the start and end of the subject text. If one places the regular expression between these characters, it effectivaly requires the singular expression to match the entire subject. 
>The `^` anchor can force the expression to find words that follow that anchor at the beginning of a sentence or start of a line in Javascript code. The `$` anchor locates any term of code at the end of a line in Javascript code. Not only do these anchors apply to Javascript, they also apply to .NET, JAVA, PCRE, Python and Ruby languages.

### Quantifiers

>Quantifiers match a number of instances of a character, group, or character class in a string. For example, the regular expression:
`/\d{4}/` matches a four-digit number. It is the same as:`/\d\d\d\d/`.
>  They indicate numbers of characters or expressions to match. There are various special characters that can be used as quantifiers. For example `b*` will match the letter or word that proceeds a word in front of `b` 0 or more times. To be more specific, `/go*/` matches the letter `g` in any given expression or line of code. If we put `+` following a letter or string, the `+` symbol will match the preceding item of that character 0 or more times in a regular expression.

### OR Operator

>The 'OR Operator' uses the special charcter `|`. One can provide as many terms as needed as long as they are separated by the pipe character. For example `I like (dogs|lizards), but not (cats|birds)` would render the following statement: `I like dogs or lizards, but not cats or birds`. 'OR Operators' are not needed for regular expressions in e-mail validations.

### Character Classes

>Character class is a commonly used in regular expressions as a construct that uses square brackets `[ ]`. A character class matches a single character or group of characters out of a list of possible characters. Within a character class, the following special characters have functions: `\,^,- and ]`. In the following e-mail address: `[claudiachittim2022]@gmail.com` the letters `[claudiachittim2022]` are considered a special character class. One could load that class into a regular expression and fetch all e-mails that have those special characters in a string or query of e-mail addresses. They could then mark those characters as valid or invalid.

>Using the special character `\` inside a character class would match any digit from 0-9 and a-z with the letter or digit following the `\`. So `[\domain@domain.com]` would match any e-mmail address with the characters that follow the `\` special character. 

### Flags

>A regular expression (regex) consists of optional flags. There are only six types of flags in Javascript: `i, g, m, s, u and y`. Each character has a different function for searching and processing of characters. For example `m` enables the multiline mode. `m` affects the behavior of `^` amd `$`. In the multiline mode they match not only at the beginning and the end of a string, but also at the start and end of a line.

>An example of the `m` flag is seen in the console log below:

>1. `const req=(all e-mails)`
>2. `1st e-mail: test@testing.com`
>3. `2nd e-mail: testing @test.com`
>4. `3rd email: tester@testing.com`

>5. `console.log( str.match(/^\d/gm)); //1,2,3`

>Without the `m` flag in the console log the script would only render a `1` as seen here: `console.log(str.match(/^\d/g)); //1`.

>The `g` flag searches for all matches in a string or line of e-mails. When validating an e-mail `g` is for a global search, meaning it will match all occurences. 

### Grouping and Capturing
>Grouping enables a programer to capture a list of words as a whole word. For exmaple `\b(Chirp|Cuddle|Bark)\b` groups all three words together. It is useful to apply grouping when one needs to capture a string of words instead of programming the expression to capture just one word. Parentheses `()` are needed for grouping as shown in the example above. 
>
>Capturing refers to a program that grabs at something useful to a specific program. For example, if a printer needs to "capture" a port, the Windows may allow for a program to do that. It is usually applied to programs that utilize printer ports. It is also a term that is used when saving a bitmapped image on a website. In terms of e-mail validation `capturing` is not a term that may be applied to any regular expression. 

### Bracket Expressions

>Brackets `[ ]` allow a regulated expression to match specific characters within the brackets within a range. For example, `[1-9]` will search for numbers `1,2,3,4,5,6,7,8 and 9` or if given another special character a group of numbers within that range. Within the brackets the `-` character is not recognized literally. You can specify a range of characters within the brackets using a hyphen `-`. You can also replace the hyphen `-` with a carrot character `^`, as in `[^abcd]` but the range of the request will only cover letters `a,b,c and d` and not include the range of the entire alphabet.  

### Greedy and Lazy Match

>A greedy search in a regular expression tries to match any letter, character or number within the `/` characters. For example:
>1. `let regexp = /".+/g`
>2. `let str = ' an "elephant" in the "room";
>3. `alert(str.match(regexp)); // "elephant" in the "room"

> Anything that is in between the the forward slash and has quotations will be picked up by the greedy search. The `g` flag makes the search global for all occurences. The `.+` denotes any character except a new line. 

>A lazy match or quantifier allows the the expression or e-mail validation to repeat a minimal number of times. It is enabled by the question mark character `?`. For example, `\w*?E` tells the expression to match zero or more word characters, but as few as needed which might be none at all, then it finally looks for `E` in any given string. 

### Boundaries

> Boundaries set the beginning and end of a string of letters. For example in `[A-Z]` the letters 'A' and 'Z' are boundaries for the string associated in the brakets. Word boundaries can be replaced with start-of-string and end-of-string anchors such as `[^A-Z]`. Applying `^` to the string in the brackets will only match `A` and not `A-Z`.

### Backreferences

>Backreferences in numbers and patterns are useful when it comes to matching larger groups of content or text paragraphs. They are not useful for validating e-mails. 

## Author

[Claudia Chittim](https://c0y01202.github.io/Biography_Page) is a digital analyst and beginner web developer who has over 10 years of working in the Internet industry.
