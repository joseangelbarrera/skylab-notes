




**Browser Environment**

Dom is as you see html by javascript

WITH JAVASCRIPT YOU HAVE ACCESs TO SOME OBJECTS

Two kinds:

1. Related with html: **DOM**: Document Object Model methods are proprierties to access html.

2. Related with things that happend into browser: **BOM** (Browser Object Model). BOM is formed by all objects that are out of the loaded document and are part of the window object

You can access with **window object** (global). This object is the complete scope.

One good practice is to use and specify (in our final code) the windows. object as:

`window.myNumber = 5`

Every time you refresh the page, you start a new window object from scratch.

This is for all global methods and global objects.

**DOM**
The DOM (Document Object Model) is a way of representing a HTML document (or XML) like a tree of nodes.

By using DOM methods and properties we can access the page elements, modify them, remove them or adding new ones.

**ACCESING TO NODES:**

```
<body>
    <p class="opener">first paragraph</p>
    <p><em>second</em> paragraph</p>
    <p id="closer">final</p>
    <!-- and that's about it -->
</body>
```


But we are going to acces by jQuery.

jQuery best work with version above 2

Tis two expresion are equal:

$() ==== jquery()


**Callbacks and Functions**
A callback is a function that is passed as an argument to another function and is executed after its parent function has completed.

It is important to know how to pass callbacks into their parent function:

*Callback without Arguments*

`$.get( "myhtmlpage.html", myCallBack )` 
When $.get() finishes getting the page myhtmlpage.html, it executes the myCallBack() function.

*link Callback with Arguments*
Note that this notation

`$.get( "myhtmlpage.html", myCallBack( param1, param2 ) )`

 is wrong because immediately executes myCallBack( param1, param2 )  and return a value that is passed as the second parameter to $.get().

We actually want to pass the function myCallBack() for that reason you can use an anonymous function as a wrapper that exactly calls myCallBack(), with the values of param1 and param2.

```
$.get( "myhtmlpage.html", function() { myCallBack( param1, param2 ); });
```

When $.get() finishes getting the page myhtmlpage.html, it executes the anonymous function

link Right

link Callback without Arguments
text and html


**attr()**
The atribute of an element could be very useful, so be ready to get and set them.

The .attr() method acts as both a getter and a setter.

As a setter, .attr() can accept either a key and a value, or an object containing one or more key/value pairs.

```
$( "a" ).attr( "href", "allMyHrefsAreTheSameNow.html" );
 
$( "a" ).attr({
    title: "all titles are the same too!",
    href: "somethingNew.html"
});
```


.attr() as a getter:

```$( "a" ).attr( "href" ); // Returns the href for the first a element in the document
```



**Selecting Elements**

jQuery accept all CSS3 selectors, we are going to explain here a few of them, but the important ones.

Selecting Elements by ID
`$( "#theId" )`

Selecting Elements by Class Name
`$( ".oneClass" )`

by Attribute
`$( "input[target='_target']" )`

 by Compound CSS Selector
`$( "#notes ul.quotation li" )`

with a Comma-separated List of Selectors
`$( "div.thisClass, ul.quotation" )`



--
Posted in: Using jQuery Core > Frequently Asked Questions
How do I determine the state of a toggled element?
You can determine whether an element is collapsed or not by using the :visible and :hidden selectors.

var isVisible = $( "#myDiv" ).is( ":visible" );
 
var isHidden = $( "#myDiv" ).is( ":hidden" );
If you're simply acting on an element based on its visibility, just include :visible or :hidden in the selector expression. For example:

$( "#myDiv:visible" ).animate({
    left: "+=200px"
}, "slow" );
 ---

**replace text**

:eq() selector or .eq() method will allow you to select the proper item.

However, to replace the text, you must get the value before you set it:

// This doesn't work; text() returns a string, not the jQuery object:
$( this ).find( "li a" ).eq( 2 ).text().replace( "foo", "bar" );
 
// This works:
var thirdLink = $( this ).find( "li a" ).eq( 2 );
var linkText = thirdLink.text().replace( "foo", "bar" );
thirdLink.text( linkText );

The first example just discards the modified text. The second example saves the modified text and then replaces the old text with the new modified text. Remember, .text() gets; .text( "foo" ) sets.




i$('imput').val()




access to the value of a form.

important

to inert elements froma a place to another, or create a new element you can use apped or appendto


append I operate qith parent
appedTo I operate with child

**.prepend**

this insert a element ant the begining of a parent


**clone()**
create a copy



**remove()** and **detach()**


**eq()**

select the object quith the () order in the jquery object

