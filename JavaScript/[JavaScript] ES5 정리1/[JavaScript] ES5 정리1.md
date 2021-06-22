# [JavaScript] ES5 정리1



## 1. Strict mode

Strict mode에서 잘못된 구문을 실제 오류로 변경합니다.

```javascript
"use strict";
x = 3.14; // Error by strict mode
```



## 2. String.trim()

문자열 앞과 뒤의 공백을 제거합니다.

```javascript
var str = "       Hello World!        ";
console.log(str.trim()); // Hello World!
```



## 3. Property Access [] on strings

문자열에 대한 속성 액세스를 허용합니다.

```javascript
var str = "HELLO WORLD";
console.log(str[0]); // H
```



## 4. JSON.parse()

 JSON을 String에서 Object로 형변환시킵니다.

```javascript
var str = '{"name":"John", "age":30, "city":"New York"}';
var obj = JSON.parse(str);

console.log(typeof str); // string
console.log(typeof obj); // object
```



## 5. JSON.stringify()

 JSON을 Object에서 String으로 형변환 시킵니다.

```javascript
var obj = {name:"John", age:30, city:"New York"};
var str = JSON.stringify(obj);

console.log(typeof obj); // object
console.log(typeof str); // string
```



## 6. Date.now ()

현재 시간과 zero date (January 1. 1970 00:00:00 UTC)의 차이를 밀리세컨즈로 반홥합니다.

```javascript
var timInMSs = Date.now();
console.log(timInMSs); // 1624368615644 (매번 결과 다름)
```



## 7. Trailing Commas

객체 및 배열 정의에서 후행 쉼표를 허용합니다.

```javascript
person = {
  firstName: "John",
  lastName: " Doe",
  age: 46,
}

points = [
  1,
  5,
  10,
  25,
  40,
  100,
];
```



## 8. Reserved Words as Property Names

예약어를 속성 이름으로 허용합니다.

```javascript
var obj = {name: "John", new: "yes"}
```



## 참조

* [w3schools - ECMAScript 2009 - ES5](https://www.w3schools.com/js/js_es5.asp)
* [JavaScript ES5 ( ECMAScript 5 )](https://blog.naver.com/zoz0312/221670693965)|**작성자** [AJu](https://blog.naver.com/zoz0312)

