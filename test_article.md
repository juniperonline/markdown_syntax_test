

 - [ ] 1. Syntax; usage of const/let; single vs multiple params; returning objects;
 - [ ] 2. Functions: Regular vs. Arrow Functions; Regular Function Binding; Single-line vs Multiple-line Arrow Functions;
 - [ ]  Absence of the "function" keyword; It cannot be used as a function constructor
 - [ ] 3. 'this'
 - [ ] 3.1 What does 'this' reference to
 - [ ] 3.2 'this'
 - [ ] 3.3 What does it refer to

# Article: X_PLAYBOOK_NAME_X

___

## Syntax

- Syntax example
  - new operator
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

### Arrow Functions
- Single-line
  - Install GIT
- Multiple-line

| Function                            | Required? | Type       | Default | Purpose / Value                           |
| ----------------------------------- | --------- | ---------- | ------- | ----------------------------------------- |
| X_PLAYBOOK_NAME_X_apps              | no        | dictionary |         | Define what applications will be deployed |
| X_PLAYBOOK_NAME_X_apps.X_APP_NAME_X | no        | boolean    | true    | Deploy the application?                   |


```javascript
  function ask(question, yes, no) {
  if (confirm(question)) yes();
  else no();
}

ask(
  "Do you agree?",
  function() { alert("You agreed."); },
  function() { alert("You canceled the execution."); }
);
```
Edge cases: 

___

### Defining 'this'

The keyword 'this' refers to the object responsible for executing the current function.

In JavaScript, 'this' is used a bit differently, than in other languages like C++ or Java.

It is entirely determined by **how** a function is called, and not **where** it is defined.

```javascript
  class NameGenerator {
    constructor() {
      const btn = document.querySelector['button'];
      this.names = ['Max', 'Anna', 'George']; // 'this' will refer to the constructor
      this.currentName = 0; 
      btn.addEventListener ('click', this.addName); // but 'this' will refer to the button object
    }
```

We can simplify the usage of 'this', by the formula: 

![image info](./pictures/this_formula.png)


If called in an object method, 'this' references the object itself.

```javascript
  class NameGenerator {
    constructor() {
      const btn = document.querySelector['button'];
      this.names = ['Max', 'Anna', 'George']; // 'this' will refer to the constructor
      this.currentName = 0; 
      btn.addEventListener ('click', this.addName); // but 'this' will refer to the button object
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
In the constructor, 'this' is used to attach parts of the class together.

If called anywhere else, 'this' references the global object.

```javascript
  function ask(question, yes, no) {
  if (confirm(question)) yes();
  else no();
}

ask(
  "Do you agree?",
  function() { alert("You agreed."); },
  function() { alert("You canceled the execution."); }
);
```

There are a few ways to handle and control what 'this' refers to.


### References

1. Defining 'this' : formula [Understanding Functions and 'this' In The World of ES2017](https://youtu.be/gvicrj31JOM)
2. 'this' in object method example: Project Documentation: [X_PROJECT_DOC_URL_X](X_PROJECT_DOC_URL_X)
3. 'this' in regular functions example: Project Documentation: [X_PROJECT_DOC_URL_X](X_PROJECT_DOC_URL_X)
