# [JavaScript] ES5 정리3 - Object



## 1. 종류



### Property Descriptor

| 이름         | 설명                    |
| ------------ | ----------------------- |
| value        | 설정할 값               |
| writable     | 값 변경 가능 여부       |
| get          | 값 반환 프로퍼티 함수   |
| set          | 값 설정 프로퍼티 함수   |
| enumerable   | 프로퍼티 열거 가능 여부 |
| configurable | 프로퍼티 삭제 가능 여부 |



### Object 함수

| 이름                       | 설명                                    |
| -------------------------- | --------------------------------------- |
| defineProperty()           | 프로퍼티 추가, 프로퍼티 속성 변경       |
| defineProperties()         | 다수의 프로퍼티 추가, 속성 변경         |
| getPrototypeOf()           | prototype에 연결된 프로퍼티 반환        |
| getOwnPropertyNames()      | 프로퍼티 이름을 배열로 반환             |
| keys()                     | 열거 가능 프로퍼티 이름 반환            |
| getOwnPropertyDescriptor() | 디스크립터 속성 반환                    |
| preventExtensions()        | 프로퍼티 추가 금지 설정                 |
| isExtensible()             | 프로퍼티 추가 금지 여부 반환            |
| seal()                     | 프로퍼티 추가, 삭제 금지 설정           |
| isSealed()                 | 프로퍼티 추가, 삭제 금지 여부 반환      |
| freeze()                   | 프로퍼티 추가, 삭제/변경 금지 설정      |
| isFrozen()                 | 프로퍼티 추가, 삭제/변경 금지 여부 반환 |



## 2. 프로퍼티 정의



### defineProperty()

```javascript
var obj = {
  oldProp : 'oldVlue'
};

// Change Old Property
Object.defineProperty(obj, 'oldProp', {
  value: 'changeValue'
});
console.log(obj); // { oldProp: 'changeValue' }

// New Property
Object.defineProperty(obj, 'newProp', {
  value: 'newValue',
  enumerable: true
});
console.log(obj); // { oldProp: 'changeValue', newProp: 'newValue' }
```



### defineProperties()

```javascript
var obj = {};

Object.defineProperties(obj, {
  soccer: {
    value: '축구'
  },
  baseball: {
    value: '야구',
    enumerable: true
  }
});

console.log(obj); // { baseball: '야구' }
console.log(obj.soccer); // 축구
```



## 2. 프로퍼티 디스크립터

| 타입   | 속성 이름    | 속성 값                     | 디폴트 값 | 기능                       |
| ------ | ------------ | --------------------------- | --------- | -------------------------- |
| data   | value        | JS 지원 데이터 타입         | undefined | 프로퍼티 값으로 사용       |
|        | writable     | true, false                 | false     | false: value 값 변경 불가  |
| access | get          | Function Obeject, undefined | undefined | 프로퍼티 함수              |
|        | set          | Function Obeject, undefined | undefined | 프로퍼티 함                |
| public | enumerable   | true, false                 | false     | false: for-in으로열거 불가 |
|        | configurable | true, false                 | false     | false: 프로퍼티 삭제 불가  |

* 디스크립터 타입에 속한 속성만 같이 사용할 수 있습니다.
* 데이터 타입과 액세스 타입은 같이 사용할 수 없습니다. 

### 디스크립터 타입 인식 기준

**value 또는 writable 작성 확인**

* 작성되어 있는 경우
  * 데이터 프로퍼티 디스크립터 타입으로 인식
* 작성되어 있지 않은 경우
  * 액세스 프로퍼티 디스크립터 타입으로 인식



### value

```javascript
var obj = {};

Object.defineProperty(obj, 'book', {
  value: 'HarryPotter',
  enumerable: true,
  configurable: true
});

console.log(obj); // { book: 'HarryPotter' }

// ---

var obj2 = {};

Object.defineProperty(obj, 'fruit', {
  value: 'banana',
  enumerable: true,
  writable: true,
  configurable: true,
  get frt() {
    return this.fruit;
  },
  set frt(value) {
    this.fruit = value;
  }
});

console.log(obj2); // {}
```



### writable

```javascript
var obj = {};
Object.defineProperty(obj, 'movie', {
  value: 'HarryPotter',
  writable: true
});

obj.book = "Leon"
console.log(obj.book); // Leon

// ---

var obj2 = {};
Object.defineProperty(obj2, 'fruit', {
  value: 'Banana',
  writable: false
});

obj2.fruit = "Apple"
console.log(obj2.fruit); // Banana
```



### enumerable

