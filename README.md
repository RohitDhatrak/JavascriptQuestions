###### 1. What's the result?

```javascript
Number(undefined)
```
<details><summary><b>Answer</b></summary>
<p>
  
  NaN
</p>
</details>

###### 2. What's the result?

```javascript
Number("   123    ")
Number("12 3")
```
<details><summary><b>Answer</b></summary>
<p>
  
  123,
  NaN (only whitespace from the start and end are removed)
</p>
</details>

###### 3. What's the result?

```javascript
Boolean(" ")
Boolean("0")
```
<details><summary><b>Answer</b></summary>
<p>
  
  true,
  true
  
  Only values that are intuitively “empty”, like 0, "", null, undefined, and NaN, become false.
</p>
</details>

###### 4. What's the result?

```javascript
typeof null
```
<details><summary><b>Answer</b></summary>
<p>
  
  object
  
  That’s an officially recognized error in typeof behavior, coming from the early days of JavaScript and kept for compatibility.
  
  Definitely, null is not an object. It is a special value with a separate type of its own.
</p>
</details>

###### 5. What's the result?

```javascript
2 ** 2
```
<details><summary><b>Answer</b></summary>
<p>
  
  2² = 4
</p>
</details>

###### 6. What's the result?

```javascript
2 + 2 + '1'
'1' + 2 + 2
```
<details><summary><b>Answer</b></summary>
<p>
  
  4 + '1' >> '41'
  
 '12' + 2 >> '122'
</p>
</details>

###### 7. What's the result?

```javascript
+true
+""
+"2" + +"3"
```
<details><summary><b>Answer</b></summary>
<p>
  
  1,
  0,
  5
  
  The plus + exists in two forms: the binary and the unary form.
  
  The unary plus doesn’t do anything to numbers. But if the operand is not a number, the unary plus converts it into a number.
</p>
</details>

###### 8. What's the result?

```javascript
let a = 1;
let b = 2;

let c = 3 - (a = b + 1);  
// Good to understand how it works. Please don’t write the code like that. 
```
<details><summary><b>Answer</b></summary>
<p>
  
  0
  
  All operators in JavaScript return a value. That’s obvious for + and -, but also true for =
  
  The call x = value writes the value into x and then returns it.
</p>
</details>

###### 9. What's the result?

```javascript
let a = (1 + 2, 3 + 4);
```
<details><summary><b>Answer</b></summary>
<p>
  
  a = 7
  
  The comma operator allows us to evaluate several expressions, dividing them with a comma ,. 
  Each of them is evaluated but only the result of the last one is returned.
  
  Why do we need an operator that throws away everything except the last expression?

  Sometimes, people use it in more complex constructs to put several actions in one line.

  For example:

  ```javascript
  // three operations in one line
  for (a = 1, b = 3, c = a * b; a < 10; a++) {
   ...
  }
  // doesn't improve code readability so we should think well before using this.
  ```
</p>
</details>
    
    
###### 10. What's the result?

```javascript
let y = "5";
let x = y++; // number or string 5?
```
<details><summary><b>Answer</b></summary>
<p>
  
  number 5
  
  JavaScript first coerces the string to a number then assigns the value to the variable x and then increments the value.
</p>
</details>

###### 11. What's the result?

```javascript
let a = NaN;
let b = NaN;

a === b;
a == b;
```
<details><summary><b>Answer</b></summary>
<p>
  
  false, false
  
  NaN is the only value in JavaScript that is not equal to itself. So we can check for a NaN value by checking if the value is equal to itself.
  According to IEEE standard NaN is not equal to NaN.
</p>
</details>

###### 12. What's the result?

```javascript
isNaN("this is a string not a NaN value");
Number.isNaN("this is a string not a NaN value");
```
<details><summary><b>Answer</b></summary>
<p>
  
  true, false
  
  isNaN tries to coerce the value into a Number before checking if it's a NaN value. This issue has been fixed in Number.isNaN().
</p>
</details>

###### 13. What's the result?

