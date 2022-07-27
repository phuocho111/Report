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
    - [1.  Number](#1--number)
    - [2. BigInt](#2-bigint)
    - [3.  String](#3--string)
    - [4. Boolean (logical type)](#4-boolean-logical-type)
    - [5. Giá trị Null](#5-giá-trị-null)
    - [6. Giá trị Undefined](#6-giá-trị-undefined)
    - [7. Object](#7-object)
    - [8. Symbols](#8-symbols)
    - [9. The typeof operator](#9-the-typeof-operator)
  - [Loops: while and for](#loops-while-and-for)
    - [1. The "while" loop](#1-the-while-loop)
    - [2.The “do…while” loop](#2the-dowhile-loop)
    - [3.The “for” loop](#3the-for-loop)
      - [Skipping parts](#skipping-parts)
    - [4. Breaking the loop](#4-breaking-the-loop)
    - [5. Continue to the next iteration](#5-continue-to-the-next-iteration)
    - [6. Labels for break/continue](#6-labels-for-breakcontinue)
    - [7. Summary:](#7-summary)
  - [- `for` - Điều kiện được kiểm tra trước mỗi lần lặp, cài đặt bổ sung có sẵn.](#--for---điều-kiện-được-kiểm-tra-trước-mỗi-lần-lặp-cài-đặt-bổ-sung-có-sẵn)
  - [The "switch" statement](#the-switch-statement)
    - [1. The syntax](#1-the-syntax)
    - [2. An example](#2-an-example)

## Data types

## I.Kiểu dữ liệu

### 1.  Number
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
### 3.  String
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
### 2.The “do…while” loop
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
### 3.The “for” loop
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