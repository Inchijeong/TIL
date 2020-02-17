# [JavaScript] 자료형(Data Type)



## 자료형이란

변수에 데이터가 저장될때 변수가 어떤 타입의 데이터를 저장할 수 있는지 표현한 것이 자료형입니다.

자바스크립트는 이 모든것을 통틀어서 `var` 키워드를 사용하지만 (`let` 과 `const` 는 지금 생각하지 않겠습니다)

어떤 자료의 형태가 있는지는 아는 것은 어느 언어를 공부하든 필수라고 생각됩니다.



## 자료형의 종류

자료형은 다음과 같이 7가지 형태가 있습니다.

- 기본 자료형 (Primitive)
  - **Boolean** - `true` 또는 `false` 중 하나를 값으로 가집니다.
  - **Null** - 어떤 값이 의도적으로 비어있음을 표현한 것입니다.
  - **Undefined** - 값을 할당하지 않은 상태를 표현한 것입니다.
  - **Number** - 숫자를 값으로 가집니다.
  - **String** - 문자를 값으로 가집니다.
  - **Symbol** (ECMAScript 6 에 추가됨)
- **Object**
  - 데이터를 다루는 데이터 구조
  - Array, Function 등 ..



변수에 저장할때 기본 자료형은 값 자체 가지고 있습니다.

하지만 참조형(Object)는 변수가 저장된 주소를 가지고 있습니다.

어떤 언어든 기본형과 참조형의 개념은 중요한 것 같습니다.



하나씩 살펴보겠습니다.



### Boolean

참인지 거짓인지를 표현하는 자료형입니다.

주로 조건문의 조건절과 판별식에 사용됩니다.



### Null

null 은 아무것도 없는 상태를 뜻합니다.



### Undefiend

undefiend는 정의되지 않은 상태를 뜻합니다.



#### null 과 undefined의 차이

null 과 undefined는 처음 어렵게 느껴질수 있겠지만

```javascript
var num;
console.log(num); // undefined
var num = 1;
num = null;
console.log(num); // null
```

위와 같이 초기화하지 않고 변수를 표시하면 undefined가 되고

null 을 대입한다는 것은 비어있는 상태를 null 이라는 리터럴을 넣어 표현한 것입니다.



**참조**

```javascript
typeof null          // "object" (not "null" for legacy reasons)
typeof undefined     // "undefined"
null === undefined   // false
null  == undefined   // true
null === null        // true
null == null         // true
!null                // true
isNaN(1 + null)      // false
isNaN(1 + undefined) // true
```



### Number

Java 에서는 byte, short, int, long, float, double 등 정수와 실수 그리고 크기로 다양한 숫자형 타입을 나눕니다.

하지만 JavaScript 는 숫자 타입은 그냥 number 입니다.

```javascript
var num1 = 1;
var pi = 3.14;
```



### String

문자 하나 또는 문자열을 나타내는 타입입니다.

문자열을 표시하는 방법은 다양합니다.

기본적으로 `'`, `"`  로 문자의 앞뒤를 묶어 표현합니다.

따옴표로 시작했으면 따옴표로 끝나고 큰따옴표로 시작했으면 큰따옴표로 끝나야합니다.

```javascript
var str1 = "hello";
var str2 = 'hello';
var str3 = "hello'; // Invalid or unexpected token

```



#### 이스케이프(Escape)

```javascript
var str4 = "coscha's blog";
var str5 = 'coscha\'s blog \n is good.';
```

`str4` 로도 표현이 가능하지만

`str5` 의 `\`를 문자 앞에 붙이면 특수문자를 표현할 수 있습니다.

이것을 **이스케이프(Escape)** 라고 합니다.

이 밖에도 `\n`, `\t` 등 다양한 사용법이 있습니다.



#### 문자열 여러줄

다음과 같이 여러줄을 표시할때 ` 를 사용할 수 있습니다.

```javascript
var str6 = 
    `Hello
     World
     Welcome`;
```



#### 숫자와 문자열 연산

문자열과 숫자를 더하면 문자열이 됩니다.

```javascript
var str1 = 'one'+2;
console.log(str1); // one2
var str2 = 1+2+'three';
console.log(str2); // 3three
```

연산은 왼쪽에서 오른쪽으로 진행되기 때문에 `str2` 는 `1+2` 먼전 연산되어 `3`이 되고

그 후 `3+'three'` 가 연산되어 위와 같은 결과가 나타납니다.



### Object

Array 도 Function 도 Object 객체입니다.

양이 많아 상세 정리는 본문에서 분리하였습니다.

각 타입은 예를 들어 다음과 같이 표현 할 수 있습니다.

```javascript
var obj = {
    num: 1
    sayHello: function(str){
        console.log(str);
    }
};
var arr = [1, 2, 3];
var sum = function (a, b){
    return a+b;
}
```



## 참조 사이트

[생활코딩](https://opentutorials.org/course/1)

[zerocho](https://www.zerocho.com/)

[MDN](https://developer.mozilla.org/ko/docs/Web/JavaScript)

