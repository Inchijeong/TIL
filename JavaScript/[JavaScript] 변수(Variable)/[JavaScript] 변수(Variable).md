

# [JavaScript] 변수(Variable)



## 변수의 선언과 초기화

메모리에 데이터 공간을 할당하는 것을 **변수의 선언**이라고 합니다.

선언된 공간에 값을 넣는것을 **대입**이라고 합니다.



> 자바스크립스트는 느슨한 타입(loosely typed) 언어이며 동적(dynamic) 언어이기 때문에 변수의 타입을 미리 선언할 필요가 없습니다.



자바스크립스트에서는 다음과 같이 `var` 키워드[^1]를 사용하여 변수를 선언합니다.

[^1]: 키워드는 제어문의 시작과 끝, 특정한 조작 목적 등에 쓰입니다. [키워드와 예약어](https://blog.sonim1.com/118) 참조.

```javascript
var man; // 변수의 선언
var num = 123; // 변수의 선언과 초기화
```

**변수의 선언**은 데이터 공간을 `man` 이라는 변수명으로 사용하겠다는 것을 의미합니다.

`num` 은 이라는 공간에  `123` 이라는 값을 변수의 선언과 동시에 대입시키는 것을 **초기화**라고 합니다.



> 문장 끝에 ;(세미콜론)은 문장이 끝난다는 것을 컴퓨터에게 알려주는 것입니다.
>
> 선택사항이기 때문에 사용하는 건 개인적인 판단입니다.
>
> 자세히 알고싶은 분들은 [세미콜론을 써야 하나 말아야 하나](https://bakyeono.net/post/2018-01-19-javascript-use-semicolon-or-not.html) 를 읽어 보시는 것을 추천드립니다.



## 선언시 주의사항(표기법)

### 작명

개발은 혼자할 수도 있지만 실제로는 다른 사람과 함께 팀을 이뤄서 많이 합니다.

변수명을 다음과 같이 나만 알아볼 수 있는 변수를 사용하면 안되겠죠?

```javascript
var aaa2342;
var apple;
var Battlecruiser;
```

정답은 없습니다. 

하지만 개발자는 그 변수가 어떤 데이터를 담고 있는지 유추할 수 있도록 해야합니다.

```javascript
var arr = ['a', 'b'];
var arrLen = arr1.length;
var sum = function (a, b){
    return a+b;
}
```



### 표기법

변수명을 만들때 `man` 과 같이 한 단어라면 문제없습니다.

하지만 한 단어가 아닌 경우 어떻게 표기해야할까요?

자바스크립트는 변수명에 띄어쓰기를 허용하지 않습니다.



그래서 **자바스크립트**는 **Camel Case**를 사용합니다.



1. camelCase(낙타 표기법)
   * `objectOrientedProgramming` 
   * 첫 글자는 소문자
   * 단어와 단어 사이의 첫 단어를 대문자
2. snake_case(뱀 표기법)
   * `object_oriented_programming`
   * 모든 글자 소문자
   * 단어와 단어 사이를 `_`(언더스코어) 로 표기



위 두 표기법은 다른 언어에서도 자주 사용됩니다.



### 규칙

* `$`, `_`  외의 특수문자로 시작 할 수 없습니다.
* 숫자로 시작할 수 없습니다.
* 예약어를 사용할 수 없습니다.

*Javascript Coding Convention* 을 검색해보시면 더 많은 자료를 찾아볼수 있습니다.



## 참조 사이트

[생활코딩](https://opentutorials.org/course/1)

[zerocho](https://www.zerocho.com/)

[MDN](https://developer.mozilla.org/ko/docs/Web/JavaScript)

[ZETAWIKI](https://zetawiki.com/wiki/%EC%8A%A4%EB%84%A4%EC%9D%B4%ED%81%AC_%ED%91%9C%EA%B8%B0%EB%B2%95)