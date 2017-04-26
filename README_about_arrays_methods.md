# Array methods

**concat()**
Joins two or more arrays, and returns a copy of the joined arrays

**copyWithin()** 
Copies array elements within the array, to and from specified positions

**every()**
Checks if every element in an array pass a test

**fill()** 
Fill the elements in an array with a static value

**filter()** 
Creates a new array with every element in an array that pass a test

**find()** 
Returns the value of the first element in an array that pass a test

**findIndex()**
Returns the index of the first element in an array that pass a test

**forEach()**
Calls a function for each array element

**indexOf()**
Search the array for an element and returns its position

**isArray()**
Checks whether an object is an array

**join()** 
Joins all elements of an array into a string

**lastIndexOf()**
Search the array for an element, starting at the end, and returns its position

**map()**
Creates a new array with the result of calling a function for each array element

**pop()**
Removes the last element of an array, and returns that element

**push()**
Adds new elements to the end of an array, and returns the new length

**reduce()**
Reduce the values of an array to a single value (going left-to-right)

**reduceRight()**
Reduce the values of an array to a single value (going right-to-left)

**reverse()** Reverses the order of the elements in an array

**shift()** Removes the first element of an array, and returns that element

**slice()**
Selects a part of an array, and returns the new array

**some()**
Checks if any of the elements in an array pass a test

**sort()**
Sorts the elements of an array

**splice()**
Adds/Removes elements from an array

**toString()**
Converts an array to a string, and returns the result

**unshift()**
Adds new elements to the beginning of an array, and returns the 
new length

**valueOf()** Returns the primitive value of an array




##__`for Each:`__

arr.forEach(function callback(currentValue, index, array) {
    //your iterator
}[, thisArg]);

####callback:
Function to execute for each element, taking three arguments:

####currentValue:
The current element being processed in the array.

####index:
The index of the current element being processed in the array.
array:

The array that forEach() is being applied to.

thisArg Optional:
Value to use as this

##__`keys`__

The Object.keys() method returns an array of a given object's
own enumerable properties, in the same order as that provided
by a for...in loop (the difference being that a for-in loop
enumerates properties in the prototype chain as well).


##__`filter`__

###SyntaxEDIT:

```
var newArray = arr.filter(callback[, thisArg])
___Parameters___
```

####callback
Function is a predicate, to test each element of the array. Return true to keep the element, false otherwise, taking three arguments:

#####element
The current element being processed in the array.

#####index
The index of the current element being processed in the array.

#####array
The array filter was called upon.

#####thisArg Optional
Optional. Value to use as this when executing callback.
Return value

A new array with the elements that pass the test.