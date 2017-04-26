

# Functions

## Function globals


## Function locals


funtion

one functions coulf be var f = function() { return 3}
this style is a anonimous function (without name)

anonimous: function() { return 3}

we van ask for this functions is that the reason qe assign a variable

functions are a value that we assign to a variable

a call back function is the funcions used into anoterhe function

the anonimous functions could be used ad an argumnet into another function

a funtion is a date ()

if we make `typeof`  it returns 'functions'

the global functions or variables cannot be seeing in the local eviorement, but otherwise is possible

the name of that is 'scope chaine'.

__Anonimous functions__ are those that doesn't have a name and can be used to:

Pass that function as an argument of a function
Define a function and execute it inmediately
>>> function(a){ return a; }
When we pass a function A as an argument of another function B and B executes A, we tell that A is a callback function

>>> function invoke_and_add(a, b){ return a() + b(); }
>>> function one() { return 1; }
>>> function two() { return 2; }
>>> invoke_and_add(one, two);
3
>>> invoke_and_add(one, function(){return 7;})
>>> 

##Closures

If we define a function n() inside of another function f() , n() will have access to all the variables in its scope and its father's scope. This is what is called scope chain

Functions have what is called as __lexical scope__ which means they create theis scope (which variables can they access) when they are defined, not when they are executed

>>> function f1(){ var a = 1; return f2(); }
>>> function f2(){ return a; }
>>> f1();
a is not defined
>>> var a = 5;
>>> f1();
5
>>> a = 55;
>>> f1();
55
>>> delete a;
true
>>> f1();
a is not defined
var a = 123;
function f() {
  alert(a);
  var a = 1;
  alert(a);
}
f();


__hoisting effect__: this is a very crazy effect that produce javascript when you are declaring variables into a function and at the same time you declare the same name of a variables outside the function.

A __closure__ is created when a function maintains a link with the scope of the father, even after the parent function has finished. Its a secret link.

a closure is created when an inner function refers to an outer function's variables


another example

function timesCallFn() {
    var times = 1;
    return function() {
    return times++;
      }
    };
var m = timesCallFn() 

the scope of a functions include the variables it can access


__scope chain__ look for it



##Exercise 1

function test() {
    foo();
    bar();
    var foo = function () {
        alert("this won't run!");
    }
    function bar() {
        alert("this will run!");
    }
}
test();
What will return the execution of test()? Why?ç

This function have two intenr functions, but both are differetn between them.

The first one:
 var foo = function () {
        alert("this won't run!");
    }

the variable is not defined.