use 

**jQuery methods**


**Getting and Setting Information About Elements**

.html() – Get or set the HTML contents.
.text() – Get or set the text contents; HTML will be stripped.
.attr() – Get or set the value of the provided attribute.
.width() – Get or set the width in pixels of the first element in the selection as an integer.
.height() – Get or set the height in pixels of the first element in the selection as an integer.
.position() – Get an object with position information for the first element in the selection, relative to its first positioned ancestor. This is a getter only.
.val() – Get or set the value of form elements.

**link Moving, Copying, and Removing Elements**

.insertAfter() method places the selected element(s) after the element provided as an argument.
.after() method places the element provided as an argument after the selected element.

Several other methods follow this pattern:
.insertBefore()
.before()

appendTo()
.append()

.prependTo()
.prepend().


**link Cloning Elements**

.clone().


**Removing Elements**

.remove() permanently remove the selection and their associated data and events.

.detach()  remove the selection but data and events persist.

empty(): leave the element on the page but remove its contents.

**Creating New Elements**
```
Creating new elements from an HTML string.
$( "<p>This is a new paragraph</p>" );
$( "<li class=\"new\">new list item</li>" );
```

```
// Creating a new element with an attribute object.
$( "<a/>", {
    html: "This is a <strong>new</strong> link",
    "class": "new",
    href: "foo.html"
});
```



Example

```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Document</title>
  <!-- Latest compiled and minified CSS -->
  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/css/bootstrap.min.css" integrity="sha384-1q8mTJOASx8j1Au+a5WDVnPi2lkFfwwEAa8hDDdjZlpLegxhjVME1fgjWPGmkzs7" crossorigin="anonymous">
  <style type="text/css">


  </style>
</head>
<body>

  <div class="container">
    <ul class="list-group" id="myList"></ul>
  </div>


  <script type="text/javascript" src="https://code.jquery.com/jquery-3.2.1.js"></script>

  <script type="text/javascript">
    var beatles = ['john','paul','george','ringo']
    var htmlList = ''
    beatles.forEach( function(name, i) {
      htmlList += '<li class="list-group-item">' + name + '</li>'
      console.log(htmlList)
    })
    console.log( typeof htmlList )
    $('#myList').html(htmlList)
  </script>
</body>
</html>
```


traversing

from a election how to acces to their sounrounded elements


.parent() to access to the parent of an element

.parents() to access to **all** the parent of an element


link Siblings
.prev()
.next()
. nextAll()
.siblings()
.nextUntil()
.prevAll()
.prevUntil()


.find()
.first()


.siblings() to select all siblings:


[]


you can cuse two forms of .each

.each
$( ).each



**.ready()**

To run code as soon as the document is ready to be manipulated, jQuery has a statement known as the ready event:

```$( document ).ready(function() {
 
    // Your code here.
 
});
```


**event.preventDefault()**
For click and most other events, you can prevent the default behavior by calling event.preventDefault() in the event handler:

```
$( document ).ready(function() {
 
    $( "a" ).click(function( event ) {
 
        alert( "As you can see, the link no longer took you to jquery.com" );
 
        event.preventDefault();
 
    });
 
});
```


**Adding an HTML Class**
To add a class to the html use the .addClass() call:

```
$( "a" ).addClass( "test" );
```


**Removing an HTML Class**
To remove an existing class, use .removeClass():

```
$( "a" ).removeClass( "test" );
```


**EVENTS**



Event propagation: when you click in a buttom is as you are clicking in all the pahers elements of this buttom

ON: useful to capture events

a good practoce is change animation and effcts tchangng classes (adding or deleting)


There are actions by default from some elements, with the object (event) . preventDefault() the objecto goes to be stopped.

For example, url, mailto, etc from a buttom could be stopped in order to achieve other actions i done to this bottom.

**events delegation**
this means that you can select a
(you put a third attribute in a event on()


select and value.

in a select el .val() is el value selected. but if i do not put value as attibute of the elements it select the selection.

for ecample.

the user can select Spain but I prefer to have the SP value, or the user select their name but I use the ID. 

```
<imput>
<select name="selñectos" id="selector-pisos">
    <option value="1" class="value">casa 1</option>
    <option value="2" class="value"> finca 2 </option>
    <option value="3" class="value"> casona 3</option>
    <option value="4" class="value"> vivienda 4</option>
    <option value="5" class="value"> piso 5</option>
</select>
</imput>
```




**work with the DOM**

its best practice to work as less as possible with the DOM. For that reason we catched the DOM, this means that we can work with only one time and save result for another moment we can need them.
