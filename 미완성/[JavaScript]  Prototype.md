# [JavaScript] Prototype

**목차**

[TOC]



생성자 함수(Function) 란 객체를 생성하는 함수입니다.

일반 함수와 다르게 대문자로 시작합니다.

객체는  `new` 키워드를 통해서 만들수 있습니다.

```javascript
function User(){
    // this 는 함수 자기 자신을 가리킵니다.
 	this.level = 1;
    this.writable = true;
    this.write = function(){
        if(writable)
        console.log('write.')
    }
}

var kim = new User();
var lee = new User();
```









클래스를 사용하면 메모리 공간을 줄일수 있습니다.



자바스크립트에는 Prototype Link 와 Prototype Object 가 존재하고 이 둘을 묶어 Prototype라고 부릅니다.



객체는 다음과 같이 생성합니다.

```javascript
var obj = {};
// 위와 같습니다.
var obj = new Object();
```

따라서, 객체는 함수에 의해 정의됩니다.



함수가 정의될때 

