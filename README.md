# JavaScript Documentation
## Topics
- Terms
- Data Types
- Modules
- Functions / Methods
- Object Oriented Programming (OOP)
- Scope
- Asynchronious Development
- Debugging
### Terms
#### scope

  The scope tells you where a variable is available and accessable. Like is it available inside the whole class or just in a specific function.

#### promise

  A promise is a object that represents the eventual completion or failure of a async operation and its resulting value. It has three states (pending, fulfilled, rejected).

### Data Types
There are several datatypes in js like in any other script or programming language.
Primitve datatypes:
- Undefined
- Null
- Number
- String
- Boolean
- BigInt
- Symbol (to generate access keys)
  
Non primitive datatypes:
- Objects / Arrays

### Modules
In JavaScript you are able to import and export modules to reuse use whereever you want.
There are several ways to import libraries nowadays.
#### Import default export from module
```import myDefault from './path/of/module/module.js'```
#### Import all exports from module
```import * as variableName from './path/of/module/module.js'```
#### Import specific exports out of a module
```import {functionA, functionB} from './path/of/module/module.js'```
#### Export written function
```js
function exampleFunction(param) {
  return param;
}

module.exports.exampleFunction = exampleFunction;
```
#### Export function directly
```js
module.exports.exampleFunction = function(param) {
  return param;
}
```

### Functions / Methods
#### Basic function
```js
function exampleFunction(param) {
  return param;
}
```
#### Callback function
A callback function is a function passed as an argument to another function.
```js
function myDisplayer(some) {
  document.getElementById("demo").innerHTML = some;
}

function myCalculator(num1, num2, myCallback) {
  let sum = num1 + num2;
  myCallback(sum);
}

myCalculator(5, 5, myDisplayer);
```

### Object Oriented Programming (OOP)
- Classes are templates for objects.
- JavaScript calls a constructor method when we create a new instance of a class.
- Inheritance is when we create a parent class with properties and methods that we can extend to child classes.
- We use the extends keyword to create a subclass.
- The super keyword calls the constructor() of a parent class.
- Static methods are called on the class, but not on instances of the class.

Here we have a basic class with all the topics from above:
```js
class HospitalEmployee {
  constructor(name) {
    this._name = name;
    this._remainingVacationDays = 20;
  }
  
  get name() {
    return this._name;
  }
  
  get remainingVacationDays() {
    return this._remainingVacationDays;
  }
  
  takeVacationDays(daysOff) {
    this._remainingVacationDays -= daysOff;
  }

  static generatePassword() {
    return Math.floor(Math.random() * 10000);
  }
}

class Nurse extends HospitalEmployee {
  constructor(name, certifications) {
    super(name);
    this._certifications = certifications;
  } 
  
  get certifications() {
    return this._certifications;
  }
  
  addCertification(newCertification) {
    this.certifications.push(newCertification);
  }
}

const nurseOlynyk = new Nurse('Olynyk', ['Trauma','Pediatrics']);
nurseOlynyk.takeVacationDays(5);
console.log(nurseOlynyk.remainingVacationDays);
nurseOlynyk.addCertification('Genetics');
console.log(nurseOlynyk.certifications);
```
### Asynchronious Development

### Debugging
