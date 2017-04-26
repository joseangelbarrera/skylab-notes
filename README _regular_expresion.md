#Regular expresion

Allow us to find patters in a chain of thext.

[This is a lesson fron juanMa] (https://github.com/juanmaguitar/javascript-notes/tree/master/markdown-en/08-regular-expressions)

there a re two ways to create regualr expresion

##___The contructor function:___
va myRegExpr = new RegExp("")

forexample
var myRegExpr = new RegExp("j.*t")

we are looking for j.*t

j the first letter
t the last one

it can return true or false.
They can change the string 

this is very usefull in order to check some info the user are providing


all the instances we create going to acees to the method


##___literal notation___

var myRegExpr = /j.*t/

look at this symbol : /

thereare threee modificator

/g (global) : looking for all cases
/i ignoreCase : it ignore the case sensitive
/   m multile : the avoid the line cut
ej:

```var re = newregExp('j.*t', 'gmi')
```

to text regualer expresion use this link (http://regexr.com/)

'someText'.test([/otx/]) ==>  incorrect
[/otx/].test('someText')= ==> incorrect
/[otx]/.test('someText') ==> correct

with the simbol ^you are searchng for string do not martchs this patters

var myRegExpr = /j.*t/igm

we can use them in 


#methods:

##.test()
check if something is true or false

##.exec()
return an array with the string than have the pattern


### we can use string methods as

.match()
.split() : convert in a array
.replace()
.length
.search()

'we are learning regular expresion in javascript today'.search(/j.*t*/)
// ===> 1


ç


Regular Expression Syntax

https://en.wikipedia.org/wiki/Regular_expression
http://www.addedbytes.com/cheat-sheets/regular-expressions-cheat-sheet/
http://www.visibone.com/regular-expressions/

##[abc]

Looks for coincidences of the characters in the pattern

>>> "some text".match(/[otx]/g)
["o", "t", "x", "t"]

## [a-z]

Looks for coincidences in that characters range

[a-d] is the same than [abcd]
[a-z] looks for all the lowercase characters [a-zA-Z0-9_] looks for all the characters, numbers and the underscore

>>> "Some Text".match(/[a-z]/g)
["o", "m", "e", "e", "x", "t"]
>>> "Some Text".match(/[a-zA-Z]/g)
["S", "o", "m", "e", "T", "e", "x", "t"]
###￼￼[^abc]

Returns everything that does NOT match the pattern

>>> "Some Text".match(/[^a-z]/g)
["S", " ", "T"]
a|b

Returns a or b (the bar indicates OR)

>>> "Some Text".match(/t|T/g);
["T", "t"]
>>> "Some Text".match(/t|T|Some/g);
["Some", "T", "t"]
a(?=b)

Returns a only is found followed by b

>>> "Some Text".match(/Some(?=Tex)/g);
null
>>> "Some Text".match(/Some(?= Tex)/g);
["Some"]
a(?!b)

Returns a only is found NOT followed by b

>>> "Some Text".match(/Some(?! Tex)/g);
null
>>> "Some Text".match(/Some(?!Tex)/g);
["Some"]
\

Escape character that are used to find special characters used in the pattern as literals

>>> "R2-D2".match(/[2-3]/g)
["2", "2"]
>>> "R2-D2".match(/[2\-3]/g)
["2", "-", "2"]
\n

￼￼￼￼￼￼￼ New line

\r

Carriage return (To begin a new line \r\n is used in Windows, \n in Unix and \r in Mac)

\f

New page

\t

Tabulation

\v

Vertical Tabulation

\s

Blank espace or any of the previous 5 sequences

>>> "R2\n D2".match(/\s/g)
["\n", " "]
\S

The opposite of the previous sequence. Returns everything but blank spaces and the 5 escape sequences. The same than [^\s]

>>> "R2\n D2".match(/\S/g)
["R", "2", "D", "2"]
\w

Any letter, number, or underscore. The same than [A-Za-z0-9_]

>>> "Some text!".match(/\w/g)
["S", "o", "m", "e", "t", "e", "x", "t"]
\W

The contrary than \w

>>> "Some text!".match(/\W/g)
[" ", "!"]
\d

Locates a number. The same than [0-9]

>>> "R2-D2 and C-3PO".match(/\d/g)
["2", "2", "3"]
\D

The contrary than \d. It locates non-numerical characters. The same than [^0-9] or [^\d]

>>> "R2-D2 and C-3PO".match(/\D/g)
["R", "-", "D", " ", "a", "n", "d", " ", "C", "-", "P", "O"]
\b

A word "limit" (space, puntuation, hyphen...)

>>> "R2D2 and C-3PO".match(/[RD]2/g)
["R2", "D2"]
>>> "R2D2 and C-3PO".match(/[RD]2\b/g)
["D2"]
>>> "R2-D2 and C-3PO".match(/[RD]2\b/g)
["R2", "D2"]
\B

The contrary than \b

>>> "R2-D2 and C-3PO".match(/[RD]2\B/g)
null
>>> "R2D2 and C-3PO".match(/[RD]2\B/g)
["R2"]
^

Represents the beginning of the string where we're looking for. If we have the modificator m it represents the beginning of every line.

>>> "regular\nregular\nexpression".match(/r/g);
["r", "r", "r", "r", "r"]
>>> "regular\nregular\nexpression".match(/^r/g);
["r"]
>>> "regular\nregular\nexpression".match(/^r/mg);
["r", "r"]
$

Represents the final of the string where we're looking for If we have the modificator m it represents the end of every line.

>>> "regular\nregular\nexpression".match(/r$/g);
null
>>> "regular\nregular\nexpression".match(/r$/mg);
["r", "r"]
.

Represents any character but the new line and the carriage return

>>> "regular".match(/r./g);
["re"]
>>> "regular".match(/r.../g);
["regu"]
*

It matches if the preceding pattern happen 0 or more times /.*/ will return everything, including "nothing" (empty string)

>>> "".match(/.*/)
[""]
>>> "anything".match(/.*/)
["anything"]
>>> "anything".match(/n.*h/)
["nyth"]
?

It matches if the preceding pattern happen 0 or once

>>> "anything".match(/ny?/g)
["ny", "n"]
+

It matches if the preceding pattern happen 1 or more times (at least once)

>>> "anything".match(/ny+/g)
["ny"]
>>> "R2-D2 and C-3PO".match(/[a-z]/gi)
["R", "D", "a", "n", "d", "C", "P", "O"]
>>> "R2-D2 and C-3PO".match(/[a-z]+/gi)
["R", "D", "and", "C", "PO"]
{n}

It matches if the preceding pattern happen exactly n times

>>> "regular expression".match(/s/g)
["s", "s"]
>>> "regular expression".match(/s{2}/g)
["ss"]
>>> "regular expression".match(/\b\w{3}/g)
["reg", "exp"]
{min,max}

It matches if the preceding pattern happen between min and max times max can be omitted (will only have minimum) min cannot be omitted

>>> "doooooooooodle".match(/o/g)
["o", "o", "o", "o", "o", "o", "o", "o", "o", "o"]
>>> "doooooooooodle".match(/o{2}/g)
["oo", "oo", "oo", "oo", "oo"]
>>> "doooooooooodle".match(/o{2,}/g)
["oooooooooo"]
>>> "doooooooooodle".match(/o{2,6}/g)
["oooooo", "oooo"]
(pattern)

When the pattern is between parentheses, is being captured and stored so it can be used in substitutions (patterns capture).
Thse captures are available at $1, $2,... $9

>>> "regular expression".replace(/(r)/g, '$1$1')
"rregularr exprression"
>>> "regular expression".replace(/(r)(e)/g, '$2$1')
"ergular experssion"
{?:pattern}

Non capturable pattern (not available at $1, $2, ...)

>>> "regular expression".replace(/(?:r)(e)/g, '$1$1')
"eegular expeession"





