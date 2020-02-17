# [JavaScript] 연산자(Operator)



## 연산자란?

수학에서 두 수를 가지고 더하고 빼듯이 프로그래밍에서도 

연산자는 어떠한 데이터를 가지고 새로운 결과를 도출해냅니다.

연산자의 대상이 되는 데이터를 **피연산자** 라고 합니다.

산술연산 말고도 다양한 연산자가 있으며, 때로는 피연산자를 문자로 사용할 수도 있습니다.



## 연산자의 종류

[MDN 표현과 연산자](https://developer.mozilla.org/ko/docs/Web/JavaScript/Guide/Expressions_and_Operators) 에 있는 내용을 요약한 것입니다.

보다 상세한 설명은 해당 사이트를 참조하세요.

아래 모든 내용은 MDN 에서 가져왔음을 밝힙니다.



- 대입 연산자
- 비교 연산자
- 산술 연산자
- 비트단위 연산자
- 논리 연산자
- 문자열 연산자
- 조건 (삼항) 연산자
- 콤마 연산자
- 단항 연산자
- 관계 연산자



### 1. 대입 연산자

`=` 를 사용하여 오른쪽 피연산자의 값을 왼쪽 피연산자에 대입합니다.

`x = y` 는 `y`의 값을 `x` 에 할당한다는 뜻입니다.

다른 연산을 하고 대입하는 복합 대입 연산자도 있습니다.

| 이름                              | 복합 대입 연산자 | 뜻            |
| --------------------------------- | ---------------- | ------------- |
| 대입 연산                         | `x = y`          | `x = y`       |
| 덧셈 대입                         | `x += y`         | `x = x + y`   |
| 뺄셈 대입                         | `x -= y`         | `x = x - y`   |
| 곱셈 대입                         | `x *= y`         | `x = x * y`   |
| 나눗셈 대입                       | `x /= y`         | `x = x / y`   |
| 나머지 연산 대입                  | `x %= y`         | `x = x % y`   |
| 왼쪽 이동 연산 대입               | `x <<= y`        | `x = x << y`  |
| 오른쪽 이동 연산 대입             | `x >>= y`        | `x = x >> y`  |
| 부호 없는 오른쪽 이동 연산 대입   | `x >>>= y`       | `x = x >>> y` |
| 비트 단위 논리곱 연산 대입        | `x &= y`         | `x = x & y`   |
| 비트 단위 배타적 논리합 연산 대입 | `x ^= y`         | `x = x ^ y`   |
| 비트 단위 논리합 연산 대입        | `x |= y`         | `x = x | y`   |



**구조 분해 할당(destructuring assignment)**

복학 대입 연산 에서, *구조 해제 대입 문법* 은 배열의 구조나 객체를 반영하여, 배열이나 객체에서 데이터를 추출할 수 있게 해주는 자바스크립트 표현입니다.

```javascript
// 1
var foo = ["one", "two", "three"];

// without destructuring
var one   = foo[0];
var two   = foo[1];
var three = foo[2];

// with destructuring
var [one, two, three] = foo;

// 2
var a, b, rest;
[a, b] = [10, 20];

console.log(a);
// expected output: 10

console.log(b);
// expected output: 20

[a, b, ...rest] = [10, 20, 30, 40, 50];

console.log(rest);
// expected output: [30,40,50]
```



### 2. 비교 연산자

피연산자들을 비교하고 비교에 따라 논리 값을 반환합니다.

`==` 나 `!=` 는 타입을 적절하게 변환시켜 비교하지만 `===` 나 `!==` 는 변환시키지 않고 엄격하게 비교합니다.

| 연산자                  | 설명                                                         | 참을 반환하는 예제                 |
| ----------------------- | ------------------------------------------------------------ | ---------------------------------- |
| 같은(`==`)              | 피연산자들이 같으면 참을 반환합니다.                         | `3 == var1``"3" == var1``3 == '3'` |
| 다른(`!=`)              | 피연산자들이 다르면 참을 반환합니다.                         | `var1 != 4var2 != "3"`             |
| 엄격히 같은(`===`)      | 피연산자들이 같고 피연산자들의 같은 형태인 경우 참을 반환합니다. [`Object.is`](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Object/is) 와 [자바스크립트에서의 같음](https://developer.mozilla.org/ko/docs/Web/JavaScript/Equality_comparisons_and_sameness)을 참고하세요. | `3 === var1`                       |
| 엄격히 다른(`!==`)      | 피연산자들이 다르거나 형태가 다른 경우 참을 반환합니다.      | `var1 !== "3"3 !== '3'`            |
| ~보다 큰(`>`)           | 좌변의 피연산자 보다 우변의 피연산자가 크면 참을 반환합니다. | `var2 > var1"12" > 2`              |
| ~보다 크거나 같음(`>=`) | 좌변의 피연산자 보다 우변의 피연산자가 크거나 같으면 참을 반환합니다. | `var2 >= var1var1 >= 3`            |
| ~보다 작음(`<`)         | 좌변의 피연산자 보다 우변의 피연산자가 작으면 참을 반환합니다. | `var1 < var2"2" < 12`              |
| ~보다 작거나 같음(`<=`) | 좌변의 피연산자 보다 우변의 피연산자가 작거나 같으면 참을 반환합니다. | `var1 <= var2var2 <= 5`            |



### 3. 산술 연산자

숫자값(리터럴 또는 변수)을 피연산자로 갖고, 하나의 숫자 값을 반환합니다. 

자바스크립트의 산술 연산은 부동 소수점 값을 연산하는 것처럼 동작합니다.

0으로 나누는 것은 Infinity 를 발생시킵니다.

| 연산자                | 설명                                                         | 예제                                                         |
| --------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 나머지 연산자(`%`)    | 이항 연산자입니다. 두 피연산자를 나눈후 나머지를 반환합니다. | 12 % 5 returns 2.                                            |
| 증가 연산자(`++`)     | 단항 연산자입니다. 피연산자에 1을 더합니다. 만약 연산자를 피연산자 앞(`++x`)에 사용하면, 피연산자에 1을 더한 값을 반환합니다.; 만약 연산자를 피연산자 뒤(`x++`)에 사용하면, 피연산자에 1을 더하기 전 값을 반환합니다. | If `x` is 3, then `++x` sets `x` to 4 and returns 4, whereas `x++` returns 3 and, only then, sets `x` to 4. |
| 감소 연산자(`--`)     | 단항 연산자입니다. 피연산자로 부터 1을 뺍니다. 반환값은 증가 연산자와 유사합니다. | If `x` is 3, then `--x` sets `x` to 2 and returns 2, whereas `x--` returns 3 and, only then, sets `x` to 2. |
| 단항 부정 연산자(`-`) | 단항 연산자 입니다. 피연산자의 반대값(부호 바뀐값)을 반환합니다. | If `x` is 3, then `-x` returns -3.                           |
| 숫자화 연산자(`+`)    | 단항연산자 입니다. 피연산자가 숫자값이 아니라면 피연산자를 숫자로 변환하기를 시도합니다. | `+"3"` returns `3`. `+true` returns `1.`                     |



### 4. 비트단위 연산자

피연산자를 32비트의 집합으로 취급합니다.

비트단위 연산자는 자주 사용하지 않아 간략하게 테이블만 삽입했습니다.

| 연산자                  | 사용법    | 설명                                                         |
| ----------------------- | --------- | ------------------------------------------------------------ |
| 비트단위 논리곱         | `a & b`   | 두 피연산자의 각 자리 비트의 값이 둘다 1일 경우 해당하는 자리에 1을 반환합니다. |
| 비트단위 논리합         | `a | b`   | 두 피연산자의 각 자리 비트의 값이 둘다 0일 경우 해당하는 자리에 0을 반환합니다. |
| 비트단위 배타적 논리합  | `a ^ b`   | 두 피연산자의 각 자리 비트의 값이 같을 경우 해당하는 자리에 0을 반환합니다. [두 피연산자의 각 자리 비트의 값이 다를 경우 해당하는 자리에 1을 반환합니다.] |
| 비트단위 부정           | `~ a`     | 피연산자의 각 자리의 비트를 뒤집습니다.                      |
| 왼쪽 시프트             | `a << b`  | 오른쪽에서 0들을 이동시키면서, a의 이진수의 각 비트를 b비트 만큼 왼쪽으로 이동시킨 값을 반환합니다. |
| 부호 전파 오른쪽 시프트 | `a >> b`  | 사라지는 비트를 버리면서, a의 이진수의 각 비트를 b비트만큼 이동시킨값을 반환합니다. |
| 부호 없는 오른쪽 시프트 | `a >>> b` | 사라지는 비트를 버리고 왼쪽에서 0을 이동시키면서, a의 이진수의 각 비트를 b비트 만큼 이동시킨 값을 반환합니다. |



### 5. 논리 연산자

논리 연산자는 보통 부울 값과 사용됩니다.

부울 값들과 사용될때, 연산자는 부울값을 반환합니다.

그러나 `&&` 와 `||` 연산자는 실제로 명시된 피연사들 중 하나를 반환합니다.

| 연산자         | 사용법           | 설명                                                         |
| -------------- | ---------------- | ------------------------------------------------------------ |
| 논리 곱(`&&`)  | `expr1 && expr2` | (논리 곱) `expr1을 false로 변환할 수 있으면,expr1을 반환합니다 `; 불가능한 경우, `expr2을 반환합니다`. 이와 같이, 부울 값과 이용될때, `두 피연산자가 true이면,&&는` `true를 반환합니다`; 이 외의 경우, `false를 반환합니다`. |
| 논리 합(`||`)  | `expr1 || expr2` | (논리 합)` expr1`을` true로 변환 할 수 있으면,expr1을 반환합니다 `; 불가능한 경우, `expr2을 반환합니다`. 이와 같이, 부울 값과 이용될때, `||` 는 두 피연산자중 하나만 `true이면, true 를 반환합니다`; 만약 둘다 false인 경우,  `false을 반환합니다`. |
| 논리 부정(`!`) | `!expr`          | (논리 부정) 만약 피연산자가  `true로 변환될 수 있으면false을 반환합니다`; 불가능한 경우,`true`를 반환합니다. |



**false 인 값**

* `null`
* `NaN`
* `0`
* 빈 문자열(`""`,` ''`, ``)

- undefined



**단축 계산**

논리 연산자가 왼쪽에서 오른쪽으로 평가될때, 논리연산자는 다음의 규칙을 따라서 **단축 계산**으로 검사됩니다.

- `false && anything` 는 false 로 단축 계산 됩니다.
- `true || anything` 는 true 로 단춘 계산 됩니다.



### 6. 문자열 연산자

문자열 값으로 사용될 수 있는 비교 연산자에 덧붙여서 사용합니다.

연결 연산자 `+` 는 두 문자열 값을 연결하고, 두 문자열이 합쳐진 새로운 문자열을 반환합니다.

```javascript
console.log("hello " + "world") // hello world
```



또한, 복합 대입 연사자 `+=` 는 문자열을 연결하는데 사용할 수 있습니다.

```javascript
var mystring = "alpha";
mystring += "bet";
console.log(mystring) // alphabet
```



### 7. 조건 (삼항) 연산자

```javascript
(조건) ? a : b
```

만약 `조건`이 참 이라면, `a` 를 그렇지 않은 경우 `b` 를 값으로 갖습니다.



### 8. 콤마 연산자

두 피연산자를 평가하고 마지막 피연산자의 값을 반환합니다.

```javascript
function fn() { 
    if (x) {
        foo();
        return bar();
    } else {
        return 1;
    } 
}
// 콤마 연산자를 사용하면 다음과 같이 표현 할수 있습니다.
function fn() {
    return x ? (foo(), bar())
    	: 1;
}

출처: https://mygumi.tistory.com/50 [마이구미의 HelloWorld]
```



다음 사이트에서 보다 상세한 설명을 찾아 볼 수 있습니다.

 <https://mygumi.tistory.com/50> 



### 9. 단항 연산자



#### delete

`delete` 연산자는 객체, 객체의 속성, 배열의 특정한 위치에 있는 객체를 삭제할 수 있습니다.

연산이 수행 가능할때 `true` 불가능하면 `false` 를 반환합니다.

동작이 성공했다면 속성이나 원소를 `undefined` 로 설정합니다.

```javascript
x = 42;
var y = 43;
myobj = new Number();
myobj.h = 4;    // create property h
delete x;       // returns true (can delete if declared implicitly)
delete y;       // returns false (cannot delete if declared with var)
delete Math.PI; // returns false (cannot delete predefined properties)
delete myobj.h; // returns true (can delete user-defined properties)
delete myobj;   // returns true (can delete if declared implicitly)
```



#### typeof

피연산자의 타입을 나타내는 문자열을 반환합니다. 

```javascript
typeof 피연산자
```

반환값은 다음 중 하나가 됩니다.

- boolean
- string
- number
- function
- object
- undefined



#### void

`void` 연산자는 값을 반환하지 않고 평가되도록 명시합니다.

```javascript
void (식)
```



`void(0)` 은 하이퍼링크에 명시하여 사용 할 수 있습니다.

사용자가 클릭했을때 자바스크립트에 영향을 주지 않도록 하기 위해 다음과 같이 사용합니다.

```html
<a href="javascript:void(0)">Click here to do nothing</a>
```



### 10. 관계 연산자



#### in

`in` 연산자는 객체의 특정한 속성이 있는 경우 `true` 를 반환합니다.

```javascript
propNameOrNumber in objectName
```

objectName는 객체의 이름 입니다.

propNameOrNumber 는 속성의 이름을 나타내는 문자열 또는 배열의 인덱스 입니다.

```javascript
// Arrays
var trees = ["redwood", "bay", "cedar", "oak", "maple"];
0 in trees;        // returns true
3 in trees;        // returns true
6 in trees;        // returns false
"bay" in trees;    // returns false (you must specify the index number,
                   // not the value at that index)
"length" in trees; // returns true (length is an Array property)

// built-in objects
"PI" in Math;          // returns true
var myString = new String("coral");
"length" in myString;  // returns true

// Custom objects
var mycar = { make: "Honda", model: "Accord", year: 1998 };
"make" in mycar;  // returns true
"model" in mycar; // returns true
```



#### instanceof

`instanceof` 연산자는 명시된 객체가 명시된 객체형인 경우 `true`를 반환합니다.

```javascript
objectName instanceof objectType
```

다음 과 같이 theDay 가 Date 객체인지 확인 할 수 있습니다.

```javascript
var theDay = new Date(1995, 12, 17);
if (theDay instanceof Date) {
  // statements to execute
}
```



---

\+ 추가

---



### 11. 그룹 연산자

그룹연산자 `()` 는 표현식 평가의 우선순위를 조절합니다. 

```javascript
var a = 1;
var b = 2;
var c = 3;

// default precedence
a + b * c     // 7
// evaluated by default like this
a + (b * c)   // 7

// now overriding precedence 
// addition before multiplication   
(a + b) * c   // 9

// which is equivalent to
a * c + b * c // 9
```



### 12. 확산 연산자

확산연산자 `...` 는 다중인수(함수호출)또는 다중요소(문자배열)들이 예상되는 곳에서

확장될 수 있는 표현을 하게합니다.

```javascript
// 1
var parts = ['shoulder', 'knees'];
var lyrics = ['head', ...parts, 'and', 'toes'];
// 2
function f(x, y, z) { }
var args = [0, 1, 2];
f(...args);
```





## 연산자 우선 순위

| Operator type                 | Individual operators                     |
| ----------------------------- | ---------------------------------------- |
| 맴버 연산자                   | `. []`                                   |
| 객체 호출/생성 연산자         | `() new`                                 |
| 부정/증가 연산자              | `! ~ - + ++ -- typeof void delete`       |
| 곱셈/나눗셈 연산자            | `* / %`                                  |
| 덧셈/뺄셈 연산자              | `+ -`                                    |
| 비트단위 시프트 연산자        | `<< >> >>>`                              |
| 관계 연산자                   | `< <= > >= in instanceof`                |
| 같음 비교 연산자              | `== != === !==`                          |
| 비트 단위 논리곱 연산자       | `&`                                      |
| 비트단위 배타적 논리합 연산자 | `^`                                      |
| 비트단위 논리합 연산자        | `|`                                      |
| 논리 곱 연산자                | `&&`                                     |
| 논리 합 연산자                | `||`                                     |
| 조건 연산자                   | `?:`                                     |
| 대입 연산자                   | `= += -= *= /= %= <<= >>= >>>= &= ^= |=` |
| 콤마 연산자                   | `,`                                      |



## 참조 사이트

[MDN](https://developer.mozilla.org/ko/docs/Web/JavaScript)

<https://ccollect.tistory.com/42>

<https://mygumi.tistory.com/50>

