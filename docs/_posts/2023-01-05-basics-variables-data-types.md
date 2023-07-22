---
layout: default
title: Basics of javascript 
description: Basic Easy to learn Tutorial for Absolute Beginers 
date: 2023-01-05 00:00:00
---

# Basics of Javascript 

We will cover basic concepts of Javascript with like Variables , Datatypes, Strict Etc 

1. [Use Strict](#use-strict) 
1.1 [Invalid Example of Strict](#invalid-examples-of-strict)
2. variables
3. datatypes 
4. Type Conversions
5. Basic Operators, maths

## Use Strict 
The "use strict" directive was new in ECMAScript version 5.
It is not a statement, but a literal expression, ignored by earlier versions of JavaScript.
The purpose of "use strict" is to indicate that the code should be executed in "strict mode".
With strict mode, you can not, for example, use undeclared variables.

Strict mode is declared by adding "use strict"; to the beginning of a script or a function.
Declared at the beginning of a script, it has global scope (all code in the script will execute in strict mode):

### Invalid Examples of Strict 
See Below **[code]({{ site.github.repository_url }}/blob/main/src/basic-varaible-datatypes/strict-example-1.js)** as example in file ``
```js
"use strict";
x = 3.14;  // This will cause Error as x is not defined 
console.log(x)
```
Output of this will be  Error :x:  due to non declaration of a variable 
```
iddhirajpantoji@Siddhirajs-MacBook-Pro basic-varaible-datatypes % node strict-example-1.js 
/Users/siddhirajpantoji/Siddhiraj/nodejs-beginer-guide/src/basic-varaible-datatypes/strict-example-1.js:2
x = 3.14; 
  ^

ReferenceError: x is not defined
    at Object.<anonymous> (/Users/siddhirajpantoji/Siddhiraj/nodejs-beginer-guide/src/basic-varaible-datatypes/strict-example-1.js:2:3)
    at Module._compile (node:internal/modules/cjs/loader:1256:14)
    at Module._extensions..js (node:internal/modules/cjs/loader:1310:10)
    at Module.load (node:internal/modules/cjs/loader:1119:32)
    at Module._load (node:internal/modules/cjs/loader:960:12)
    at Function.executeUserEntryPoint [as runMain] (node:internal/modules/run_main:81:12)
    at node:internal/main/run_main_module:23:47

Node.js v18.16.1
```

See Another **[example]({{ site.github.repository_url }}/blob/main/src/basic-varaible-datatypes/strict-example-2.js)**
```js
"use strict";
myFunction();

function myFunction() {
  y = 3.14;   // This will also cause an error because y is not declared
}
```
Output Will be 
```
siddhirajpantoji@Siddhirajs-MacBook-Pro basic-varaible-datatypes % node strict-example-2.js 
/Users/siddhirajpantoji/Siddhiraj/nodejs-beginer-guide/src/basic-varaible-datatypes/strict-example-2.js:5
  y = 3.14;   // This will also cause an error because y is not declared
    ^

ReferenceError: y is not defined
    at myFunction (/Users/siddhirajpantoji/Siddhiraj/nodejs-beginer-guide/src/basic-varaible-datatypes/strict-example-2.js:5:5)
    at Object.<anonymous> (/Users/siddhirajpantoji/Siddhiraj/nodejs-beginer-guide/src/basic-varaible-datatypes/strict-example-2.js:2:1)
    at Module._compile (node:internal/modules/cjs/loader:1256:14)
    at Module._extensions..js (node:internal/modules/cjs/loader:1310:10)
    at Module.load (node:internal/modules/cjs/loader:1119:32)
    at Module._load (node:internal/modules/cjs/loader:960:12)
    at Function.executeUserEntryPoint [as runMain] (node:internal/modules/run_main:81:12)
    at node:internal/main/run_main_module:23:47

Node.js v18.16.1
```

:warning: Strict Mode should be activated at the strat of file "use strict";