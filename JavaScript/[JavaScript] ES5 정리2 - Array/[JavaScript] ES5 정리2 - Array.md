# [JavaScript] ES5 정리2 - Array



## 1. Array.isArray()

객체가 배열인지 확인합니다.

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
console.log(Array.isArray(fruits)); // true
```



## 2. Array.forEach()

배열의 원소에 대해 한 번씩 함수를 호출합니다.

```javascript
var num = 0;
var numbers = [45, 4, 9, 16, 25];
numbers.forEach(myFunction);

function myFunction(value) {
  num += value;
}

console.log(num); // 99
```



## 3. Array.map()

배열을 순회하며, 함수의 반환값을 원소로하는 새로운 배열을 반환합니다.

```javascript
var numbers1 = [45, 4, 9, 16, 25];
var numbers2 = numbers1.map(myFunction);

function myFunction(value) {
  return value * 2;
}

console.log(numbers2); // [ 90, 8, 18, 32, 50 ]
```



## 4. Array.filter()

배열에서 조건에 맞는 원소들을 모아 새로운 배열을 반환합니다.

```javascript
var numbers = [45, 4, 9, 16, 25];
var over18 = numbers.filter(myFunction);

function myFunction(value) {
  return value > 18;
}

console.log(over18); //[ 45, 25 ]
```



## 5. Array.reduce()

배열을 순회하며, 원소값을 통해 새로운 값을 만들어 반환합니다.

```javascript
var numbers1 = [45, 4, 9, 16, 25];
var sum = numbers1.reduce(myFunction);

function myFunction(total, value) {
  return total + value;
}

console.log(sum); // 99
```

`arr.reduce(callback(accumulator, currentValue))`

* `accumulator`: 콜백의 이전 반환값
* `currentValue`: 처리할 현재 요소



## 6. Array.reduceRight()

`reduce`와 기능은 같으나 역순으로 순회합니다.

```javascript
var numbers1 = [45, 4, 9, 16, 25];
var diff = numbers1.reduceRight(myFunction);

function myFunction(total, value) {
  return total - value;
}

console.log(diff); // -49
```



## 7. Array.every()

배열의 모든 원소가 조건을 만족한다면 `true`를 반환합니다.

```javascript
var numbers = [45, 4, 9, 16, 25];
var allOver18 = numbers.every(myFunction);

function myFunction(value) {
  return value > 18;
}

console.log(allOver18); // false
```



## 8. Array.some()

배열에서 원소가 하나라도 조건을 만족한다면 `true`를 반환합니다.

```javascript
var numbers = [45, 4, 9, 16, 25];
var someOver18 = numbers.some(myFunction);

function myFunction(value) {
  return value > 18;
}

console.log(someOver18); // true
```



## 9. Array.indexOf()

배열에서 원소를  검색하고 해당 위치를 반환합니다. (찾지 못했다면 -1 반환)

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
var appleIdx = fruits.indexOf("Apple");
var grapeIdx = fruits.indexOf("Grape");

console.log(appleIdx); // 2
console.log(grapeIdx); // -1
```



## 10. Array.lastIndexOf()

`indexOf`와 기능은 같으나 역순으로 순회합니다.

```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
var appleIdx = fruits.lastIndexOf("Apple");
var grapeIdx = fruits.lastIndexOf("Grape");

console.log(appleIdx); // 2
console.log(grapeIdx); // -1
```



## 참조

* [w3schools - ECMAScript 2009 - ES5](https://www.w3schools.com/js/js_es5.asp)
* [JavaScript ES5 ( ECMAScript 5 )](https://blog.naver.com/zoz0312/221670693965)|**작성자** [AJu](https://blog.naver.com/zoz0312)





