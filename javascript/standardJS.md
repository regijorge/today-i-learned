# Standard JS
* [Ref](https://standardjs.com/rules.html)
* [VS Code Extension](https://marketplace.visualstudio.com/items?itemName=chenxsan.vscode-standardjs)

## Rules

### 1) 2 spaces indentation
```
```

### 2) Use single quotes for strings except to avoid escaping.
```
console.log('hello there')    // ✓ ok
console.log("hello there")    // ✗ avoid

console.log(`hello ${name}`)  // ✓ ok
console.log(`hello there`)    // ✗ avoid
```

### 3) No unused variables.
```
function myFunction () {
  var result = something()   // ✗ avoid
}
```

### 4) Add a space after keywords.
```
if (condition) { ... }   // ✓ ok
if(condition) { ... }    // ✗ avoid
```

### 5) Add a space before a function declaration's parentheses
```
function name (arg) { ... }   // ✓ ok
function name(arg) { ... }    // ✗ avoid

run(function () { ... })      // ✓ ok
run(function() { ... })       // ✗ avoid
```

### 6) Always use === instead of ==
Exception: obj == null is allowed to check for null || undefined
```
if (name === 'John')   // ✓ ok
if (name == 'John')    // ✗ avoid

if (name !== 'John')   // ✓ ok
if (name != 'John')    // ✗ avoid
```

### 8) Infix operators must be spaced
```
// ✓ ok
var x = 2
var message = 'hello, ' + name + '!'

// ✗ avoid
var x=2
var message = 'hello, '+name+'!'
```

### 9) Commas should have a space after them
```
// ✓ ok
var list = [1, 2, 3, 4]
function greet (name, options) { ... }

// ✗ avoid
var list = [1,2,3,4]
function greet (name,options) { ... }
```

### 10) Keep else statements on the same line as their curly braces
```
// ✓ ok
if (condition) {
  // ...
} else {
  // ...
}

// ✗ avoid
if (condition) {
  // ...
}
else {
  // ...
}

```

### 11) For multi-line if statements, use curly braces
```
// ✓ ok
if (options.quiet !== true) console.log('done')

// ✓ ok
if (options.quiet !== true) {
  console.log('done')
}

// ✗ avoid
if (options.quiet !== true)
  console.log('done')
```

### 12) Always handle the err function parameter
```
// ✓ ok
run(function (err) {
  if (err) throw err
  window.alert('done')
})

// ✗ avoid
run(function (err) {
  window.alert('done')
})
```

### 13) Declare browser globals with a /* global */ comment
Exceptions are: window, document, and navigator.
Prevents accidental use of poorly-named browser globals like open, length, event, and name.
```
/* global alert, prompt */

alert('hi')
prompt('ok?')
```
Explicitly referencing the function or property on window is okay too, though such code will not run in a Worker which uses self instead of window.
```
window.alert('hi')   // ✓ ok
```

### 14) Multiple blank lines not allowed
```
// ✓ ok
var value = 'hello world'
console.log(value)

// ✗ avoid
var value = 'hello world'


console.log(value)
```

### 15) For the ternary operator in a multi-line setting, place ? and : on their own lines
```
// ✓ ok
var location = env.development ? 'localhost' : 'www.api.com'

// ✓ ok
var location = env.development
  ? 'localhost'
  : 'www.api.com'

// ✗ avoid
var location = env.development ?
  'localhost' :
  'www.api.com'
```

### 16) For var declarations, write each declaration in its own statement
```
// ✓ ok
var silent = true
var verbose = true

// ✗ avoid
var silent = true, verbose = true

// ✗ avoid
var silent = true,
    verbose = true
```

### 17) Wrap conditional assignments with additional parentheses. This makes it clear that the expression is intentionally an assignment (=) rather than a typo for equality (===)
```
// ✓ ok
while ((m = text.match(expr))) {
  // ...
}

// ✗ avoid
while (m = text.match(expr)) {
  // ...
}
```

### 18) Add spaces inside single line blocks
```
function foo () { return true }  // ✓ ok

function foo () {return true}    // ✗ avoid
```

### 19) Use camelcase when naming variables and functions
```
function myFunction () { }     // ✓ ok
function my_function () { }    // ✗ avoid

var myVar = 'hello'            // ✓ ok
var my_var = 'hello'           // ✗ avoid
```

### 20) Trailing commas not allowed
```
var obj = {
  message: 'hello',   // ✗ avoid
}
```

### 21) Commas must be placed at the end of the current line
```
var obj = {
  foo: 'foo',
  bar: 'bar'   // ✓ ok
}

var obj = {
  foo: 'foo'
  ,bar: 'bar'   // ✗ avoid
}
```

### 22) Dot should be on the same line as property
```
console
  .log('hello') // ✓ ok

console.
    log('hello')  // ✗ avoid
```

### 23) Files must end with a newline
```

```

### 24) No space between function identifiers and their invocations
```
console.log('hello')  // ✓ ok

console.log ('hello') // ✗ avoid
```

### 25) Add space between colon and value in key value pairs
```
var obj = { 'key': 'value' }     // ✓ ok

var obj = { 'key' : 'value' }    // ✗ avoid
var obj = { 'key' :'value' }     // ✗ avoid
var obj = { 'key':'value' }      // ✗ avoid
```

### 26) Constructor names must begin with a capital letter
```
function Animal () {}
var dog = new Animal()    // ✓ ok

function animal () {}
var dog = new animal()    // ✗ avoid
```

### 27) Constructor with no arguments must be invoked with parentheses
```
function Animal () {}
var dog = new Animal()  // ✓ ok
var dog = new Animal    // ✗ avoid
```

### 28) Objects must contain a getter when a setter is defined
```
var person = {
  set name (value) {
    this._name = value
  },
  get name () {         // ✓ ok
    return this._name
  }
}

var person = {
  set name (value) {    // ✗ avoid
    this._name = value
  }
}
```

### 29) Constructors of derived classes must call super
```
class Dog extends Animal {
  constructor () {
    super()             // ✓ ok
    this.legs = 4
  }
}

class Dog {
  constructor () {
    super()             // ✗ avoid
    this.legs = 4
  }
}

class Dog extends Animal {
  constructor () {      // ✗ avoid
    this.legs = 4
  }
}
```

### 30) Use array literals instead of array constructors
```
var nums = [1, 2, 3]            // ✓ ok
var nums = new Array(1, 2, 3)   // ✗ avoid
```

### 31) Avoid using arguments.callee and arguments.caller
```
function foo (n) {
  if (n <= 0) return

  foo(n - 1)                // ✓ ok
}

function foo (n) {
  if (n <= 0) return

  arguments.callee(n - 1)   // ✗ avoid
}
```

### 32) Avoid modifying variables of class declarations
```
class Dog {}
Dog = 'Fido'    // ✗ avoid
```

### 33) Avoid modifying variables declared using const
```
const score = 100
score = 125       // ✗ avoid
```

### 34) Avoid using constant expressions in conditions (except loops)
```
if (x === 0) {  // ✓ ok
  // ...
}

while (true) {  // ✓ ok
  // ...
}

if (false) {    // ✗ avoid
  // ...
}
```

### 35) No control characters in regular expressions
```
var pattern = /\x20/    // ✓ ok
var pattern = /\x1f/    // ✗ avoid
```

### 36) No debugger statements
```
function sum (a, b) {
  debugger      // ✗ avoid
  return a + b
}
```

### 37) No delete operator on variables
```
var name
delete name     // ✗ avoid
```

### 38) No duplicate arguments in function definitions
```
function sum (a, b, c) {  // ✓ ok
  // ...
}

function sum (a, b, a) {  // ✗ avoid
  // ...
}
```

### 39) No duplicate name in class members
```
class Dog {
  bark () {}
  bark () {}    // ✗ avoid
}
```

### 40) No duplicate keys in object literals
```
var user = {
  name: 'Jane Doe',
  name: 'John Doe'    // ✗ avoid
}
```

### 41) No duplicate case labels in switch statements
```
switch (id) {
  case 1:
    // ...
  case 1:     // ✗ avoid
}
```

### 42) Use a single import statement per module
```
import { myFunc1, myFunc2 } from 'module' // ✓ ok

import { myFunc1 } from 'module'
import { myFunc2 } from 'module'          // ✗ avoid
```

### 43) No empty character classes in regular expressions
```
const myRegex = /^abc[a-z]/   // ✓ ok
const myRegex = /^abc[]/      // ✗ avoid
```

### 44) No empty destructuring patterns
```
const { a: { b } } = foo      // ✓ ok
const { a: {} } = foo         // ✗ avoid
```

### 45) No using eval()
```
var result = user[propName]             // ✓ ok
eval( "var result = user." + propName ) // ✗ avoid
```

### 46) No reassigning exceptions in catch clauses
```
try {
  // ...
} catch (e) {
  const newVal = 'new value'  // ✓ ok
}

try {
  // ...
} catch (e) {
  e = 'new value'             // ✗ avoid
}
```

### 47) No extending native objects
```
Object.prototype.age = 21     // ✗ avoid
```

### 48) Avoid unnecessary function binding
```
const name = function () {
  this.getName()
}.bind(user)    // ✓ ok

const name = function () {
  getName()
}.bind(user)    // ✗ avoid
```

### 49) Avoid unnecessary boolean casts
```
const result = true
if (result) {     // ✓ ok
  // ...
}

const result = true
if (!!result) {   // ✗ avoid
  // ...
}
```

### 50) No unnecessary parentheses around function expressions
```
const myFunc = function () { }     // ✓ ok
const myFunc = (function () { })   // ✗ avoid
```

### 510) Use break to prevent fallthrough in switch cases
```
switch (filter) {
  case 1:
    doSomething()
    break           // ✓ ok
  case 2:
    doSomethingElse()
}

switch (filter) {
  case 1:
    doSomething()
    // fallthrough  // ✓ ok
  case 2:
    doSomethingElse()
}

switch (filter) {
  case 1:
    doSomething()    // ✗ avoid
  case 2:
    doSomethingElse()
}
```

### 52) No floating decimals
```
const discount = 0.5     // ✓ ok
const discount = .5      // ✗ avoid
```

### 53) Avoid reassigning function declarations
```
function myFunc () { }
myFunc = myOtherFunc    // ✗ avoid
```

### 54) No reassigning read-only global variables
```
window = {}     // ✗ avoid
```

### 55) No implied eval()
```
setTimeout(function () { alert('Hello world') })     // ✓ ok

setTimeout("alert('Hello world')")                   // ✗ avoid
```

### 56) No function declarations in nested blocks
```
if (authenticated) {
  function setAuthUser () {}    // ✗ avoid
}
```

### 57) No invalid regular expression strings in RegExp constructors
```
RegExp('[a-z]')   // ✓ ok
RegExp('[a-z')    // ✗ avoid
```

### 58) No irregular whitespace
```
function myFunc () /*<NBSP>*/{}   // ✗ avoid
```

### 59) No using __iterator__
```
Foo.prototype.__iterator__ = function () {}   // ✗ avoid
```

### 60) No labels that share a name with an in scope variable
```
var score = 100
function game () {
  score: while (true) {      // ✗ avoid
    score -= 10
    if (score > 0) continue score
    break
  }
}
```

### 61) No label statements
```
label:
  while (true) {
    break label     // ✗ avoid
  }
```

### 62) No unnecessary nested blocks
```
function myFunc () {
  myOtherFunc()       // ✓ ok
}

function myFunc () {
  {                   // ✗ avoid
    myOtherFunc()
  }
}
```

### 63) Avoid mixing spaces and tabs for indentation
```

```

### 64) Do not use multiple spaces except for indentation
```
const id = 1234       // ✓ ok
const id =    1234    // ✗ avoid
```

### 65) No multiline strings
```
const message = 'Hello \
                 world'     // ✗ avoid
```

### 66) No new without assigning object to a variable
```
const character = new Character()   // ✓ ok
new Character()                     // ✗ avoid
```

### 67) No using the Function constructor
```
var sum = new Function('a', 'b', 'return a + b')    // ✗ avoid
```

### 68) No using new require
```
const myModule = new require('my-module')    // ✗ avoid
```

### 69) No using the Symbol constructor
```
const foo = new Symbol('foo')   // ✗ avoid
```

### 70) No using primitive wrapper instances
```
const message = new String('hello')   // ✗ avoid
```

### 71) No calling global object properties as functions
```
const math = Math()   // ✗ avoid
```

### 72) No octal literals
```
const decimal = 34        // ✓ ok
const octalString = '042' // ✓ ok
const octal = 042         // ✗ avoid
```

### 73) No octal escape sequences in string literals
```
const copyright = 'Copyright \251'  // ✗ avoid
```

### 74) Avoid string concatenation when using __dirname and __filename
```
const pathToFile = path.join(__dirname, 'app.js')   // ✓ ok
const pathToFile = __dirname + '/app.js'            // ✗ avoid
```

### 75) Avoid using __proto__. Use getPrototypeOf instead
```
const foo = Object.getPrototypeOf(obj)  // ✓ ok
const foo = obj.__proto__               // ✗ avoid
```

### 76) No redeclaring variables
```
let name = 'John'
name = 'Jane'         // ✓ ok

let name = 'John'
let name = 'Jane'     // ✗ avoid
```

### 77) Avoid multiple spaces in regular expression literals
```
const regexp = /test {3}value/  // ✓ ok
const regexp = /test value/     // ✓ ok

const regexp = /test   value/   // ✗ avoid
```

### 78) Assignments in return statements must be surrounded by parentheses
```
function sum (a, b) {
  return (result = a + b)   // ✓ ok
}

function sum (a, b) {
  return result = a + b     // ✗ avoid
}
```

### 79) Avoid assigning a variable to itself
```
name = name   // ✗ avoid
```

### 80) Avoid comparing a variable to itself
```
if (score === score) {}   // ✗ avoid
```

### 81) Avoid using the comma operator
```
if (doSomething(), !!test) {}   // ✗ avoid
```

### 82) Restricted names should not be shadowed
```
let undefined = 'value'     // ✗ avoid
```

### 83) Sparse arrays are not allowed
```
let fruits = ['apple',, 'orange']       // ✗ avoid
```

### 84) Tabs should not be used
```

```

### 85) Regular strings must not contain template literal placeholders
```
const message = `Hello ${name}`   // ✓ ok
const message = 'Hello ${name}'   // ✗ avoid
```

### 86) super() must be called before using this
```
class Dog extends Animal {
  constructor () {
    this.legs = 4     // ✗ avoid
    super()
  }
}
```

### 87) Only throw an Error object.
```
throw new Error('error')    // ✓ ok
throw 'error'               // ✗ avoid
```

### 88) Whitespace not allowed at end of line
```

```

### 89) Initializing to undefined is not allowed
```
let name
name = 'value'          // ✓ ok

let name = undefined    // ✗ avoid
```

### 90) No unmodified conditions of loops
```
for (let i = 0; i < items.length; i++) {...}    // ✓ ok
for (let i = 0; i < items.length; j++) {...}    // ✗ avoid
```

### 91) No ternary operators when simpler alternatives exist
```
let score = val || 0          // ✓ ok
let score = val ? val : 0     // ✗ avoid
```

### 92) No unreachable code after return, throw, continue, and break statements
```
function doSomething () {
  return true
  console.log('never called')     // ✗ avoid
}
```

### 93) No flow control statements in finally blocks
```
try {
  // ...
} catch (e) {
  // ...
} finally {
  return 42     // ✗ avoid
}
```

### 94) The left operand of relational operators must not be negated
```
if (!(key in obj)) {}     // ✓ ok
if (!key in obj) {}       // ✗ avoid
```

### 95) Avoid unnecessary use of .call() and .apply()
```
sum.call(null, 1, 2, 3)   // ✗ avoid
```

### 96) Avoid using unnecessary computed property keys on objects
```
const user = { name: 'John Doe' }       // ✓ ok
const user = { ['name']: 'John Doe' }   // ✗ avoid
```

### 97) No unnecessary constructor
```
class Car {
  constructor () {      // ✗ avoid
  }
}
```

### 98) No unnecessary use of escape
```
let message = 'Hell\o'  // ✗ avoid
```

### 99) Renaming import, export, and destructured assignments to the same name is not allowed
```
import { config } from './config'               // ✓ ok
import { config as config } from './config'     // ✗ avoid
```

### 100) No whitespace before properties
```
user.name       // ✓ ok
user .name      // ✗ avoid
```

### 101) No using with statements
```
with (val) {...}    // ✗ avoid
```

### 102) Maintain consistency of newlines between object properties
```
const user = { name: 'Jane Doe', age: 30, username: 'jdoe86' }    // ✓ ok

const user = {
  name: 'Jane Doe',
  age: 30,
  username: 'jdoe86'
}             // ✓ ok

const user = {
  name: 'Jane Doe', age: 30,
  username: 'jdoe86'            // ✗ avoid
}
```

### 103) No padding within blocks
```
if (user) {
  const name = getName()    // ✓ ok
}

if (user) {
                            // ✗ avoid
  const name = getName()

}
```

### 104) No whitespace between spread operators and their expressions
```
for (let i = 0; i < items.length; i++) {...}    // ✓ ok
for (let i = 0 ;i < items.length ;i++) {...}    // ✗ avoid
```

### 105) Must have a space before blocks
```
if (admin) {...}    // ✓ ok
if (admin){...}     // ✗ avoid
```

### 106) No spaces inside parentheses
```
getName(name)       // ✓ ok
getName( name )     // ✗ avoid
```

### 107) Unary operators must have a space after
```
typeof !admin        // ✓ ok
typeof!admin        // ✗ avoid
```

### 108) Use spaces inside comments
```
// comment          // ✓ ok
//comment           // ✗ avoid

/* comment */       // ✓ ok
/*comment*/         // ✗ avoid
```

### 110) No spacing in template strings
```
const message = `Hello, ${name}`      // ✓ ok
const message = `Hello, ${ name }`    // ✗ avoid
```

### 111) Use isNaN() when checking for NaN
```
if (isNaN(price)) { }       // ✓ ok
if (price === NaN) { }      // ✗ avoid
```

### 112) typeof must be compared to a valid string
```
typeof name === 'undefined'     // ✓ ok
typeof name === 'undefimed'     // ✗ avoid
```

### 113) Immediately Invoked Function Expressions (IIFEs) must be wrapped
```
const getName = (function () { }())   // ✓ ok
const getName = (function () { })()   // ✓ ok

const getName = function () { }()     // ✗ avoid
```

### 114) The * in yield*expressions must have a space before and after
```
yield * increment()   // ✓ ok
yield* increment()    // ✗ avoid
```

### 115) Avoid Yoda conditions
```
if (age === 42) { }    // ✓ ok
if (42 === age) { }    // ✗ avoid
```

### 116) No semicolons
```
window.alert('hi')   // ✓ ok
window.alert('hi');  // ✗ avoid
```

### 117) Never start a line with (, [, `, or a handful of other unlikely possibilities
This is the only gotcha with omitting semicolons, and standard protects you from this potential issue.

(The full list is: [, (, `, +, *, /, -, ,, ., but most of these will never appear at the start of a line in real code.)
```
// ✓ ok
;(function () {
  window.alert('ok')
}())

// ✗ avoid
(function () {
  window.alert('ok')
}())
// ✓ ok
;[1, 2, 3].forEach(bar)

// ✗ avoid
[1, 2, 3].forEach(bar)
// ✓ ok
;`hello`.indexOf('o')

// ✗ avoid
`hello`.indexOf('o')
```
Note: If you're often writing code like this, you may be trying to be too clever.

Clever short-hands are discouraged, in favor of clear and readable expressions, whenever possible.

Instead of this:
```
;[1, 2, 3].forEach(bar)
```

This is strongly preferred:
```
var nums = [1, 2, 3]
nums.forEach(bar)
```