if we write the function in this way:

 function bar() {
        alert("this will run!");

 it will run whitout problems.


#Exercise two

```
var a = 1;
function f() {
    var a = 2;
    function n() {
        alert(a);
    }
    n();
}
f();
```


What will show this code in the alert()? Why?

### solution
it will show : 2





##Exercice 3

```
var mathy = function(x) {
    return function (y) {
        return function (z) {
            return (x / y) - z;
        }
    }
}
```



¿Cómo hariamos la operación (4 / 3) - 2 con este código en una linea?
Solution:
**mathy(4)(3)(2)**



##Exercise 4

```
var superGreeter = function(greeting) {
    return function(place) {
        return function(nickname) {
            return function(name) {
                return greeting + ', ' + name + '! Welcome to ' + place + ', ' + nickname + '.';
            }
        }
    } 
};
­
superGreeter('Hey')('Berlin')('old pal')('Hans')
//'Hey, Hans! Welcome to Berlin, old pal.'
­
hiParisBuddyGreeter = superGreeter('Hi')('Paris')('buddy');
helloTokyoGreeter = superGreeter('Hello')('Tokyo');
­
hiParisBuddyGreeter('Franz')
//'Hi, Franz! Welcome to Paris, buddy.'
helloTokyoGreeter('friend')
//[Function]
helloTokyoGreeter('friend')('Yuki')
//'Hello, Yuki! Welcome to Tokyo, friend.'
```






#Array methods as Higher Order Functions

for example .forEach
This function needs antoher function to rur.


###map()

map() returns a new array with the result of calling a function provided as an argument over every element of the array
```
var myNumbers = [1,2,3,4];
var myDoubleNumbers = myNumbers.map(function (item) {return item*2})
myDoubleNumbers
```


###every()

###some()

### reduce()

```
[2, 4, 6, 7, 8].reduce(funtcion (acc, item) { return acc + item}, 0)
```

this  return the sum of items = >> 27

```
var scores = [5,3,4,1,7,3,5,2,7,2,9,4] // 12

var newScores = scores.map( function(score) { return score + 1 })
var havePassedAll = newScores.every( function(score) { return score >= 5 })
var isThereSome10 = newScores.some( function(score) { return score === 10 })
var failedScores = newScores.filter( function(score) { return score < 5 })

var averageScore = newScores.reduce( function(acc, item) {
  return acc + item
},0) / newScores.length
```


## Examples:

```
var scores = [5,3,4,1,7,3,5,2,7,2,9,4] // 12

var scores = [
  {
    student: "julian",
    score: 4
  },
  {
    student: "maria",
    score: 8
  },
  {
    student: "paco",
    score: 2
  },
  {
    student: "luisa",
    score: 9
  }
]

var newScores = scores.map( function(score) { return score + 1 })
var havePassedAll = newScores.every( function(score) { return score >= 5 })
var isThereSome10 = newScores.some( function(score) { return score === 10 })
var failedScores = newScores.filter( function(score) { return score < 5 })

var averageScore = newScores.reduce( function(acc, item) {
  return acc + item
},0) / newScores.length

// -------------------------------------

function addOne(score) { return score + 1 }
var addOne = score => score++

// -------------------------------------

// var newScores = scores.map( score => score + 1 )
// var havePassedAll = newScores.every( score => score >= 5 ) // true or false
// var isThereSome10 = newScores.some( score => score === 10 ) // true or false
// var failedScores = newScores.filter( score => score < 5  )

```

```
var scores = [5,3,4,1,7,3,5,2,7,2,9,4] // 12

var scores = [
  {
    student: "julian",
    score: 4
  },
  {
    student: "maria",
    score: 8
  },
  {
    student: "paco",
    score: 2
  },
  {
    student: "luisa",
    score: 9
  }
]

var newScores = scores.map( function(score) { return score + 1 })
var havePassedAll = newScores.every( function(score) { return score >= 5 })
var isThereSome10 = newScores.some( function(score) { return score === 10 })
var failedScores = newScores.filter( function(score) { return score < 5 })

var averageScore = newScores.reduce( function(acc, item) {
  return acc + item
},0) / newScores.length

// -------------------------------------

function addOne(score) { return score + 1 }
var addOne = score => score++

// -------------------------------------

// var newScores = scores.map( score => score + 1 )
// var havePassedAll = newScores.every( score => score >= 5 ) // true or false
// var isThereSome10 = newScores.some( score => score === 10 ) // true or false
// var failedScores = newScores.filter( score => score < 5  )


Add Comment Collapse

Juanma Garrido [12:41 PM]  
added this JavaScript/JSON snippet 
function showPassedStudentNames ( student ) {
  if (student.score >= 5) console.log(student.name)
}

function addOneToScore( student ) {
  student.score++;
  return student;
}

// show names of students that have passed
students.forEach( showPassedStudentNames )

// show names of students that have passed after adding 1 to scores
students
  .map( addOneToScore )
  .forEach( showPassedStudentNames )

students
  .map( addOneToScore )
  .filter( function(student) { return student.score >= 5 })
  .map( function(student) { return student.name })
  .join(" - ")

var students = [
  {
    name: "julian",
    score: 4
  },
  {
    name: "maria",
    score: 8
  },
  {
    name: "paco",
    score: 2
  },
  {
    name: "luisa",
    score: 9
  }
]
```

```
function addOneToScore( student ) {
  student.score++;
  return student;
}

var addOneToScore = function( student ) {
  student.score++;
  return student;
}

typeof addOneToScore === "function"
```



## prototype

is a propiety of functions

for example

```
function person(gender) {}
this.gender = gender;
}
```

var person1 = new person('male')
var person 2 = new person (¡female')

The `prototype {}` function in an objetc

We hace the __prototype chain__

when you find for , it starts with the own object, and them to the prototype of the constructor function.

[THIS IS THE LINK TO KNOW ABOUT] (https://github.com/juanmaguitar/javascript-notes/tree/master/markdown-en/09-prototype)

Prototype chain

The objects have a thing called the prototype chain

If an object foo doesn't have a property bar when we do foo.bar, Javascript will look for that property in its prototype (the property prototype of the constructor function that created it)
If is not found there, it will be searched in the prototype of that prototype (the property prototype of the constructor function that created that prototype object)
And so on, until reaching the object at the highest level, the Object object

![EXAMPLE] (https://raw.githubusercontent.com/juanmaguitar/javascript-notes/master/markdown-en/09-prototype/img/prototype.png)

