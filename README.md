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
  
  JavaScript first coerces the string to a numver then assigns the value to the variable x and then increments the value.
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
  
  isNaN tries to coerces the value into a Number before checking if it's a NaN value. This issue has been fixed in Number.isNaN().
</p>
</details>
