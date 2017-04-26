# arrays and objetcs

this into a method of a object represent the object whitin

create objectos

literal notation


notation from a empty object
ver hero{} 

***txt***
___txt___
   drer
   der
      *sdfsdf
      * espace
      * espace
         * espace

we can create a function

```    function createhero()) {
    
    return {
        breed: 'turtle'}

    };
}    
```

[Visit ***GitHub!***](www.github.com)
[Search for it.] (www.google.com)
[####The Latest News from the BBC####]
[You're ___really, really___ going to want to see this.] ( www.dailykitten.com )



# How to create objects:

1.
```
var hero = {
  breed: 'Turtle',
  occupation: 'Ninja'
};
```

2.

```
var hero = {};
hero.breed = 'Turtle';
hero.name = 'Leonardo';
```

3.

```
function createHero() {
  return {
    breed: 'Turtle',
    occupation: 'Ninja'
  }
}
var hero = createHero();
```

4. ###Factory Function

```
function createHero(customName, customOccupation) {
  return {
    breed: customName,
    occupation: customOccupation
  }
}
var hero = createHero('Turtle', 'Ninja');
var hero = createHero('Power', 'Ranger');
```

5. ###Costructor Function

```
function Hero(name) {
  this.name = name;
  this.occupation = 'Ninja';
  this.whoAreYou = function() {
    return "I'm " + this.name + " and I'm a " + this.occupation;
  }
}

var h1 = new Hero('Michelangelo');
var h2 = new Hero('Donatello');
```



