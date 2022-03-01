

 - [ ] 1. Syntax; usage of const/let; single vs multiple params; returning objects;
 - [ ] 2. Functions: Regular vs. Arrow Functions; Regular Function Binding; Single-line vs Multiple-line Arrow Functions;
 - [ ]  Absence of the "function" keyword; It cannot be used as a function constructor
 - [ ] 3. 'this'
 - [ x] 3.1 What does 'this' reference to
 - [x ] 3.2 'this'
 - [ ] 3.3 What does it refer to

# Article: Arrow Functions

___

## Syntax

- Syntax example
  - ===
- const / let
- Parameters
  - Single
  - Multple
- Returning objects

___

## Functions

### Regular Functions
What are regular functions? 
- Binding
___

### Arrow Functions
- Single-line
  - Install GIT
- Multiple-line

| Function                            | Required? | Type       | Default | Purpose / Value                           |
| ----------------------------------- | --------- | ---------- | ------- | ----------------------------------------- |
| X_PLAYBOOK_NAME_X_apps              | no        | dictionary |         | Define what applications will be deployed |
| X_PLAYBOOK_NAME_X_apps.X_APP_NAME_X | no        | boolean    | true    | Deploy the application?                   |

___
### Differences between Regular Functions and Arrow Functions

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
