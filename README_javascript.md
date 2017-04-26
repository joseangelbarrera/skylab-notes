# Javascript from scratch

# Style guide Javascrip
##___Javascript Standar Style:___

Glossary of Modern JavaScript Concepts: [Part 1]
(https://auth0.com/blog/glossary-of-modern-javascript-concepts/)

[This link shows you JavaScript style guide, with linter & automatic code fixer](https://standardjs.com/)

The javascript files are a part of the website:

1. Content: .hmtl
2. Design: .css
3. Behavior: .js

This are the three layers of a website. Javascrip is one of them.

##Variable
its like a box where you can put all you want to be executable into
`var nameVariable = x` 
variables are case sensitive

## Kind of data


1. var a; typeof a;
2. var s = '1s'; s++; 
3. !!"false"
4. !!undefined
5. undefined == null
6. false == ""
7. false === ""
8. typeof "2E+2"
9. a = 3e+3; a++;

== this simbols compares the values of two things

2== '2'
> true

2 === '2'
> false

primitive values


##Six data types that are primitives:
Boolean
Null
Undefined
Number
String
Symbol (new in ECMAScript 6)

##and Object

* function
* arrays
* objects


falsy values

### primitive data:
1. Number
2. String
3. bolean
4. Undefined (only one value = undefined)
5. Null (only one value = Null)
`typeof` give us the kind of data have a value

### Object
Data that is not a primitive is an object.

## operations

++ before or after

```var = 5
var b = a++
b
5
a
6
```


```var = 5
var b = ++a
b
6
a
6
```

increment plus x 

```var a = 5
a =+ 5
a
10
```

= assign value
== compare
=== compare value and feature
best practice allways ===


a string coul be converted tu number by two ways
multiply by 1
add a add symbol
b = '243534'
b = (+a)

in order to know the bolean os something you can ad a double admitration

< !! = if (more or less)
----

!!4
true
!!'barcelona'
true
!!''
false

###falsy values (they return false):
- zero
- false
- empty string ""
- undefind
- null
- NaN

### ternary operator

There also exist what is called the ternary operator ? that allow us to abbreviate some simple if sentences
Example:

var result = (a === 1) ? "a is one" : "a is not one";

we prefer use this notation with the case is simple. We must to try to make our code easy to read.

### Switch (case - default - break)

it is usefull in case the value is exact, is not so conditional as the if else

```var a = '1';
var result = '';
switch (a) { 
  case 1: 
    result = 'Number 1'; 
    break; 
  case '1': 
    result = 'String 1'; 
    break; 
  default: 
    result = 'I don\'t know'; 
    break;
}
result;
```


\n return
\t tab
\

```
var res = '\n';
for  (var i = 0; i<10; i++){
for ( var j = 0; j<10; j++)  {
    res += ' * ';
    }
    res += '\n';
}
```

result is:

"
 *  *  *  *  *  *  *  *  *  * 
 *  *  *  *  *  *  *  *  *  * 
 *  *  *  *  *  *  *  *  *  * 
 *  *  *  *  *  *  *  *  *  * 
 *  *  *  *  *  *  *  *  *  * 
 *  *  *  *  *  *  *  *  *  * 
 *  *  *  *  *  *  *  *  *  * 
 *  *  *  *  *  *  *  *  *  * 
 *  *  *  *  *  *  *  *  *  * 
 *  *  *  *  *  *  *  *  *  * 
"

```
var res = '\n';
for  (var i = 1; i<11; i++){
for ( var j = 1; j<11; j++)  {
    res += (i*j) + '\t\t';
    }
    res += '\n';
}
```


1   2   3   4   5   6   7   8   9   10  
2   4   6   8   10  12  14  16  18  20  
3   6   9   12  15  18  21  24  27  30  
4   8   12  16  20  24  28  32  36  40  
5   10  15  20  25  30  35  40  45  50  
6   12  18  24  30  36  42  48  54  60  
7   14  21  28  35  42  49  56  63  70  
8   16  24  32  40  48  56  64  72  80  
9   18  27  36  45  54  63  72  81  90  
10  20  30  40  50  60  70  80  90  100 


# Functions

functions allways return something. If you no ask for it returns `undefined`

be careful about `console.log` and `return`

return as the name say us return something but console.log will not return, only print.

A function only return a value –variable– (no two or more)

`argumnets` is a pseudo array (it is a resered word that include the arguments of the funtion)



function

### Hexadecimal

notes from JuanMa:

binary number = combination of 1 and 0
decimal number = combination of numbers from 0 to 9. Ten numers in total.

The number 5678 is a combination from:

8*(10^0) +7*(10^1) + 6*(10^2) + 5*(10^3)
8 +70 + 600 + 5000 = 5678

the hexadecimal notation is a combination from
numbers from zero to nine adn letters ABCDEF

0000FF is a combination from

  *(16^0) + *(16^1) + *(16^3)




