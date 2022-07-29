# Javascript

- [Data types](#ikiểu-dữ-liệu)
  
  1. [Number](#1-number)
  2. [BigInt](#2-bigint)
  3. [String](#3-string)
  4. [Boolean](#4-boolean-logical-type)
  5. [Null](#5-giá-trị-null)
  6. [Undefined](#6-giá-trị-undefined)
  7. [Object](#7-object)
  8. [Symbols](#8-symbols)
  9. [The typeof operator](#9-the-typeof-operator)
- [Javascript](#javascript)
  - [Data types](#data-types)
  - [I.Kiểu dữ liệu](#ikiểu-dữ-liệu)
    - [1. Number](#1-number)
    - [2. BigInt](#2-bigint)
    - [3. String](#3-string)
    - [4. Boolean (logical type)](#4-boolean-logical-type)
    - [5. Giá trị Null](#5-giá-trị-null)
    - [6. Giá trị Undefined](#6-giá-trị-undefined)
    - [7. Object](#7-object)
    - [8. Symbols](#8-symbols)
    - [9. The typeof operator](#9-the-typeof-operator)
  - [Loops: while and for](#loops-while-and-for)
    - [1. The "while" loop](#1-the-while-loop)
    - [2. The “do…while” loop](#2-the-dowhile-loop)
    - [3. The “for” loop](#3-the-for-loop)
      - [Skipping parts](#skipping-parts)
    - [4. Breaking the loop](#4-breaking-the-loop)
    - [5. Continue to the next iteration](#5-continue-to-the-next-iteration)
    - [6. Labels for break/continue](#6-labels-for-breakcontinue)
    - [7. Summary:](#7-summary)
  - [- `for` - Điều kiện được kiểm tra trước mỗi lần lặp, cài đặt bổ sung có sẵn.](#--for---điều-kiện-được-kiểm-tra-trước-mỗi-lần-lặp-cài-đặt-bổ-sung-có-sẵn)
  - [The "switch" statement](#the-switch-statement)
    - [1. The syntax](#1-the-syntax)
    - [2. An example](#2-an-example)
    - [3. Grouping of “case”](#3-grouping-of-case)
    - [4. Type matters](#4-type-matters)
  - [Conditional branching: if, '?'](#conditional-branching-if-)
    - [1. The “if” statement](#1-the-if-statement)
    - [2. Boolean conversion](#2-boolean-conversion)
    - [3. The “else” clause](#3-the-else-clause)
    - [4. Several conditions: “else if”](#4-several-conditions-else-if)
    - [5. Conditional operator ‘?’](#5-conditional-operator-)
    - [6. Multiple ‘?’](#6-multiple-)
    - [7. Non-traditional use of ‘?’](#7-non-traditional-use-of-)
  - [Function expressions](#function-expressions)
    - [1. Function is a value](#1-function-is-a-value)
    - [2. Callback functions](#2-callback-functions)
    - [3. khác nhau giữa Expressions Function và Declaration Function](#3-khác-nhau-giữa-expressions-function-và-declaration-function)
    - [4. Summary](#4-summary)
  - [+ Expression function được tạo ra khi luồng thực thi đến chúng](#-expression-function-được-tạo-ra-khi-luồng-thực-thi-đến-chúng)
  - [Arrow functions, the basics](#arrow-functions-the-basics)
    - [Multiline arrow functions](#multiline-arrow-functions)
  - [Logical operators](#logical-operators)
  - [1. || (OR)](#1--or)
  - [2. OR "||" finds the first truthy value](#2-or--finds-the-first-truthy-value)
    - [3. && (AND)](#3--and)
  - [4. AND “&&” finds the first falsy value](#4-and--finds-the-first-falsy-value)
    - [5. ! (NOT)](#5--not)
  - [Error handling, "try...catch"](#error-handling-trycatch)
    - [1. The “try…catch” syntax](#1-the-trycatch-syntax)
    - [2. Error object](#2-error-object)
    - [3. Optional “catch” binding](#3-optional-catch-binding)
    - [4. Using “try…catch”](#4-using-trycatch)
    - [5. Throwing our own errors](#5-throwing-our-own-errors)
    - [6. Rethrowing](#6-rethrowing)
    - [7. try…catch…finally](#7-trycatchfinally)
  - [Promises, async/await](#promises-asyncawait)
    - [1. Introduction: callbacks](#1-introduction-callbacks)
      - [1. Callback in callback](#1-callback-in-callback)
      - [2. Handling errors](#2-handling-errors)
      - [3. Pyramid of Doom](#3-pyramid-of-doom)
    - [2. Promise](#2-promise)
  - [2. Một finally trình xử lý chuyển kết quả và lỗi cho trình xử lý tiếp theo.](#2-một-finally-trình-xử-lý-chuyển-kết-quả-và-lỗi-cho-trình-xử-lý-tiếp-theo)
    - [3. Promises chaining](#3-promises-chaining)
    - [1. Returning promises](#1-returning-promises)
    - [2. Xây dựng function loadScript](#2-xây-dựng-function-loadscript)
    - [4. Error handling with promises](#4-error-handling-with-promises)
    - [1. Implicit try...catch](#1-implicit-trycatch)
    - [2. Rethrowing](#2-rethrowing)
    - [3. Unhandled rejections](#3-unhandled-rejections)
    - [5. Promise API](#5-promise-api)
    - [1.  Promise.all](#1--promiseall)
    - [2.  Promises.allSettled](#2--promisesallsettled)
    - [3. Promise.race](#3-promiserace)
    - [4. Promise.any](#4-promiseany)
    - [5. Promise.resolve](#5-promiseresolve)
    - [6. Promise.reject](#6-promisereject)
    - [6. Async/await](#6-asyncawait)
    - [1. Async functions](#1-async-functions)
    - [2.Await](#2await)
    - [3. Error handling](#3-error-handling)
    - [4. Summary](#4-summary-1)
  - [4. Với promise hoặc callback, việc kết hợp if/else hoặc retry với code asynchnous là một điều gì đó khá khó chịu. Với async/await, việc này vô cùng dễ dàng.](#4-với-promise-hoặc-callback-việc-kết-hợp-ifelse-hoặc-retry-với-code-asynchnous-là-một-điều-gì-đó-khá-khó-chịu-với-asyncawait-việc-này-vô-cùng-dễ-dàng)
  - [Export and Import](#export-and-import)
  - [Class](#class)
    - [1. syntax](#1-syntax)
    - [2. Getters/setters](#2-getterssetters)
    - [3. Class inheritance](#3-class-inheritance)
    - [4. Static properties and methods](#4-static-properties-and-methods)
    - [5. Class checking: "instanceof"](#5-class-checking-instanceof)
    - [Object.prototype.toString for the type](#objectprototypetostring-for-the-type)
  - [Mixin](#mixin)
  - [+ EventMixin Chức năng quan trọng của nhiều object là làm việc với các event. Có thể hiểu là một object sẽ chứa các method làm nhiệm vụ tạo ra các event khi có vấn đề gì đó xảy ra, và object còn lại thì sẳn sàng để lắng nghe những event đó.](#-eventmixin-chức-năng-quan-trọng-của-nhiều-object-là-làm-việc-với-các-event-có-thể-hiểu-là-một-object-sẽ-chứa-các-method-làm-nhiệm-vụ-tạo-ra-các-event-khi-có-vấn-đề-gì-đó-xảy-ra-và-object-còn-lại-thì-sẳn-sàng-để-lắng-nghe-những-event-đó)
  - [Date and time](#date-and-time)
  
  - [Export and Import](#export-and-import)
  - [Class](#class)
    - [1. syntax](#1-syntax)
    - [2. Getters/setters](#2-getterssetters)
    - [2. Class inheritance](#2-class-inheritance)
    - [3. Static properties and methods](#3-static-properties-and-methods)
    - [4. Class checking: "instanceof"](#4-class-checking-instanceof)
    - [1. Object.prototype.toString for the type](#1-objectprototypetostring-for-the-type)
 
  - [Export and Import](#export-and-import)
  - [Class](#class)
    - [1. syntax](#1-syntax)
    - [2. Getters/setters](#2-getterssetters)
    - [3. Class inheritance](#3-class-inheritance)
    - [4. static-properties-and-methods ](#4-static-properties-and-methods)
    - [5. class-checking-instance of](#5-class-checking-instanceof)
  - [Date and time](#date-and-time)
## Data types

## I.Kiểu dữ liệu

### 1. Number
```javascript
let n = 123;
n = 12.345;
```
+ đại diện cho số nguyên và số thập phân
+ các hoặt động của Numbers:  addition `+`, subtraction `-`, multiplication `*`, division `/`
+ giá trị sô đặc biệt: `Infinity`, `-Infinity` and `NaN`
1. Infinity: giá trị vô cực
```javascript
alert( 1 / 0 ); // Infinity
```
```javascript
alert( Infinity ); // Infinity
```
2. NaN: đại diện cho 1 lỗi tính toán
```javascript
alert( "not a number" / 2 ); // NaN, such division is erroneous
```
```javascript
alert( NaN + 1 ); // NaN
alert( 3 * NaN ); // NaN
alert( "not a number" / 2 - 1 ); // NaN
```
lưu ý:  `NaN ** 0 is 1`

### 2. BigInt
+ Đại diện cho số nguyên lớn hơn `2^53-1` và nhở hơn `-2^53-1`
+ Giá trị BigInt được tạo bằng cách thêm n vào cuối một số nguyên:
```javascript
// the "n" at the end means it's a BigInt
const bigInt = 1234567890123456789012345678901234567890n;
```
### 3. String
+ 1 String luôn đặt trong dấu ngoặc kép  (quotes)
```javascript
let str = "Hello";
let str2 = 'Single quotes are ok too';
let phrase = `can embed another ${str}`;
```
+ Có 3 loại dấu ngoặc kép
1. Double quotes: "Hello".
2. Single quotes: 'Hello'.
3. Backticks: `` `Hello` ``.
+ nó có thể nhúng các biến và biểu thức được bọc trong ${...}
```javascript
let name = "John";

// embed a variable
alert( `Hello, ${name}!` ); // Hello, John!

// embed an expression
alert( `the result is ${1 + 2}` ); // the result is 3
```

### 4. Boolean (logical type)
+ có 2 giá trị: true và false 
```javascript
let nameFieldChecked = true; // yes, name field is checked
let ageFieldChecked = false; // no, age field is not checked
```
+ Giá trị của Boolean cũng đến từ giá trị so sánh
```javascript
let isGreater = 4 > 1;

alert( isGreater ); // true (the comparison result is "yes")
```
### 5. Giá trị Null
+ giá trị không được được miêu tả, là loại giá trị riêng biệt chỉ gồm giá trịn Null (`nothing`, `empty` or `value unknown`)
```javascript
let age = null;
```
### 6. Giá trị Undefined
+ Là giá trị riêng biệt giống với null, nghĩa là `undefined is “value is not assigned”`
+ Biến được khai báo nhưng không được chỉ định thì giá trị là undefined
```javascript
let age;

alert(age); // shows "undefined"
```
+ Về mặt kĩ thuật, có thể chỉ đnhj là biến `undefined`
### 7. Object
+ là dữ liệu nguyên thủy từ đơn giản đến phức tạp, Object được sử dụng để lưu trữ nhiều dữ liệu
### 8. Symbols
+ là dữ liệu sử dụng tạo ra nhận dạng duy nhất cho object, nó được để tránh xung đột tên giữa các thuộc tính, vì không có Symbol nào bằng giống nhau cả. Hoặc nó cũng được dùng để thêm các thuộc tính mà không thể bị ghi đè hoặc không muốn bị nhận ra
```javascript
const NAME = Symbol()
const person = {
  [NAME]: 'Flavio'
}

person[NAME] //'Flavio'

const RUN = Symbol()
person[RUN] = () => 'Person is running'
console.log(person[RUN]()) //'Person is running'
```

### 9. The typeof operator

```javascript
typeof undefined // "undefined"

typeof 0 // "number"

typeof 10n // "bigint"

typeof true // "boolean"

typeof "foo" // "string"

typeof Symbol("id") // "symbol"

typeof Math // "object"  (1)

typeof null // "object"  (2)

typeof alert // "function"  (3)
```
---
## Loops: while and for

### 1. The "while" loop
+ Syntax
```javascript
while (condition) {
  // code
  // so-called "loop body"
}
```
+ Khi điều kiện đúng thì phần loop body sẽ được thực thi
```javascript
let i = 0;
while (i < 3) { // shows 0, then 1, then 2
  alert( i );
  i++;
}
```
+ while (i != 0) is while (i):
```javascript
let i = 3;
while (i) { // when i becomes 0, the condition becomes falsy, and the loop stops
  alert( i );
  i--;
}
```
### 2. The “do…while” loop
+ Syntax
```javascript
do {
  // loop body
} while (condition);
```
+ Vòng lặp sẽ thực hiện phần loop body đầu tiên, rồi kiểm tra điều kiện, khi đúng thì sẽ thực hiện lại.
```javascript
let i = 0;
do {
  alert( i );
  i++;
} while (i < 3);// 0, 1, 2
```
+ Các cú pháp của hình thức này chỉ được sử dụng khi khi muốn loop body thực thi ít nhất 1 lần bất kể điều kiện đang đúng, hình thức khác ưa thích hơn: while(){}
### 3. The “for” loop
+ Vòng lặp for rất nhiều tổ hợp, nhưng nó cũng được sử dụng phổ biến nhất
+ Syntax
```javascript
for (begin; condition; step) {
  // ... loop body ...
}
```
+ Example
```javascript
for (let i = 0; i < 3; i++) { // shows 0, then 1, then 2
  alert(i);
}
```

| part |  |  |
| ----- | ------ | ------ |
| begin | 	let i = 0 |  	Thực thi một lần khi vào vòng lặp.
| condition | i < 3 | Được kiểm tra trước mỗi lần lặp lại vòng lặp. Nếu sai, vòng lặp sẽ dừng lại
| body | alert(i) | Chạy đi chạy lại trong khi điều kiện là trung thực. |
| step |i++ | Thực thi sau phần thân trên mỗi lần lặp.|

+ khi khai biến ở nội tuyến `inline` 
```javascript
for (let i = 0; i < 3; i++) {
  alert(i); // 0, 1, 2
}
alert(i); // error, no such variable
``` 
```javascript
let i = 0;

for (i = 0; i < 3; i++) { // use an existing variable
  alert(i); // 0, 1, 2
}

alert(i); // 3, visible, because declared outside of the loop
```

#### Skipping parts
+ Có thể lượt bỏ bất kì phần tử của `for`
```javascript
let i = 0; // we have i already declared and assigned

for (; i < 3; i++) { // no need for "begin"
  alert( i ); // 0, 1, 2
}
```
```javascript
let i = 0;

for (; i < 3;) {
  alert( i++ );
}
```
```javascript
for (;;) {
  // repeats without limits
}
```
### 4. Breaking the loop
+ Bình thường vòng lặp sẽ thoát ra khi điều kiên trở thành falsy nhưng có thể kết thúc vòng lặp bằng `break`.
```javascript
let sum = 0;

while (true) {

  let value = +prompt("Enter a number", '');

  if (!value) break; // (*)

  sum += value;

}
alert( 'Sum: ' + sum );
```
### 5. Continue to the next iteration
+ Chỉ thị nhẹ hơn `break` sẽ không dừng vòng lặp, Thay vào đó, nó dừng vòng lặp hiện tại và buộc vòng lặp bắt đầu một vòng lặp mới (nếu điều kiện cho phép).
```javascript
for (let i = 0; i < 10; i++) {

  // if true, skip the remaining part of the body
  if (i % 2 == 0) continue;

  alert(i); // 1, then 3, 5, 7, 9
}
```
-> `continue: i % 2 !== 0`
+ No break/continue
```javascript
if (i > 5) {
  alert(i);
} else {
  continue;
}

->(i > 5) ? alert(i) : continue; // continue isn't allowed here
```

### 6. Labels for break/continue
+ Thoát ra từ nhiều vòng lặp lồng nhau
```javascript
for (let i = 0; i < 3; i++) {

  for (let j = 0; j < 3; j++) {

    let input = prompt(`Value at coords (${i},${j})`, '');

    // what if we want to exit from here to Done (below)?
  }
}

alert('Done!');
```
+ `break <labelName>` câu lệnh trong vòng lặp thoát ra `label` 
```javascript
labelName: for (...) {
  ...
}
```
```javascript
label: {
  // ...
  break label; // works
  // ...
}
```
```javascript
outer: for (let i = 0; i < 3; i++) {

  for (let j = 0; j < 3; j++) {

    let input = prompt(`Value at coords (${i},${j})`, '');

    // if an empty string or canceled, then break out of both loops
    if (!input) break outer; // (*)

    // do something with the value...
  }
}

alert('Done!');
```

### 7. Summary:
+ #### 3 loại vòng lặp:
  - `While` - Điều kiện được kiểm tra trước mỗi lần lặp.
  - `do..while ` - Điều kiện được kiểm tra sau mỗi lần lặp.
  - `for` - Điều kiện được kiểm tra trước mỗi lần lặp, cài đặt bổ sung có sẵn.
---
## The "switch" statement
### 1. The syntax
+ 1 `switch` có thể thay thế nhiều `if`
+ 1 `switch` có nhiều `case` và mặc định tùy chọn
```javascript
switch(x) {
  case 'value1':  // if (x === 'value1')
    ...
    [break]

  case 'value2':  // if (x === 'value2')
    ...
    [break]

  default:
    ...
    [break]
}
```
### 2. An example
```javascript
let a = 2 + 2;

switch (a) {
  case 3:
    alert( 'Too small' );
    break;
  case 4:
    alert( 'Exactly!' );
    break;
  case 5:
    alert( 'Too big' );
    break;
  default:
    alert( "I don't know such values" );
}// Exactly
```
+ Lưu ý: nếu không các `case` kế tiếp sẽ thực hiện mà không có bất kỳ kiểm tra nào
```javascript
let a = 2 + 2;

switch (a) {
  case 3:
    alert( 'Too small' );
  case 4:
    alert( 'Exactly!' );
  case 5:
    alert( 'Too big' );
  default:
    alert( "I don't know such values" );
}// Exactly, Too big, I don't know such values
```
### 3. Grouping of “case”
+ một số biến `case` khi chia sẻ code giống nhau sẽ được nhóm lại
```javascript
let a = 3;

switch (a) {
  case 4:
    alert('Right!');
    break;

  case 3: // (*) grouped two cases 3 and 5
  case 5:
    alert('Wrong!');
    alert("Why don't you take a math class?");
    break;

  default:
    alert('The result is strange. Really.');
}
// Wrong!, Why don't you take a math class?
```
### 4. Type matters
+ Hãy nhấn mạnh rằng việc kiểm tra bình đẳng luôn nghiêm ngặt. Các giá trị phải cùng loại để khớp.
```javascript
let arg = prompt("Enter a value?");
switch (arg) {
  case '0':
  case '1':
    alert( 'One or zero' );
    break;

  case '2':
    alert( 'Two' );
    break;

  case 3:
    alert( 'Never executes!' );
    break;
  default:
    alert( 'An unknown value' );
}
// 1 và 0, 2 sẽ chạy
//Nhưng đối với 3, kết quả của lời nhắc là một chuỗi "3", không hoàn toàn bằng === với số 3. Vì vậy, nhận được mã chết trong trường hợp 3
```
---
## Conditional branching: if, '?'
 
### 1. The “if” statement
+ if(...) sẽ đánh giá điều kiện ở trong dấu ngoặc đơn, nếu kết quả `true` thì trả về khối code
```javascript
let year = prompt('In which year was ECMAScript-2015 specification published?', '');

if (year == 2015) alert( 'You are right!' );
// nhập 2015 thì kết quả là 'you are right'
// ngược lại thì sẽ không xuất hiện gì cả
```
### 2. Boolean conversion
+ if(...) đánh giá câu lệnh ở trong dấu ngoặc đơn và chuyển đổi dưới dạng `Boolean`
+ false/falsy: 0 , "", null, undefined, NaN
+ true/truthy: other
```javascript
  if (0) { // 0 is falsy
  ...
}
```
```javascript
if (1) { // 1 is truthy
  ...
}
```
+ Có thể đánh giá giá trị `Boolean` trước đó đến `if`
```javascript
let cond = (year == 2015); // equality evaluates to true or false

if (cond) {
  ...
}
```
### 3. The “else” clause
+ Câu lệnh `if` có thể chứa 1 khối `else`, `else` sẽ thực thi khi điều kiện là `falsy`
```javascript
let year = prompt('In which year was the ECMAScript-2015 specification published?', '');

if (year == 2015) {
  alert( 'You guessed it right!' );
} else {
  alert( 'How can you be so wrong?' ); // any value except 2015
}
// nhập 2015 thì sẽ là 'You guessed it right!'
// nhập khác 2015 thì sẽ là  'How can you be so wrong?'
```
### 4. Several conditions: “else if”
+ else if: biến thể của điều kiện
```javascript
let year = prompt('In which year was the ECMAScript-2015 specification published?', '');

if (year < 2015) {
  alert( 'Too early...' );// nhập số dưới 2015
} else if (year > 2015) {
  alert( 'Too late' );// nhập số trên 2015
} else {
  alert( 'Exactly!' );// nhập 2015
}
```
### 5. Conditional operator ‘?’
+ Gán 1 biến dựa vào đièu kiện
```javascript
let accessAllowed;
let age = prompt('How old are you?', '');

if (age > 18) {
  accessAllowed = true;// nhập số trên 18
} else {
  accessAllowed = false;// nhập số bằng hoặc dưới 18
}

alert(accessAllowed);
```
+ sử dụng `?` để trình bày điều kiện ngắn gọn hơn bằng toán tử 3 ngôi (ternary) 
+ Syntax
```javascript
let result = condition ? value1 : value2;
```
+ Example
```javascript
// the comparison operator "age > 18" executes first anyway
// (no need to wrap it into parentheses)
let accessAllowed = age > 18 ? true : false; 
```
### 6. Multiple ‘?’
+ Chuỗi `?` có thể trả về `value` dựa vào nhiều hơn 1 điều kiện
```javascript
let age = prompt('age?', 18);

let message = (age < 3) ? 'Hi, baby!' :
  (age < 18) ? 'Hello!' :
  (age < 100) ? 'Greetings!' :
  'What an unusual age!';

alert( message );
```
Khi qua if...else
```javascript
if (age < 3) {
  message = 'Hi, baby!';
} else if (age < 18) {
  message = 'Hello!';
} else if (age < 100) {
  message = 'Greetings!';
} else {
  message = 'What an unusual age!';
}
```
### 7. Non-traditional use of ‘?’
+ `?` được sử dụng để thay thế cho `if`
```javascript
let company = prompt('Which company created JavaScript?', '');

(company == 'Netscape') ?
   alert('Right!') : alert('Wrong.');
```
---
## Function expressions
+ Trong javascript, function không phải là 'magical language structure', nhưng là giá trị đặc biệt
+ Function Declaration:
```javascript
function sayHi() {
  alert( "Hello" );
}
```
+ Function Expression:
```javascript
let sayHi = function() {
  alert( "Hello" );
};
```
### 1. Function is a value
+ cho dù hàm được tạo ra như thế nào, thì funtion vẫn là value
```javascript
function sayHi() {
  alert( "Hello" );
}

alert( sayHi ); // shows the function code
//
```
```javascript
function sayHi() {   // (1) create
  alert( "Hello" );
}

let func = sayHi;    // (2) copy

func(); // Hello     // (3) run the copy (it works)!
sayHi(); // Hello    //     this still works too (why wouldn't it)
```
+ Lưu ý: Function Expressions thì có dấu chấm phẩy ở cuối, Function Declarations thi không ( Function Expressions được tạo ra như function(){} ở trong assignment statement: `let sayHi = ...;`)

### 2. Callback functions
+ với 1 hàm 3 tham số `ask(question, yes, no)` : `question`:là câu hỏi, `yes`:function chạy khi kết quả đúng, `no`: function chạy nếu kết quả sai
```javascript
function ask(question, yes, no) {
  if (confirm(question)) yes()
  else no();
}

function showOk() {
  alert( "You agreed." );
}

function showCancel() {
  alert( "You canceled the execution." );
}

// usage: functions showOk, showCancel are passed as arguments to ask
ask("Do you agree?", showOk, showCancel);
```
Dùng Expressions Function để viết ngắn hơn
```javascript
function ask(question, yes, no) {
  if (confirm(question)) yes()
  else no();
}

ask(
  "Do you agree?",
  function() { alert("You agreed."); },
  function() { alert("You canceled the execution."); }
);
```
### 3. khác nhau giữa Expressions Function và Declaration Function
+ Declaration Function: một hàm, được khai báo như một câu lệnh riêng biệt, trong luồng mã chính
```javascript
// Function Declaration
function sum(a, b) {
  return a + b;
}
```
+ Expressions Function: được tạo ra bên trong biểu thức hoặc bên trong một cấu trúc cú pháp khác, function được tao ra nằm bên phải `assignment expression` `=`
```javascript
// Function Expression
let sum = function(a, b) {
  return a + b;
};
```
+ Declaration Function: được gọi sớm hơn nếu nó được xác định, được xem như là global Function Declarations trong nó khi javascript chuẩn bị chạy script ( giai đoạn khởi tạo `initialization stage` ), sau khi tất cả Function Declarations được xử lí code sẽ chạy
```javascript
sayHi("John"); // Hello, John

function sayHi(name) {
  alert( `Hello, ${name}` );
}
```
+ Nếu Expressions Function thì sẽ không chạy, việc thực hiện chỉ xảy ra trong `function(){}`
```javascript
sayHi("John"); // error!

let sayHi = function(name) {  // (*) no magic any more
  alert( `Hello, ${name}` );
};
```
+ trong `strictmode`, khi Function Declaration ở trong khối code, nó sẽ được nhìn thấy ở mọi nơi trong khối nhưng không được nhìn thấy ở bên ngoài nó.
```javascript
"use strict"
let age = prompt("What is your age?", 18);

// conditionally declare a function
if (age < 18) {

  function welcome() {
    alert("Hello!");
  }

} else {

  function welcome() {
    alert("Greetings!");
  }

}

// ...use it later
welcome(); // Error: welcome is not defined

```
Nếu cho `Welcome` nằm trên `funtion declaration` thì `welcome` bên trong `if` sẽ được chạy
```javascript
let age = 16; // take 16 as an example

if (age < 18) {
  welcome();               // \   (runs)
                           //  |
  function welcome() {     //  |
    alert("Hello!");       //  |  Function Declaration is available
  }                        //  |  everywhere in the block where it's declared
                           //  |
  welcome();               // /   (runs)

} else {

  function welcome() {
    alert("Greetings!");
  }
}

// Here we're out of curly braces,
// so we can not see Function Declarations made inside of them.

welcome(); // Error: welcome is not defined
```
Nếu gọi `Welcome` ở ngoài `if` thì code sẽ được chạy
```javascript
let age = prompt("What is your age?", 18);

let welcome;

if (age < 18) {

  welcome = function() {
    alert("Hello!");
  };

} else {

  welcome = function() {
    alert("Greetings!");
  };

}

welcome(); // ok now
```
Hoặc có thể dùng question mask `?`
```javascript
let age = prompt("What is your age?", 18);

let welcome = (age < 18) ?
  function() { alert("Hello!"); } :
  function() { alert("Greetings!"); };

welcome(); // ok now
```
### 4. Summary
+ Function là các giá trị. Chúng có thể được gán, sao chép hoặc khai báo ở bất kỳ vị trí nào của mã.
+ Declaration function: Nếu hàm được khai báo dưới dạng một câu lệnh riêng biệt trong luồng mã chính.
+ Expression function: Nếu hàm được tạo như một phần của biểu thức
+ Expression function được tạo ra khi luồng thực thi đến chúng
---
## Arrow functions, the basics
+ là cú pháp tạo ra các hàm đơn giản và ngắn gọn, thường tốt hơn Function Expressions
```javascript
let func = (arg1, arg2, ..., argN) => expression;
```
+ tạo ra các function chấp nhận các arguments `arg1..argN`, `expression` ở bên phải dùng để trả về kết quả
```javascript
let func = function(arg1, arg2, ..., argN) {
  return expression;
};
```
+ Example
```javascript
let sum = (a, b) => a + b;

/* This arrow function is a shorter form of:

let sum = function(a, b) {
  return a + b;
};
*/

alert( sum(1, 2) ); // 3
```
```javascript
let double = n => n * 2;
// roughly the same as: let double = function(n) { return n * 2 }

alert( double(3) ); // 6
```
```javascript
let sayHi = () => alert("Hello!");

sayHi() //hello
```
+ Arrow Function cách sử dụng giống như Function Expressions.
```javascript
let age = prompt("What is your age?", 18);

let welcome = (age < 18) ?
  () => alert('Hello!') :
  () => alert("Greetings!");

welcome();
```
### Multiline arrow functions
+ Arrow function sẽ lấy các arguments bên trái `=>` trả về kết quả bên phải expression
```javascript
let sum = (a, b) => {  // the curly brace opens a multiline function
  let result = a + b;
  return result; // if we use curly braces, then we need an explicit "return"
};

alert( sum(1, 2) ); // 3
```
---
## Logical operators
+ Có 4 toán tử logic: `||` (OR), `&&` (AND), `!` (NOT), `??` (Nullish Coalescing)
+ chúng có thể được áp dụng đến 1 vài loại giá trị, không chỉ là boolean, chúng có thể thuộc bất kì loại nào
## 1. || (OR)
```javascript
result = a || b;
```
+ dùng để thao tác các giá trị boolean. Nếu bất kỳ đối số nào của nó là true, nó trả về true, ngược lại thì trả về false.
```javascript
alert( true || true );   // true
alert( false || true );  // true
alert( true || false );  // true
alert( false || false ); // false
```
+ Nếu toán hạn không phải dạng boolean thì nó sẽ chuyển về dạng boolean
```javascript
if (1 || 0) { // works just like if( true || false )
  alert( 'truthy!' );//1 là true, 0 là false -> true
}
```
```javascript
let hour = 9;//let hour = 12;

if (hour < 10 || hour > 18) { // true
  alert( 'The office is closed.' );
}
```
## 2. OR "||" finds the first truthy value
+ multiple OR’ed values:
```javascript
result = value1 || value2 || value3;
```
+ Toán tử `OR` sẽ thực hiện như sau:
1. Đánh giá toán hạng từ trái sang phải
2. Mỗi toán hạng sẽ chuyển đổi thành Boolean nếu kết quả đúng thì dừng và trả lại giá trị nguyên bản của toán hạng đó
3. nếu tất cả toán hạng được đánh giá ( tất cả là false ) sẽ trả lại toán hạng cuối cùng.
```javascript
alert( 1 || 0 ); // 1 (1 is truthy)

alert( null || 1 ); // 1 (1 is the first truthy value)
alert( null || 0 || 1 ); // 1 (the first truthy value)

alert( undefined || null || 0 ); // 0 (all falsy, returns the last value)
```
+ nhận được giá trị truthy đầu tiên
```javascript
let firstName = "";
let lastName = "";
let nickName = "SuperCoder";

alert( firstName || lastName || nickName || "Anonymous"); // SuperCoder
```
+ Short-circuit evaluation: (đánh giá ngắn hạng) khi quy trình `||` các đối số của nó cho đến khi đạt được giắ trị đúng đầu tiên thì giá trị sẽ trả về ngay lập tức mà không đụng tới các đối số khác 
```javascript
true || alert("not printed");
false || alert("printed");
```
### 3. && (AND)
```javascript
result = a && b;
```
+ AND trả về `true` nếu toán hạng là truthy, còn lại là `false`
```javascript
alert( true && true );   // true
alert( false && true );  // false
alert( true && false );  // false
alert( false && false ); // false
```
+ Example
```javascript
let hour = 12;
let minute = 30;

if (hour == 12 && minute == 30) {
  alert( 'The time is 12:30' );
}
```
```javascript
let hour = 12;
let minute = 30;

if (hour == 12 && minute == 30) {
  alert( 'The time is 12:30' );
}
```
+ cũng như `OR` một vài giá trị được cho phép với toán tử `AND`
```javascript
if (1 && 0) { // evaluated as true && false -> false
  alert( "won't work, because the result is falsy" );
}
```
## 4. AND “&&” finds the first falsy value
```javascript
result = value1 && value2 && value3;
```
+ Toán tử `AND` thực hiện như sau:
1. đánh giá toán tử từ trái sang phải
2. mỗi toán tử sẽ chuyển sang Boolean nếu kết quả là false thì dừng và trả lại giá trị nguyên bản của toán hạng đó
3. nếu tất cả toán hạng được đánh giá ( tất cả là truthy ) sẽ trả lại toán hạng cuối cùng.
+ Example
```javascript
// if the first operand is truthy,
// AND returns the second operand:
alert( 1 && 0 ); // 0
alert( 1 && 5 ); // 5

// if the first operand is falsy,
// AND returns it. The second operand is ignored
alert( null && 5 ); // null
alert( 0 && "no matter what" ); // 0
```
+ giá trị falsy đầu tiên được trả về
```javascript
alert( 1 && 2 && null && 3 ); // null
```
+ giá trị đúng cuối cùng được trả về
```javascript
alert( 1 && 2 && 3 ); // 3, the last one
```
+ Lưu ý:
1. mức độ ưu tiên của AND `&&` thì cao hơn OR `||`
2. Không thay thế `if` với AND `&&` và OR `||`
```javascript
let x = 1;

(x > 0) && alert( 'Greater than zero!' );
```
Hành động trong phần bên phải của && sẽ chỉ thực thi nếu đánh giá đạt được nó. Nghĩa là, chỉ khi (x> 0) là đúng.

```javascript
let x = 1;

if (x > 0) alert( 'Greater than zero!' );
```
### 5. ! (NOT)
```javascript
result = !value;
```
+ Toán tử chấp nhận 1 đối số như sau
1. Chuyển đổi toán tử đến Boolean: `true/false`
2. trả lại giá trị nghịch đảo
+ Example
```javascript
alert( !true ); // false
alert( !0 ); // true
```
+ `!!` sử dụng để chuyển đổi giá trị thành dạng Boolean, chuyển đổi nghịch đảo 2 lần để về không nghịch đảo.
```javascript
alert( !!"non-empty string" ); // true
alert( !!null ); // false
```
```javascript
alert( Boolean("non-empty string") ); // true
alert( Boolean(null) ); // false
```
---
## Error handling, "try...catch"
+ cú pháp cấu trúc `try...catch` cho pháp chúng ta `catch` các errors vì script có thể xử lí.
### 1. The “try…catch” syntax
+ `try...catch` cấu trúc có 2 main block `try` và sau đó là `catch`
```javascript
try {

  // code...

} catch (err) {

  // error handling

}
```
+ Quá trình:
1. đầu tiên code sẽ thực hiện trong `try`
2. Nếu không có lỗi thì `catch (err)` sẽ bỏ qua, việc thực thi sẽ đến cuối của `try` và tiếp tục bỏ qua `catch`
3. Nếu xảy ra lỗi thì việc thực thi `try` sẽ bị dừng lại và kiếm soát flow đến nơi bắt đầu `catch (err)`, Biến số `err` ( có thể đặt tên cho nó ) sẽ chứa error object với thông tin chi tiết những gì đã xảy ra

=>  vì vậy các error ở trong `try` sẽ không bị chết đi mà script sẽ thây đổi handle ở trong `catch`
+ Example
```javascript
try {

  alert('Start of try runs');  // (1) <--

  // ...no errors here

  alert('End of try runs');   // (2) <--

} catch (err) {

  alert('Catch is ignored, because there are no errors'); // (3)

} // (1), (2)
```
```javascript
try {

  alert('Start of try runs');  // (1) <--

  lalala; // error, variable is not defined!

  alert('End of try (never reached)');  // (2)

} catch (err) {

  alert(`Error has occurred!`); // (3) <--

}// (1), (3)
```
+ `try...catch` chỉ hoặt động runtime error (để hoặt động thì nó code trong `try` phải là javascript)
```javascript
try {
  {{{{{{{{{{{{// không phải là javascript code
} catch (err) {
  alert("The engine can't understand this code, it's invalid");
} //SyntaxError: Unexpected token 'catch'
```
+ `try...catch` hoặt động synchronously(bất đồng bộ)
```javascript
try {
  setTimeout(function() {
    noSuchVariable; // script will die here
  }, 1000);
} catch (err) {
  alert( "won't work" );
}
```
Để `setTimeout` ở ngoài `try...catch`
```javascript
setTimeout(function() {
  try {
    noSuchVariable; // try...catch handles the error!
  } catch {
    alert( "error is caught here!" );
  }
}, 1000);
```

### 2. Error object
+ `message`- thông báo lỗi con người có thể đọc được.
+ `name`- chuỗi có tên lỗi (tên hàm tạo lỗi).
+ `stack`(không chuẩn, nhưng được hỗ trợ tốt) - ngăn xếp tại thời điểm tạo lỗi.
```javascript
try {
  lalala; // error, variable is not defined!
} catch (err) {// <-- the "error object", could use another word instead of err
  alert(err.name); // ReferenceError
  alert(err.message); // lalala is not defined
  alert(err.stack); // ReferenceError: lalala is not defined at (...call stack)

  // Can also show an error as a whole
  // The error is converted to string as "name: message"
  alert(err); // ReferenceError: lalala is not defined
}
```
### 3. Optional “catch” binding
+ This is a recent addition to the language. Old browsers may need [polyfills](https://javascript.info/polyfills).
+ Nếu không cần thông tin chi tiết về lỗi, catch có thể bỏ qua:
```javascript
try {
  // ...
} catch { // <-- without (err)
  // ...
}
```
### 4. Using “try…catch”
+ sử dung để [JSON.parse(str)](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/parse) khi `Json` bị lỗi thì ta sẽ dùng `try...catch` để handle error
```javascript
let json = "{ bad json }";

try {

  let user = JSON.parse(json); // <-- when an error occurs...
  alert( user.name ); // doesn't work

} catch (err) {
  // ...the execution jumps here
  alert( "Our apologies, the data has errors, we'll try to request it one more time." );
  alert( err.name );
  alert( err.message );
}
```
### 5. Throwing our own errors
+ nếu `Json` về mặt cú pháp đúng nhưng không yêu cầu thuộc tính `name`
```javascript
let json = '{ "age": 30 }'; // incomplete data

try {

  let user = JSON.parse(json); // <-- no errors
  alert( user.name ); // no name!

} catch (err) {
  alert( "doesn't execute" );
}
//undefined
```
Để thống nhất việc sửa lỗi thì sẽ dùng toán tử `throw`
* #### “Throw” operator
1. Syntax:
```javascript
throw <error object>
```
2. Có nhiều các build-in cấu trúc tiêu chuẩn errors: `Error`, `SyntaxError`, `ReferenceError`, `TypeError` và có thể sử dụng để tạo các error object tốt
  ```javascript
  let error = new Error(message);
// or
let error = new SyntaxError(message);
let error = new ReferenceError(message);
// ...
```
 3. với toán tử `throw` sẽ tạo ra 1 `SyntaxError` có `message`

```javascript
let json = '{ "age": 30 }'; // incomplete data

try {

  let user = JSON.parse(json); // <-- no errors

  if (!user.name) {
    throw new SyntaxError("Incomplete data: no name"); // (*)
  }

  alert( user.name );

} catch (err) {
  alert( "JSON Error: " + err.message ); // JSON Error: Incomplete data: no name
}
```
### 6. Rethrowing 
+ `Rethrowing` kĩ thuật có thể giải thích các detail như
1. bắt được tất cả các lỗi
2. ở trong khối `catch (err) {...}` phân tích đối tượng lỗi `err`
3. nếu không biết handle thì dùng `throw err`
+ có thể kiểm tra loại error khi sử dụng toán tử `instanceof`
```javascript
try {
  user = { /*...*/ };
} catch (err) {
  if (err instanceof ReferenceError) {
    alert('ReferenceError'); // "ReferenceError" for accessing an undefined variable
  }
}
```
+ Sử dụng `Rethrowing` để cỏ thể `catch` chỉ handle `SyntaxError`

```javascript
let json = '{ "age": 30 }'; // incomplete data
try {

  let user = JSON.parse(json);

  if (!user.name) {
    throw new SyntaxError("Incomplete data: no name");
  }

  blabla(); // unexpected error

  alert( user.name );

} catch (err) {

  if (err instanceof SyntaxError) {
    alert( "JSON Error: " + err.message );//JSON Error: Incomplete data: no name
  } else {
    throw err; // rethrow (*)
  }

}
```
```javascript
function readData() {
  let json = '{ "age": 30 }';

  try {
    // ...
    blabla(); // error!
  } catch (err) {
    // ...
    if (!(err instanceof SyntaxError)) {
      throw err; // rethrow (don't know how to deal with it)
    }
  }
}

try {
  readData();
} catch (err) {
  alert( "External catch got: " + err ); // caught it!
}
```
### 7. try…catch…finally
+ `finally` là một block mà chúng ta có thể dùng để chạy code sau khi try và catch kết thúc, Finally sẽ vẫn chạy cho dù có lỗi xảy ra hay ko
+ Syntax
```javascript
try {
   ... try to execute the code ...
} catch (err) {
   ... handle errors ...
} finally {
   ... execute always ...
}
```
+ Example
```javascript
try {
  alert( 'try' );
  if (confirm('Make an error?')) BAD_CODE();
} catch (err) {
  alert( 'catch' );
} finally {
  alert( 'finally' );
}
// trả lời 'yes' thì  try -> catch -> finally.
// trả lời 'no' thì try -> finally.
```
---
## Promises, async/await
### 1. Introduction: callbacks
+  [Callback](https://suntech.edu.vn/callback-trong-javascript.sunpost.html) là một hàm sẽ được thực hiện sau khi một hàm khác đã thực hiện xong 
+  các hàm có thể lấy các hàm làm đối số và có thể được trả về bởi các hàm khác. Các hàm thực hiện điều này được gọi là higher - order function (Hàm bậc cao hơn).
+ Example:
```javascript
function loadScript(src, callback) {
  let script = document.createElement('script');
  script.src = src;
  script.onload = () => callback(script);
  document.head.append(script);
}

loadScript('https://cdnjs.cloudflare.com/ajax/libs/lodash.js/3.2.0/lodash.js', script => {
  alert(`Cool, the script ${script.src} is loaded`);
  alert( _ ); // _ is a function declared in the loaded script
});
```
#### 1. Callback in callback
+ Để tải tuần tự 2 script thì ta đặt script thứ 2 bên trong thứ nhất
```javascript
loadScript('/my/script.js', function(script) {

  alert(`Cool, the ${script.src} is loaded, let's load one more`);

  loadScript('/my/script2.js', function(script) {
    alert(`Cool, the second script is loaded`);
  });

});
```
+ Tương tự chúng ta sẽ có thể có script thứ 3 rồi thứ 4
```javascript
loadScript('/my/script.js', function(script) {

  loadScript('/my/script2.js', function(script) {

    loadScript('/my/script3.js', function(script) {
      // ...continue after all scripts are loaded
    });

  });

});
```
#### 2. Handling errors
+ Để theo dõi lỗi trong quá trình tải script
```javascript
function loadScript(src, callback) {
  let script = document.createElement('script');
  script.src = src;

  script.onload = () => callback(null, script);
  script.onerror = () => callback(new Error(`Script load error for ${src}`));

  document.head.append(script);
}// Nó sẽ trả về callback(null, script) nếu load thành công và callback(error) nếu thất bại.
```
+ Quy ước: 
1. `callback` đối số đầu tiên được dành 1 lỗi nếu nó xảy ra, `callback(err)` sẽ được gọi
2. Đối số thứ 2 (và những cái tiếp theo) cho kết quả thành công thì `callback(null, result1, result2…)` sẽ được gọi
-> Vì vậy `callback` function được sử dụng cả khai báo errors và trở lại kết quả.
#### 3. Pyramid of Doom
+ Cách `callback` lồng nhau chỉ hiệu quả nếu có 1,2,3 script nhưng nếu có nhiều script thì việc quản lý lồng nhau sẽ trở nên khó khăn, gọi nó là "callback hell" hay "pyramid of doom".
```javascript
loadScript('1.js', function(error, script) {

  if (error) {
    handleError(error);
  } else {
    // ...
    loadScript('2.js', function(error, script) {
      if (error) {
        handleError(error);
      } else {
        // ...
        loadScript('3.js', function(error, script) {
          if (error) {
            handleError(error);
          } else {
            // ...continue after all scripts are loaded (*)
          }
        });

      }
    });
  }
});
```
### 2. Promise
+ [Promise](https://suntech.edu.vn/lam-viec-voi-promises-trong-javascripts.sunpost.html) là một cơ trong JavaScript giúp bạn thực thi các tác vụ bất đồng bộ mà không rơi vào  tình trạng có quá nhiều các callback lồng vào nhau gây tình trạng callback hell hay pyramid of doom. Thực tế promises là 1 special JavaScript object thể hiện cho sự hoàn thành hoặc thất bại của một tiến trình bất đồng bộ.
+ Syntax
```javascript
let promise = new Promise(function(resolve, reject) {
  // executor (the producing code, "singer")
});
```
+ Khi promise thực thi hoàn thành công việc, nó sẽ gọi một trong 2 hàm là resolve(value) và reject(error)

![promise](https://javascript.info/article/promise-basics/promise-resolve-reject.svg)

1.`resolve(value)` với công việc hoàn thành kết quả là `value`
2.`reject(error)` nếu xảy ra lỗi, lỗi là error object
+ Đối tượng `promise` sẽ được trả lại bởi cấu trúc `new promise` có những thuộc tính nội bộ này
1. `state` lúc đầu là `pending`, sau đó thay đổi thành `fulfilled` khi `resolve` được gọi hoặc là `rejected` khi `reject` được gọi
2. `result` lúc đầu là `undefined` , sau đó thay đổi thành `value` khi `resolve` được gọi hoặc là `error` khi `reject(error)`

+ Then
1. Đối số đầu tiên của .then là một hàm chạy khi promise được giải quyết và nhận kết quả.
2. Đối số thứ hai của .then là một hàm chạy khi promise bị từ chối và nhận được lỗi.
```javascript
promise.then(
  function(result) { /* handle a successful result */ },
  function(error) { /* handle an error */ }
);
```
+ Catch
1. Nếu chỉ quan tâm đến sai sót, bạn có thể sử dụng  null như là đối số đầu tiên: .then(null, errorHandlingFunction). Hoặc chúng ta có thể sử dụng .catch(errorHandlingFunction)
+ Finally
1. Một finally trình xử lý không có đối số. Trong finally chúng ta không biết liệu promise có thành công hay không.
2. Một finally trình xử lý chuyển kết quả và lỗi cho trình xử lý tiếp theo.
---
### 3. Promises chaining
```javascript
new Promise(function(resolve, reject) {

  setTimeout(() => resolve(1), 1000); // (*)

}).then(function(result) { // (**)

  alert(result); // 1
  return result * 2;

}).then(function(result) { // (***)

  alert(result); // 2
  return result * 2;

}).then(function(result) {

  alert(result); // 4
  return result * 2;

});
// Promise ban đầu sẽ được giải quyết sau 1 giây (*)
// Sau đó, các .then được gọi (**).
// Giá trị mà nó trả về được chuyển cho chuỗi các trình xử lí  .then tiếp theo(***)]
// 
```
Thêm nhiều `.then` vào một `promise`
```javascript
let promise = new Promise(function(resolve, reject) {
  setTimeout(() => resolve(1), 1000);
});

promise.then(function(result) {
  alert(result); // 1
  return result * 2;
});

promise.then(function(result) {
  alert(result); // 1
  return result * 2;
});

promise.then(function(result) {
  alert(result); // 1
  return result * 2;
});
// Tất cả .then trên cùng một promise nhận được cùng một kết quả - kết quả của promise đó. 
```
### 1. Returning promises
+  sử dụng trong `.then(handler)` có thể tạo và trả về một `promise`.  Trong trường này, các handler tiếp theo sẽ đợi và sau đó nó sẽ nhận được kết quả. 
```javascript
new Promise(function(resolve, reject) {

  setTimeout(() => resolve(1), 1000);

}).then(function(result) {

  alert(result); // 1

  return new Promise((resolve, reject) => { // (*)
    setTimeout(() => resolve(result * 2), 1000);
  });

}).then(function(result) { // (**)

  alert(result); // 2

  return new Promise((resolve, reject) => {
    setTimeout(() => resolve(result * 2), 1000);
  });

}).then(function(result) {

  alert(result); // 4

});
```
### 2. Xây dựng function loadScript 
```javascript
loadScript("/article/promise-chaining/one.js").then(script1 => {
  loadScript("/article/promise-chaining/two.js").then(script2 => {
    loadScript("/article/promise-chaining/three.js").then(script3 => {
      // this function has access to variables script1, script2 and script3
      one();
      two();
      three();
    });
  });
});
// loadScript  trả về một promise và lệnh tiếp theo  .then  được 
// chạy và giải quyết xong thì nó bắt đầu tải tập lệnh tiếp theo. 
// Vì vậy, các tập lệnh được tải lần lượt và chúng ta có thể thêm 
// nhiều hành động bất đồng bộ hơn vào chuỗi
```
### 4. Error handling with promises
```javascript
fetch('/article/promise-chaining/user.json')
  .then(response => response.json())
  .then(user => fetch(`https://api.github.com/users/${user.name}`))
  .then(response => response.json())
  .then(githubUser => new Promise((resolve, reject) => {
    let img = document.createElement('img');
    img.src = githubUser.avatar_url;
    img.className = "promise-avatar-example";
    document.body.append(img);

    setTimeout(() => {
      img.remove();
      resolve(githubUser);
    }, 3000);
  }))
  .catch(error => alert(error.message));
  // .catch có thể xuất hiện sau một hoặc có thể một vài .then 
  // Nếu bất kỳ promises  nào ở trên bị từ chối (do sự cố mạng 
  // hoặc json không hợp lệ hoặc bất cứ điều gì), thì .catch 
  // sẽ bắt được các lỗi đó.
  ```
  ### 1. Implicit try...catch
  + Các đoạn code của chúng ta có thể vô hình có một `try..catch` xung quanh để khi có sự cố nào đó xảy ra lỗi đó sẽ bị từ chối. 
  + Nếu chúng ta `throw` bên trong một .then, điều đó có nghĩa là một promises bị từ chối, do đó trình điều khiển sẽ chuyển nó đến trình xử lý lỗi gần nhất. 
  ```javascript
  new Promise((resolve, reject) => {
  resolve("ok");
}).then((result) => {
  throw new Error("Whoops!"); // rejects the promise
}).catch(alert); // Error: Whoops!
```
### 2. Rethrowing
+ với `try..catch` chúng ta có thể phân tích lỗi và có thể `rethrow` nó nếu không thể xử lý được.Nếu `throw` bên trong .catch, thì trình điều khiển sẽ chuyển nó đến trình xử lý lỗi gần nhất tiếp theo. Và nếu chúng ta xử lý lỗi và kết thúc bình thường, thì nó sẽ tiếp tục đến .then gần nhất
```javascript
// the execution: catch -> catch
new Promise((resolve, reject) => {

  throw new Error("Whoops!");

}).catch(function(error) { // (*)

  if (error instanceof URIError) {
    // handle it
  } else {
    alert("Can't handle such error");

    throw error; // throwing this or another error jumps to the next catch
  }

}).then(function() {
  /* doesn't run here */
}).catch(error => { // (**)

  alert(`The unknown error has occurred: ${error}`);
  // don't return anything => execution goes the normal way

});
```
### 3. Unhandled rejections
+ Nếu có lỗi xảy ra và không có .catch, unhandledrejection sẽ kích hoạt và lấy event của đối tượng và thông tin về lỗi, vì vậy chúng ta có thể khắc phục nó thông qua các thông báo về lỗi. 
```javascript
window.addEventListener('unhandledrejection', function(event) {
  // the event object has two special properties:
  alert(event.promise); // [object Promise] - the promise that generated the error
  alert(event.reason); // Error: Whoops! - the unhandled error object
});

new Promise(function() {
  throw new Error("Whoops!");
}); // no catch to handle the error
```
---
### 5. Promise API
### 1.  Promise.all
+ Promises.all: muốn nhiều promise được thực thi song song và xử lí khi tất cả chúng đã sẵn sàng.
+ syntax
```javascript
let promise = Promise.all([...promises...]);
```
```javascript
Promise.all([
  new Promise(resolve => setTimeout(() => resolve(1), 3000)), // 1
  new Promise(resolve => setTimeout(() => resolve(2), 2000)), // 2
  new Promise(resolve => setTimeout(() => resolve(3), 1000))  // 3
]).then(alert); // 1,2,3 when promises are ready: each promise contributes an array member
//  settles 3 giây và sau đó nó cho ra kết quả là một mảng [1, 2, 3]
```
+ Lưu ý: Nếu bất kỳ `promise` nào bị từ chối, promise được trả về `Promise.all` sẽ bị từ chối ngay lập tức với chính lỗi đó
```javascript
Promise.all([
  new Promise((resolve, reject) => setTimeout(() => resolve(1), 1000)),
  new Promise((resolve, reject) => setTimeout(() => reject(new Error("Whoops!")), 2000)),
  new Promise((resolve, reject) => setTimeout(() => resolve(3), 3000))
]).catch(alert); // Error: Whoops!
//  promises  thứ hai bị từ chối trong hai giây. Điều đó dẫn đến
// việc từ chối ngay lập tức Promise.all, vì vậy sẽ .catch sẽ thực
// thi: lỗi từ chối trở thành kết quả của toàn bộ Promise.all.
```
+ `Promise.all(iterable)` cho phép các giá trị `non-promise `"thông thường" trong iterable
```javascript
Promise.all([
  new Promise((resolve, reject) => {
    setTimeout(() => resolve(1), 1000)
  }),
  2,
  3
]).then(alert); // 1, 2, 3
```
### 2.  Promises.allSettled
+ `Promise.allSettled` chỉ cần đợi cho tất cả các `promise` giải quyết, bất kể kết quả. Mảng kết quả có
1. `{status:"fulfilled", value:result}` để có phản hồi thành công,
2. `{status:"rejected", reason:error}` cho các lỗi.
```javascript
let urls = [
  'https://api.github.com/users/iliakan',
  'https://api.github.com/users/remy',
  'https://no-such-url'
];

Promise.allSettled(urls.map(url => fetch(url)))
  .then(results => { // (*)
    results.forEach((result, num) => {
      if (result.status == "fulfilled") {
        alert(`${urls[num]}: ${result.value.status}`);
      }
      if (result.status == "rejected") {
        alert(`${urls[num]}: ${result.reason}`);
      }
    });
  });
  // https://api.github.com/users/iliakan: 200
  // https://api.github.com/users/remy: 200
  // https://no-such-url: TypeError: Failed to fetch
  ```
  ### 3. Promise.race
  + Tương tự như `Promise.all`, nhưng nó chỉ đợi `promise` đã giải quyết đầu tiên và nhận kết quả (hoặc lỗi) của nó
  + syntax
  ```javascript
  let promise = Promise.race(iterable);
  ```
  ```javascript
  Promise.race([
  new Promise((resolve, reject) => setTimeout(() => resolve(1), 1000)),
  new Promise((resolve, reject) => setTimeout(() => reject(new Error("Whoops!")), 2000)),
  new Promise((resolve, reject) => setTimeout(() => resolve(3), 3000))
  ]).then(alert); // 1
  // Lấy promise đầu tiên 
```
  ### 4. Promise.any
  + Tương tự như `Promise.race`, nhưng chỉ đợi `promise` đầu tiên được thực thi và nhận được kết quả của nó. Nếu tất cả các `promise` đã cho đều bị từ chối, thì promise trả về sẽ bị từ chối với `AggregateError`
  + syntax
  ```javascript
  + let promise = Promise.any(iterable);
  ```
  ```javascript
  Promise.any([
  new Promise((resolve, reject) => setTimeout(() => reject(new Error("Whoops!")), 1000)),
  new Promise((resolve, reject) => setTimeout(() => resolve(1), 2000)),
  new Promise((resolve, reject) => setTimeout(() => resolve(3), 3000))
]).then(alert); // 1
  ```
  ```javascript 
  Promise.any([
  new Promise((resolve, reject) => setTimeout(() => reject(new Error("Ouch!")), 1000)),
  new Promise((resolve, reject) => setTimeout(() => reject(new Error("Error!")), 2000))
]).catch(error => {
  console.log(error.constructor.name); // AggregateError
  console.log(error.errors[0]); // Error: Ouch!
  console.log(error.errors[1]); // Error: Error
});
// các lỗi của promise đều có sẵn trong thuộc tính errors của đối tượng AggregateError
```
### 5. Promise.resolve
+ `Promise.resolve(value)` tạo ra một `promise` đã được giải quyết với kết quả `value`
+ syntax
```javascript
let promise = new Promise(resolve => resolve(value));
```
### 6. Promise.reject
+ `Promise.reject(error)`  được tạo ra một promise bị từ chối với `error`
+ syntax
```javascript
let promise = new Promise((resolve, reject) => reject(error));
```
---
### 6. Async/await 
+ Async / Await là một tính năng của JavaScript giúp chúng ta làm việc với các hàm bất đồng bộ theo cách thú vị hơn và dễ hiểu hơn. Nó được xây dựng trên promise và tương thích với tất cả các promise dựa trên API. 
### 1. Async functions
+ Async functions là hàm bất đồng bộ. 
```javascript
async function f() {
  return Promise.resolve(1);
}

f().then(alert); // 1
// hãy đảm bảo rằng hàm async trả về một promise. Nhưng không chỉ
// có vậy. Chúng ta có thể dùng await. Nó chỉ hoạt động bên trong 
// các async functions.
```
### 2.Await
+ syntax
```javascript
// works only inside async functions
let value = await promise;
```
+ await khi được đặt trước một promise, nó sẽ đợi cho đến khi promise kết thúc và trả về kết quả. 
+ Ưu điểm: không tốn bất kỳ tài nguyên CPU nào, vì JavaScript có thể thực hiện các công việc khác trong thời gian chờ đợi
```javascript
async function f() {

  let promise = new Promise((resolve, reject) => {
    setTimeout(() => resolve("done!"), 1000)
  });

  let result = await promise; // wait until the promise resolves (*)

  alert(result); // "done!"
}

f();
``` 
### 3. Error handling
+ Nếu một promise được xử lí bình thường, thì await promise  sẽ trả về kết quả. Nhưng trong trường hợp bị từ chối, nó sẽ tạo ra lỗi.
```javascript
async function f() {

  try {
    let response = await fetch('http://no-such-url');
  } catch(err) {
    alert(err); // TypeError: failed to fetch
  }
}

f();
```
### 4. Summary
+ Việc sử dụng async/await có một số ưu điểm vượt trội:

1. Code dễ đọc hơn rất rất nhiều, không cần phải then rồi catch, chỉ viết như bình thường, sau đó dùng try/catch để bắt lỗi.
2. Debug dễ hơn nhiều, vì mỗi lần dùng await được tính là một dòng code, do đó ta có thể đặt debugger để debug từng dòng như thường.
3. Khi có lỗi, exception sẽ chỉ ra lỗi ở dòng số mấy chứ không chung chung là un-resolved promise.
4. Với promise hoặc callback, việc kết hợp if/else hoặc retry với code asynchnous là một điều gì đó khá khó chịu. Với async/await, việc này vô cùng dễ dàng.
---
## Export and Import
```javascript
//Before declaration of a class/function/…:
export [default] class/function/variable ...

//Standalone export:
export {x [as y], ...}.

//Re-export:
export {x [as y], ...} from "module"
export * from "module" (doesn’t re-export default).
export {default [as y]} from "module" (re-export default).

//Import:

//Importing named exports:
import {x [as y], ...} from "module"

//Importing the default export:
import x from "module"
import {default as x} from "module"

//Import all:
import * as obj from "module"

//Import the module (its code runs), but do not assign any of its exports to variables:
import "module"
```
---
## Class
### 1. syntax
```javascript
class MyClass {
  // class methods
  constructor() { ... }
  method1() { ... }
  method2() { ... }
  method3() { ... }
  ...
}
// new MyClass() để tạo một đối tượng mới với tất cả các phương thức được liệt kê

// constructor phương thức được gọi tự động bởi new, vì vậy chúng ta có thể khởi tạo đối tượng ở đó.
```
```javascript
//// Class declaration
class User {
  constructor(name) { this.name = name; }
  sayHi() { alert(this.name); }
}

// proof: User is a function
alert(typeof User); // function

//// Class Expression
let User = class {
  sayHi() {
    alert("Hello");
  }
};
```
### 2. Getters/setters
+ Phương thức getter giúp ta lấy thuộc tính của đối tượng class
+ Phương thức setters mục đích của nó là lưu trữ giá trị cho các thuộc tính..
```javascript
class User {

  constructor(name) {
    // invokes the setter
    this.name = name;
  }

  get name() {
    return this._name;
  }

  set name(value) {
    if (value.length < 4) {
      alert("Name is too short.");
      return;
    }
    this._name = value;
  }

}

let user = new User("John");
alert(user.name); // John

user = new User(""); // Name is too short.
```
### 3. Class inheritance
+ Kế thừa 1 class để mở rộng 1 class khác
```javascript
//Đây là lớp cha
class Person {
    constructor(name, age) {
        this.name= name;
        this.age= age;
    }
    show() {
       return `Tối tên là: ${this.name}, ${this.age} tuổi`;
    }
 }
 //Đây là lớp con
 class Student extends Person {
     constructor(idSV, name, age) {
         super(name,age);//Phương thức super() này là phương thức tham chiếu đến lớp cha
         this.idSV = idSV;
     }
     showInfo() {
        return `Mã SV: ${this.idSV}` + this.show();
     }
 }
 ```
 ---
 ### 4. Static properties and methods
 + Có thể chỉ định phương thức class nói chung, chẳng hạn nhiều phương thức được gọi là `static`
 + Static trong lập trình hướng đối tượng OOP là một thành phần tĩnh có thể là thuộc tính hoặc phương thức.
 ```javascript
 class Animal {
  static planet = "Earth";

  constructor(name, speed) {
    this.speed = speed;
    this.name = name;
  }

  run(speed = 0) {
    this.speed += speed;
    alert(`${this.name} runs with speed ${this.speed}.`);
  }

  static compare(animalA, animalB) {
    return animalA.speed - animalB.speed;
  }

}

// Inherit from Animal
class Rabbit extends Animal {
  hide() {
    alert(`${this.name} hides!`);
  }
}

let rabbits = [
  new Rabbit("White Rabbit", 10),
  new Rabbit("Black Rabbit", 5)
];

rabbits.sort(Rabbit.compare);// sort sắp xếp các phần tử đầu tăng dần từ 1 ->, A ->

rabbits[0].run(); // Black Rabbit runs with speed 5.

alert(Rabbit.planet); // Earth
```
---
### 5. Class checking: "instanceof"
+ `instance of`: toán tử cho phép kiểm tra một đối tượng có thuộc class nào đó hay không. Nó cũng tính đến tính kế thừa.
+ syntax
```javascript
obj instanceof Class
```
+Example
```javascript
class Animal {}
class Rabbit extends Animal {}

let rabbit = new Rabbit();
alert(rabbit instanceof Animal); // true
```
+ `instance of` cũng có thể đặt một logic tùy chỉnh trong phương thức `Symbol.hasInstance`
```javascript
// setup instanceOf check that assumes that
// anything with canEat property is an animal
class Animal {
  static [Symbol.hasInstance](obj) {
    if (obj.canEat) return true;
  }
}

let obj = { canEat: true };

alert(obj instanceof Animal); // true: Animal[Symbol.hasInstance](obj) is called
```
###  Object.prototype.toString for the type
+ syntax
```javascript
let obj = {};

alert(obj); // [object Object]
alert(obj.toString()); // the same
```
1. For a number, it will be [object Number]
2. For a boolean, it will be [object Boolean]
3. For null: [object Null]
4. For undefined: [object Undefined]
5. For arrays: [object Array]

```javascript
let s = Object.prototype.toString;

alert( s.call(123) ); // [object Number]
alert( s.call(null) ); // [object Null]
alert( s.call(alert) ); // [object Function]
```
---
## Mixin
+ mixin là 1 class chứa nhiều methods để sử dụng được trong các class khác mà không cần phải có quan hệ cha-con.
```javascript
// mixin
let sayHiMixin = {
  sayHi() {
    alert("Hello " + this.name);
  },
  sayBye() {
    alert("Bye " + this.name);
  }
};

// usage:
class User {
  constructor(name) {
    this.name = name;
  }
}

// copy the methods
Object.assign(User.prototype, sayHiMixin);

// now User can say hi
new User("Dude").sayHi(); // Hi Dude!
//tạo 1 mixin chứa 2 phương thức sayHi() và sayBye() sau đó copy
// các phương thức đó vào trong class User bằng phương thức 
//assign của Object, sau đó chúng ta có thể gọi 2 phương thức 
//sayHi() và sayBye() từ User mà không cần định nghĩa lại hai 
//phuong thức này
```
+ Mixin cũng có thể kế thừa từ một mixin khác
```javascript
let sayMixin = {
  say(phrase) {
    alert(phrase);
  }
};

let sayHiMixin = {
  __proto__: sayMixin, // (or we could use Object.create to set the prototype here)

  sayHi() {
    // call parent method
    super.say("Hello " + this.name);
  },
  sayBye() {
    super.say("Bye " + this.name);
  }
};

class User {
  constructor(name) {
    this.name = name;
  }
}

// copy the methods
Object.assign(User.prototype, sayHiMixin);

// now User can say hi
new User("Dude").sayHi(); // Hello Dude!
```
+ EventMixin Chức năng quan trọng của nhiều object là làm việc với các event. Có thể hiểu là một object sẽ chứa các method làm nhiệm vụ tạo ra các event khi có vấn đề gì đó xảy ra, và object còn lại thì sẳn sàng để lắng nghe những event đó.
---
## Date and time
```javascript
let now = new Date();
alert( now ); // shows current date/time
```
+ Setting date components
1. setFullYear(year, [month], [date])
2. setMonth(month, [date])
3. setDate(date)
4. setHours(hour, [min], [sec], [ms])
5. setMinutes(min, [sec], [ms])
6. setSeconds(sec, [ms])
7. setMilliseconds(ms)
8. setTime(milliseconds) (sets the whole date by milliseconds since 01.01.1970 UTC)
+ Date.parse from a string
1. YYYY-MM-DD – is the date: year-month-day.
2. HH:mm:ss.sss – is the time: hours, minutes, seconds and milliseconds.
3. Ký tự “T” được sử dụng làm dấu phân cách.
4. Phần ‘Z’ tùy chọn biểu thị múi Time ở định dạng + -hh: mm. Một chữ cái Z có nghĩa là UTC + 0.
```javascript
let date = new Date( Date.parse('2012-01-26T13:51:50.417-07:00') );

alert(date)
```
---




