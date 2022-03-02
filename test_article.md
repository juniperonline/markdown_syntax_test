



Syntax
Compared to normal functions definition -- usage of const/let

Returning objects in particular


Absence of the "function" keyword
It cannot be used as a function constructor




# Article: Arrow Functions

In this lecture, we will get familiar with one of the most interesting and unique concepts for Javascript - Arrow Functions. 
Arrow functions are a compact alternative to the traditional function syntax. However, their use is limited.


___

## Syntax

The name of the function we derive from the 'fat arrow' we use in between the two sides of the function.
The left side represents the parameters and the right side - the expression. 
Some parts of the syntax are optional, as we will find out in later sections of the article.

<p align="center">
    <img src="./pictures/arrow_functions.PNG" style="width: 60%"/>
</p>

___
### Single parameters vs Multiple parameters

When parsing a single parameter, neither a return statement, nor parenthesis are required.

TO DO: 
better example
```javascript
x => x * x
```

If we want to parse multiple parameters, parenthesis will be required.

```javascript
(x, y) => x * y
```
___

### Single-line Arrow Functions vs Multiple-line Arrow Functions

Single-line functions don't require body braces.

```javascript
x => {
  let a = 1;
  return x + a;
}
```

Multiline statements require body braces and a return statement. In this case, we've got multiple parameters, so we can see the full syntax.

```javascript
(x, y) => {
  let a = 1;
  return x + y + a;
}
```
___


### Comparing traditional functions to arrow functions (usage const and let) 


```javascript
//Normal Function
  var multiply = function(x,y) {
    return x*y;
    };

//Arrow Function
  var multiply = (x,y) => x*y;
//or
  var multiply = (x,y) => {return x*y};  
```
___
___

### Differences between Regular Functions and Arrow Functions

What are the differences? 

One of the main differences between them is the syntax. Please look at section "Comparing traditional functions to arrow functions" to see a visual representation of that difference.

Another main difference is naming. We can not name an arrow function, however we can store it in a variable and access it that way.

[![Arrow Functions example]()](https://youtube.com/clip/UgkxUmjy9O1HzRdT7u6ILrAtY2RRPMq4YCDM "Arrow Functions")

| Regular Function  | Arrow Function |
| ----------------- | ------------- |
| Traditional Syntax | () => {} |
| Can be named or anonymous | Always anonymous  |
| Can be hoisted  | Not possible, unless inside an object  |
| 'this' can be used  | 'this' will be global |
|Access to arguments |No access to arguments|

___
### Regular Functions: Binding


___
### Defining 'this'

In JavaScript, ```this``` is used a bit differently, than in other languages like C++ or Java. The keyword ```this``` refers to the object executing the current function. It is entirely determined by **how** a function is called, and not **where** it gets defined. 

If we could simplify the usage of ```this```, it would look something like this: 

<p align="center">
    <img src="./pictures/this_formula.png" style="width: 60%"/>
</p>

If called inside an object method, ```this``` references the object that the method belongs to.

```javascript
  class NameGenerator {
    constructor() {
      const btn = document.querySelector['button'];
      this.names = ['Max', 'Anna', 'George'];
      this.currentName = 0; 
      this.addName();  // 'this' here refers to the constructor
      btn.addEventListener ('click', this.addName); // but 'this' refers to the button object
    }

    addName() {
      const name = new NameField(this.names[this.currentName]);
      this.currentName++;
      if (this.currentName >= this.names.length) {
            this.currentName = 0;
        }
     }
  }
  const gen = new NameGenerator();
```
In this example, we see that ```this``` will always point to the object that owns the object method.

However, we can use methods like ```call()```, ```apply()```, and ```bind()``` to control what ```this``` refers to.
The ```call()``` and ```apply()``` methods are interchangeable. The only way they differ is the way they supply their arguments: ```call()``` allows passing arguments one by one, separating them with commas; while ```apply()``` uses an array. 
The ```bind()``` method allows passing an array or any number of arguments, but returns a new function.

We can use ```bind()``` in our constructor as our best bet, since we don't know when the event will be fired, but we know the desired result.

Note: The methods above have no effect on arrow functions. Check later!!!!

```javascript
      btn.addEventListener ('click', this.addName.bind(this));
```

At the global level, ```this``` is equivalent to a global object called ```global``` or ```window``` in browsers.


### References

1. Defining 'this' : formula [Understanding Functions and 'this' In The World of ES2017](https://youtu.be/gvicrj31JOM)
2. 'this' in object method example [JS "this" and Function References - What is it all about?](https://youtu.be/Pv9flm-80vM)
3. 'this' in regular functions example: Project Documentation: [X_PROJECT_DOC_URL_X](X_PROJECT_DOC_URL_X)