```javascript
let negativeZero = -0;

negativeZero.toString();
negativeZero === 0;
negativeZero < 0;
negativeZero > 0;

Object.is(negativeZero, -0)
Object.is(negativeZero, 0)
```
<details><summary><b>Answer</b></summary>
<p>
  
  "0", true, false, false
  
  When we try to use these operations we get some unexpected behaviour because language developers decided negative zero isn't needed.
  
  true, false
  This was fixed in Object.is() method.
  
  Use case of -0: To show direction when something is stationary 
</p>
</details>

###### 14. What's the result?

```javascript
let string = 'orange';

function changeToApple(string) {
  string = 'apple';
}

changeToApple(string);

console.log(string);  // ??
```
<details><summary><b>Answer</b></summary>
<p>
  orange
</p>
</details>

###### 15. What's the result?

```javascript
const promise = new Promise((resolve, reject) => {
  console.log(1);
  setTimeout(() => {
    console.log("timerStart");
    resolve("success");
    console.log("timerEnd");
  }, 0);
  console.log(2);
});
promise.then(console.log);
console.log(3);
```
<details><summary><b>Answer</b></summary>
<p>
  1 2 3 timerStart timerEnd success
</p>
</details>

###### 16. What's the result?

```javascript
let fruit = prompt("Which fruit to buy?", "apple");

let bag = {
  [fruit]: 5,
};
```
<details><summary><b>Answer</b></summary>
<p>
  That’s called computed properties. The name of the property is taken from the variable fruit.
</p>
</details>

###### 17. What's the result?

```javascript
let obj = {
  for: 1,
  let: 2,
  return: 3
};

console.log( obj.for + obj.let + obj.return );
```
<details><summary><b>Answer</b></summary>
<p>
  It will print 6. There are no limitations on property names. They can be any strings or symbols. Other types are automatically converted to strings. 
</p>
</details>

###### 18. What's the result?

```javascript
let obj = {
  test: undefined
};

if(obj.test){
  console.log("hi);
}
```
<details><summary><b>Answer</b></summary>
<p>
  It won't log hi because the property exists but the value is undefined. So we can use the `in` operator to check if a property is defined of not.
 
  if("test" in obj){ // returns true
    console.log("hi");
  }
</p>
</details>

###### 19. What's the result?

```javascript
let codes = {
  "49": "Germany",
  "41": "Switzerland",
  "44": "Great Britain",
  // ..,
  "1": "USA"
};

for (let code in codes) {
  console.log(code);
}
```
<details><summary><b>Answer</b></summary>
<p>
  1, 41, 44, 49
  integer properties are sorted (UTF-16 code units order), others appear in creation order.
</p>
</details>

###### 20. What's the result?

```javascript
let a = {};
let b = a;

log( a == b );
log( a === b );
```
<details><summary><b>Answer</b></summary>
<p>
  true, true
  Both refer to the same object.
</p>
</details>

###### 21. What's does the User function return?

```javascript
function User(name) {
  this.name = name;
  this.isAdmin = false;
}

let user = new User("Jack");
```
<details><summary><b>Answer</b></summary>
<p>
  The value of this is returned implicitly.
</p>
</details>

###### 22. What's the result?

```javascript
function User() {

  if(new.target){
    console.log("Hi");
  }
}

User();
new User(); 
```
<details><summary><b>Answer</b></summary>
<p>
  1. undefined, 2. Hi
  Inside a function, we can check whether it was called with new or without it, using a special new.target property.
</p>
</details>

###### 23. What's the result?

```javascript
function BigUser() {

  this.name = "John";

  return { name: "Godzilla" };
}

function SmallUser() {

  this.name = "John";

  return "Rick";
}

console.log( new BigUser().name );
console.log( new SmallUser().name );
```
<details><summary><b>Answer</b></summary>
<p>
  
  
  1. Godzilla, 2. Johm`
  
  If return is called with an object, then the object is returned instead of this
  If return is called with a primitive, it’s ignored.
</p>
</details>

###### 24. Is the constructor call valid?

```javascript
function User(){
  this.name = "Admin"
}
let user = new User;
```
<details><summary><b>Answer</b></summary>
<p>
  We can omit parentheses after new, if it has no arguments. Omitting parentheses here is not considered a “good style”, but the syntax is permitted by specification.
</p>
</details>

###### 25. Modify the code of up, down and showStep to make the calls chainable?

```javascript
let ladder = {
  step: 0,
  up() {
    this.step++;
  },
  down() {
    this.step--;
  },
  showStep: function() {
    alert( this.step );
  }
};

