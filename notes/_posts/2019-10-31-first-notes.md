---
layout: post
title: 'JS in all its glory'
category: notes
date: 2019-09-30 21:55:44 -0400
author: EG
---


# Javascript *in all its glory*

- JavaScript Statements
- JavaScript statements are composed of:
    - Values, Operators, Expressions, Keywords and Comments.
- Statements are executed, one by one, in the same order as they are written.
- JavaScript programs (and JavaScript statements) are often called JavaScript code.
- Expression
- An *expression* is any valid unit of code that resolves to a value.
- 2 Types of expression
- **with side effects** *(for example: those that assign value to a variable)*
- those that in some sense evaluate and therefore **resolve to a value**
- The value that it returns is refered as the **Return Value** of the expression
- Debugging
    - `alert()` function, which creates a simple alert in the browser window:
- Semicolons
  ## **Using semicolons is optional**
- Javascript runs multiple phases before excuting your code
1. The first pass is to parse the syntax of your code *aka compilation phase.*
2. The second pass is to initialize variables and functions and store them in memory. *aka compilation phase.*
3. The third pass is to actually execute the code line-by-line. *execution phase." It’s where the code is run top-down, left-to-right.*
- Referencing Functions, Keywords, and Variables

 ## **Functions**
- include a pair of trailing parentheses to mark it as such, *e.g., `myFunction()`* -**Keyword** or **Variable**
- There’ll be no parentheses: `myVariable`, `debugger`, `if...else`, etc. ## Establish Good JavaScript Learning Habits
- Read all the docs
- Always have a conssole window open
- Code code code your heart out always

[Learn.co Intro](https://github.com/learn-co-curriculum/js-basics-intro-to-javascript-readme)

[MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Introduction#What_is_JavaScript)

## Data Types
 > In JavaScript, concrete instances of data can be categorized into abstract names called “data type” or, more simply, “type.” * Define a Data Type

- Everything in Javascript is Data *except*

1. **Operators** `+`,`!`,`<=`, etc 
2. **Reserved words** `function`,`for`,`debugger`, etc
- Everything In JS falls in one of its **7 Data Types:**`numbers`, `strings`, `booleans`, `symbols`, `objects`, `null`, and `undefined`.
- Basic Type Checking with the `typeof` Operator - `typeof` accepts one argument, the piece of data that we’d like to know the type of.
- > **CAREFUL** `typeof` is an operator, just like `+` or `!`. We get used to operators being only one character, but JavaScript (and many other languages) **have operators with more than one character**. As such, we **don’t need parentheses with `typeof`. That said, JavaScript also supports ()** * Identify JavaScript’s **Seven** Basic Data Types *Numbers* 1. Numbers - unline other language that divide up their number types into intergers, decimals,doubles, floats etc., in order to be as accurate as possible **JS doesn’t** **JavaScript only has a single, all- encompassing number type:**
  
```javascript 
    typeof 42; //=> “number”

    typeof 3.141592653589793;
        //=> "number"
        
        typeof 5e-324;
        //=> "number"
        
        typeof -Infinity;
        //=> "number"
``` 

> **Think About This** As JavaScript has become a language for the back-end as well as the front-end, it's imprecision around numbers keep it from entering many banking or engineering applications where precision is vital.  

 1. Strings  
     - A string consists of a matching pair of `'single quotes'`, `"double quotes"`, or ``backticks`` with zero or more characters in between  
     - Even empty strings are strings  
 2. Booleans
     - Booleans can only be `true` or `false`  
     > Play a big role in `if` statements and looping in JS.
     - Play a big role in conditional statements. 
     ```javascript
            typeof true;
            //=> "boolean"
            
            typeof false;
            //=> "boolean"
     ```
 3. Objects
     - JS `Objects` a collection of properties bounded by curly braces `{}` , similar to a hash in Ruby or dictionary in Python.  
     - the properties can **point to any values of any data type even other objects.**   
      ```javascript 
            {
            "name": "JavaScript",
            "createdBy": {
                "firstName": "Brendan",
                "lastName": "Eich"
            },
            "firstReleased": 1995,
            "isAwesome": true
            }
            
            typeof {}
            //=> "object"
      ```

       > From JavaScript's perspective, what we call `"arrays"` are just special-cases of an `"object"` where the keys are all `numbers`. So while JavaScript has `Array`s like `let dogs = ["Byron", "Cubby", "Boo Radley", "Luca"]`, JavaScript really thinks that `typeof dogs` is `"object"`.  
          - *`let` declares a block scope local variable, optionally initializing it to a value.*  
          ```javascript
            let dogs = ['Byron', 'Cubby', 'Boo Radley', 'Luca'];
            typeof dogs;
            //=> "object"
          ```  
          - Symbols
          - Symbols are a relatively new data type (introduced in ES2015) that's primarily used as an alternate way to add properties to objects. 
    
    2.  `null`
          - > The `null` data type represents an intentionally absent object.
          - represents intentionally missing return object. 
          - > example, if a piece of code returns an object when it successfully executes, we could have it return `null` in the event of an error. Confusingly, the `typeof` operator returns "object" when called with `null`:
    3. `undefined`
          - > The bane of many JS developers, `undefined` is a bit of a misnomer. Instead of 'not defined,' **it actually means something more like 'not yet assigned a value.'**
    
         - ```javascript 
             typeof undefined;
             //=> "undefined"
                
             let unassignedVariable;
             typeof unassignedVariable;
             //=> "undefined"
                
             unassignedVariable = '';
             typeof unassignedVariable;
             //=> "string"
             ```   
        - > Any variable declared but not defined will be `undefined` until a value is assigned.  
      
    
    4. Primitve Types
          - >  everything except `object` — are primitive. All this means is that they *represent single values*, such as `7` or `"hello"` or `false`, instead of a collection of values.

- Describe Interactions Between Data of Various Types in JavaScript

string to be add to other strings. `javascript "this amazing"+" word"; //=> this amazing word`
    - Programming language has its own rules governing the ways in which we can operate on data of a given type. eg., numbers can be added to other numbers,

        3 - 2;//=> 1

    - **No matter what weird combination of types you give it, JavaScript won’t throw an error and will return something *(though that something might make no sense at all)*.**
    sometimes it makes sense

        'High ' + 5 + '!';//=> "High 5!"

    sometimes [comical](https://www.destroyallsoftware.com/talks/wat)

        null ** 2; // null to the power of 2//=> 0undefined ** null; // undefined to the power of null//=> 1{}+{}; // empty object plus empty object//=> "[object Object][object Object]" <-- That's a string!

    [learn.con - Data Types](https://github.com/learn-co-curriculum/js-basics-data-types-readme)