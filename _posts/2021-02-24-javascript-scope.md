---
layout: post
title:  "Javascript Scope"
categories: RAILS
tags: javascript scope
---


# Javascript Scope
    Scope determine variables accessability .
## Types of Scope
 - Global Scope
 - Local Scope

### Global Scope
  These are variables declared outside of a function
  as a result all scripts and functions have access to it.
  ```javascript
  // varriable declared here are globally scoped
     var plant = "rosemary" ;

  function garden(){

      return plant
  }
 ```
**Assigning a value to a variable that hasn't been declared will automatically become Globally scope even if the value is assigned inside a function.**

```javascript
    myFunction();
    console.log(carName)

    function myFunction() {
    carName = "Volvo";
    }

    // "Volvo"

 ```
 This is due to Javascript hoisting behaviour which involves by default moving all declarations to the top of the current script, scope or function.

### Local Scope aka block level scope