// ladder.up().up().down().showStep(); // 1
```
<details><summary><b>Answer</b></summary>
<p>
  We can return `this` in every method
  ```javascript
    let ladder = {
    step: 0,
    up() {
      this.step++;
      return this;
    },
    down() {
      this.step--;
      return this;
    },
    showStep() {
      alert( this.step );
      return this;
    }
  };```

</p>
</details>

###### 26. Is it possible to create functions A and B so that new A() == new B()??

```javascript
function A() { ... }
function B() { ... }

let a = new A;
let b = new B;

alert( a == b ); // true
```
<details><summary><b>Answer</b></summary>
<p>
  Yes, it’s possible.

  If a function returns an object then new returns it instead of this.

  So they can, for instance, return the same externally defined object obj
  ```javascript
    let obj = {};

    function A() { return obj; }
    function B() { return obj; }

    alert( new A() == new B() ); // true
  ```
</p>
</details>

###### 27. What's the result?

```javascript
let user = {
  address: null
};

log( user?.name?.first );
log( user?.address?.street )
```
<details><summary><b>Answer</b></summary>
<p>
  1. undefined 2. undefined
  
  The optional chaining ?. stops the evaluation if the value before ?. is undefined or null and returns undefined
</p>
</details>

###### 28. What's the result?

```javascript
log(user?.address);

let userAdmin = {
  admin() {
    alert("I am admin");
  }
};

let userGuest = {};

log(userAdmin.admin?.());

log(userGuest.admin?.());
```
<details><summary><b>Answer</b></summary>
<p>
  1. ReferenceError: user is not defined. If there’s no variable user at all, then user?.anything triggers an error
  
  2. I am admin 3. nothing happens
  
  The optional chaining ?. is not an operator, but a special syntax construct, that also works with functions and square brackets.
  ?.(), ?.[]
</p>
</details>

###### 29. Are the two statements valid?

```javascript
delete user?.name;
user?.name = "John";
```
<details><summary><b>Answer</b></summary>
<p>
  1. valid 2. invalid
  
  We can use ?. for safe reading and deleting, but not writing
</p>
</details>

###### 30. What's is valid in the below code?

```javascript
 let numbers = {
    0: 0
 }
 
 numbers.1 = 1;
```
<details><summary><b>Answer</b></summary>
<p>
  the first part is valid the number 0 will automatically be converted to string. By specification, object property keys may be either of string type, or of symbol type.
  
  the `numbers.1 = 1;` is invalid
</p>
</details>

###### 31. What's the result?

```javascript
 let numbers = {
    0: 0
 }
 
log(numbers."0");
log(numbers[0]);
```
<details><summary><b>Answer</b></summary>
<p>
  1. error 2. returns 0
</p>
</details>

###### 32. What's the result?

```javascript
alert( 1 || 0 );
alert( null || 1 );
alert( null || 0 || 1 );
alert( undefined || null || 0 )
```
<details><summary><b>Answer</b></summary>
<p>
  1, 1, 1, 0
  
  || returns the first truthy value (without any conversion) or the last one if no truthy value is found
</p>
</details>

###### 33. What's the result?

```javascript
alert( 1 && 0 );
alert( 1 && 5 );
alert( null && 5 );
alert( 0 && "no matter what" );
```
<details><summary><b>Answer</b></summary>
<p>
  0, 5, null, 0
  
  AND returns the first falsy value(without any conversion) or the last value if none were found
</p>
</details>

###### 34. What's the result?

```javascript
alert( !!"non-empty string" );
alert( !!null );
```
<details><summary><b>Answer</b></summary>
<p>
  true, false
  
  double NOT !! is sometimes used for converting a value to boolean type. The first NOT converts the value to boolean and returns the inverse, and the second NOT inverses it again. In the end, we have a plain value-to-boolean conversion.
</p>
</details>

###### 35. What's the result?

```javascript
NaN ** 0
```
<details><summary><b>Answer</b></summary>
<p>
1
</p>
</details>

###### 36. What's the result?

```javascript
let n = 2;
n *= 3 + 5
```
<details><summary><b>Answer</b></summary>
<p>
16
</p>
</details>