```javascript
var obj = {};
Object.defineProperty(obj, 'movie', {
  value: 'HarryPotter',
  enumerable: true
});

for (var name in obj){
  console.log('obj1: ' + obj[name]); // obj1: HarryPotter
}
console.log(Object.keys(obj)); // [ 'movie' ]

// ---

var obj2 = {};
Object.defineProperty(obj2, 'fruit', {
  value: 'Banana',
  enumerable: false
});

for (var name in obj2){
  console.log('obj2: ' + obj[name]); //
}
console.log(Object.keys(obj2)); // []
```



### configurable

```javascript
var obj = {};
Object.defineProperty(obj, 'movie', {
  value: 'HarryPotter',
  configurable: true
});

delete obj.movie;
console.log(obj.movie); // undefined

// ---

var obj2 = {};
Object.defineProperty(obj2, 'fruit', {
  value: 'Banana',
  configurable: false
});

delete obj2.fruit;
console.log(obj2.fruit); // Banana
```



## 3. Getters & Setters

```javascript
var person = {
    firstName: "John",
    lastName : "Doe",
    language : "NO",
    get lang() {
        return this.language;
    },
    set lang(value) {
        this.language = value.toUpperCase();
    }
};

person.lang = "en";
console.log(person.lang); // EN
```



## 4. 프로퍼티 추출



### getPrototypeOf()

```javascript
function Book(point) {
  this.point = point;
};
Book.prototype.getPoint = function(){};
Book.prototype.setPoint = function(){};
var obj = new Book(100);

var result = Object.getPrototypeOf(obj);
for (var key in result){
  console.log(key + ":" + result[key]);
}
// getPoint:function(){}
// setPoint:function(){}
```



### getOwnPropertyNames()

```javascript
var obj = {};
Object.defineProperties(obj, {
  book: { value: 'HarryPotter' },
  point: { value: 123 }
});

console.log(Object.getOwnPropertyNames(obj));
// [ 'book', 'point' ]
```



### keys()

```javascript
var obj = {};
Object.defineProperties(obj, {
  book: { value: 'HarryPotter', enumerable: true },
  fruit: { value: 'Banana', enumerable: true },
  point: { value: 123 }	// enumerable: false
});

console.log(Object.keys(obj));
// [ 'book', 'fruit' ]
```



## 5. 프로퍼티 디스크립터 함수



### getOwnPropertyDescriptor()

```javascript
var obj = {};
Object.defineProperty(obj, 'book', {
  value: 'HarryPotter',
  writable: true,
  enumerable: true
});

console.log(Object.getOwnPropertyDescriptor(obj, 'book'));
// { value: 'HarryPotter',
//   writable: true,
//   enumerable: true,
//   configurable: false }
```



### preventExtensions()

```javascript
var obj = {};
Object.preventExtensions(obj);
try{
  Object.defineProperty(obj, 'book', {
    value: 'HarryPotter'
  });
}catch(e){
  console.log(e);
  // TypeError: Cannot define property book, object is not extensible
}
```



### isExtensible()

```javascript
var obj = {}
Object.defineProperties(obj, {
  book: { value: 'HarryPotter' }
});
console.log(Object.isExtensible(obj)); // true

Object.preventExtensions(obj);
console.log(Object.isExtensible(obj)); // false
```



### seal()

```javascript
var obj = {};
Object.defineProperty(obj, 'book', {
  value: 'HarryPotter',
  writable: true
});

Object.seal(obj);

try{
  Object.defineProperty(obj, 'sports', {
    value: 'soccer'
  });
}catch(e){
  console.log(e);
  // TypeError: Cannot define property sports, object is not extensible
}
```



### isSealed()

```javascript
var obj = {}
Object.defineProperties(obj, {
  book: { value: "HarryPotter" }
});
console.log(Object.isSealed(obj)); // false

Object.seal(obj);
console.log(Object.isSealed(obj)); // true
```



### freeze()

```javascript
var obj = {};
Object.defineProperty(obj, 'book', {
  value: 'HarryPotter',
  writable: true
});

Object.freeze(obj);

try{
  Object.defineProperty(obj, 'book', {
    value: 'Ant'
  });
}catch(e){
  console.log(e);
  // TypeError: Cannot redefine property: book
}
```



### isFrozen()

```javascript
var obj = {}
Object.defineProperties(obj, {
  book: { value: "HarryPotter" }
});
console.log(Object.isFrozen(obj)); // false

Object.seal(obj);
console.log(Object.isFrozen(obj)); // true
```



## 참조

* [w3schools - JavaScript ES5 Object Methods](https://www.w3schools.com/js/js_object_es5.asp)
* [newsilver.log - [JavaScript] Object 오브젝트 (ES5)](https://velog.io/@newsilver1028/Javascript-Object-%EC%98%A4%EB%B8%8C%EC%A0%9D%ED%8A%B8-ES51)
* [Catsbi's Dlog](https://catsbi.oopy.io/51beb2a1-62ad-4129-ae42-9438927dfdd3#5de1b130-422d-4b89-8b55-c7ec4cf07adc)

