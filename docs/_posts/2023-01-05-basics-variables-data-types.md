---
layout: default
title: Basics of javascript 
description: Basic Easy to learn Tutorial for Absolute Beginers 
date: 2023-01-05 00:00:00
---

# Basics of Javascript 

We will cover basic concepts of Javascript with like Variables , Datatypes, Strict Etc 

1. [Use Strict](#use-strict) 
    1. [Why Strict Mode ](#why-strict-mode)
    2. [Not Allowed in Strict Mode](#not-allowed-in-strict-mode)
    3. Behaviour of this keyword 
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

### Why Strict Mode 
Strict mode makes it easier to write "secure" JavaScript.
Strict mode changes previously accepted "bad syntax" into real errors.
As an example, in normal JavaScript, mistyping a variable name creates a new global variable. In strict mode, this will throw an error, making it impossible to accidentally create a global variable.
In normal JavaScript, a developer will not receive any error feedback assigning values to non-writable properties.
In strict mode, any assignment to a non-writable property, a getter-only property, a non-existing property, a non-existing variable, or a non-existing object, will throw an error.

### Not allowed in Strict mode  
Below Examples are of what possible things are not allowed in strict Mode.
Each sample can be copied and saved in your local file. lets consider it `example.js`.
Navigate  to the directory from Command prompt execute with below Command 
```shell
node example.js
```

Consider below  **[Example]({{ site.github.repository_url }}/blob/main/src/basic-varaible-datatypes/strict-invalid-example-1.js)**
```js
"use strict";
x = 3.14;  // This will cause Error as x is not defined 
console.log(x)
```

See Another **[example]({{ site.github.repository_url }}/blob/main/src/basic-varaible-datatypes/strict-invalid-example-2.js)**
```js
"use strict";
myFunction();

function myFunction() {
  y = 3.14;   // This will also cause an error because y is not declared
}
```
Lets Consider Third **[example]({{ site.github.repository_url }}/blob/main/src/basic-varaible-datatypes/strict-invalid-example-3.js)** of Failure

```js
x = 3.14;       // This will not cause an error.
myFunction();

function myFunction() {
  "use strict";
  y = 3.14;   // This will cause an error
}
```
:warning: Objects are variables too 
Using an object, without declaring it, is not allowed: ***[code]({{ site.github.repository_url }}/blob/main/src/basic-varaible-datatypes/strict-invalid-example-4.js)***
```js
"use strict";
x = {p1:10, p2:20};      // This will cause an error
```

Deleting a variable (or object) is not allowed. **[code]({{ site.github.repository_url }}/blob/main/src/basic-varaible-datatypes/strict-invalid-example-5.js)**
```js
"use strict";
let x = 3.14;
delete x;  // SyntaxError: Delete of an unqualified identifier in strict mode.
```

Deleting a function is not allowed. **[code]({{ site.github.repository_url }}/blob/main/src/basic-varaible-datatypes/strict-invalid-example-6.js)**
```js
"use strict";
function x(p1, p2) {};
delete x;                // This will cause an error 
```
Duplicating a parameter name is not allowed: **[code]"use strict";
let x = 010;   // SyntaxError: Octal literals are not allowed in strict mode.
```js
"use strict";
function x(p1, p1) {};  // SyntaxError: Duplicate parameter name not allowed in this context
```

Octal numeric literals are not allowed: **[code]({{ site.github.repository_url }}/blob/main/src/basic-varaible-datatypes/strict-invalid-example-8.js)**
```js
"use strict";
let x = 010;   // SyntaxError: Octal literals are not allowed in strict mode.
```

Octal escape characters are not allowed: **[code]({{ site.github.repository_url }}/blob/main/src/basic-varaible-datatypes/strict-invalid-example-9.js)**
```js
"use strict";
let x = "\010";    // SyntaxError: Octal escape sequences are not allowed in strict mode.
```
Writing to a read-only property is not allowed: **[code]({{ site.github.repository_url }}/blob/main/src/basic-varaible-datatypes/strict-invalid-example-10.js)**

```js
"use strict";
const obj = {};
Object.defineProperty(obj, "x", {value:0, writable:false});

obj.x = 3.14;  
```


:warning: Strict Mode should be activated at the strat of file "use strict";