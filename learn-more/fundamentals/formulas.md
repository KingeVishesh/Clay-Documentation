---
cover: >-
  ../../.gitbook/assets/62ffcf409d74150b0191f72f_Header - claymation black
  (2).png
coverY: 0
---

# Formulas

## Types of formulas

**Operators.** Run simple calculations like`a + b`, `a * b`, `a / b`, `a != b`

**Functions.** Run more complex formulas by adding some custom code (see more below)

**Primitives.** Run formulas combining different types of data

* **Numbers:** `5`, `42`, `-1`, `3.14`, etc.
* **Strings:** `"foo"`, `'Clay'`, they need to be in `"` or `'`
* **Booleans:** `true`, `false`
* **Lists:** `[ "do", "ray", "me" ]`

**Javascript operators we support:**&#x20;

* `+`, `-` (in their unary and binary forms, i.e. `5-3` and `-3` or `+3`)
* `~` - bitwise negation
* `!` - logical negation
* `*`, `/` - multiplication, division
* `||`, `&&` - logical OR, logical AND
* `|`, `&`, `^` - bitwise OR, bitwise AND, bitwise XOR
* `=` - equality test
* `!=` - inequality test
* `<`, `>`, `<=`, `>=` - comparison operators
* `<<`, `>>` - bit shift operators
* `%` - modulo

## Popular formulas

### **Splitting first and last names into two columns**

* Split a name or a term into two columns, i.e. **Split Full Name into First Name & Last Name**
* e.g. Split full name into first and last names First name: `{{ "Full Name" }}.split(' ')[0]` Last name: `{{ "Full Name" }}.split(' ')[1]`

### **Sanitize URLs**

* Clean urls if they include unwanted characters like `https://` or unwanted paths like `/index.html`, i.e. **Strip** [**https://www.loom.com/about-us**](https://www.loom.com/about-us) **down to just** [**loom.com**](http://loom.com)
* `{{ "Domain" }}.replace("https://", "").replace("www.", "").split("/")[0]`

### Conditional runs

* Run actions based on specific conditions, e.g. **run only if another action has run,** run only if a prior action has returned a specific output, run only if box is checked
*   The formula is applied via the action input and reads `**if( {{condition}} , {{input}} )**`

    In this example we want to run Clearbit only if BuiltWith has returned a match for Hubspot. We will apply `**if( {{ "Uses Hubspot" }} , {{Domain}} )**`

### **Automatic checkbox**

* Write a formula to show a checkbox in your table, checked or unchecked based on conditions of your choice, i.e. **If A is true, show checkbox in this row**
* `if({{ "Email" }}.includes("gmail"))`
* Set your column type to checkbox, this will allow it to automatically check and uncheck depending on your true/false formula

### **Tier or filter your leads by grouping**

* Create buckets that records fall into using ternary operators that can help tiering or filtering, i.e. **If A is between B and C, label D**
* E.g. Segment companies according to employee count ranges of 1000+, 500-1000, 100-500, 100-500, 50-100, 25-50, 5-25 `if({{ "Employee Count" }} >= 1000 ? "1000+" : {{ "Employee Count" }} >= 500 ? "500-1000" : {{ "Employee Count" }} >= 100 ? "100-500": {{ "Employee Count" }} >= 50 ? "50-100" : {{ "Employee Count" }} >= 25 ? "25-50" : {{ "Employee Count" }} >= 5 ? "5-25":"1-5")`

### Scoring leads

Automate your lead scoring and use a checkbox to identify qualified leads based on certain properties in your table ⚡️ Here are a few examples to get you started:

* **Checkbox for work emails only:** `if(["hotmail","gmail", "yahoo", "icloud", "outlook", "comcast", "proton"].some((domain)=>{{{ "Email Address" }}.includes(domain)}), false, true)`
* **Checkbox for specific industries:** `if({{ "Industry" }} && ["software", "internet", "information technology"].some((i)=>{{{ Industry }}.toLowerCase().includes(i)}), true, false)`
* **Checkbox if company has a certain amount of employees:** `if({{ "Employee Count" }} && {{ "Employee Count" }} > 50 && {{ "Employee Count" }} < 200, true, false)`

And now, get creative and combine! Once you've set up all of your individual checkbox columns, add a `Final Scoring` using a chain of operators to flow through the qualification logic.

* i.e.`!{{ "Only work emails" }} ? false : {{ "In ideal industry" }} ? true : {{ "At least 20 employees"}} ? true : false`

## Add some code

**Clay formulas can support:**

* **Lodash** → `_` will refer to lodash, so `_.chunk( [ 10, 20, 30, 40 ], 2 )` will result in `[ [ 10, 20 ], [ 30, 40 ] ]`
* **Lambda functions** → the syntax for lambda function is: `(arg1, arg2, ...) => { expression }`. The extra `{}` are necessary. The above is equal to Javascript's `(arg1, arg2, ...)=> expression` and `(arg1, arg2, ...)=> { return expression }`.
* **Javascript Object functions** → Eg. strings do have `.length` property, and methods like `.split()` or `.substring()`. Arrays have `.length`, `.concat`, `.indexOf`, `.map`, `.filter` etc.
