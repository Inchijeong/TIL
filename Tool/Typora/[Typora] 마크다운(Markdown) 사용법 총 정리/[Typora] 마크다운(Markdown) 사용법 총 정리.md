# [Typora] 마크다운(Markdown) 사용법 총 정리

마크다운(Markdown)에 대해 알아보겠습니다.

<br/>

## A. 마크다운(Markdown) 이란?

* 마크업 언어의 일종으로 일반 텍스트 문서의 양식을 편집하는 문법입니다.

* 텍스트를 HTML로 변환하는 언어입니다.

<br/>

## B. 마크다운(Markdown) 사용법

### 1. 문장 & 문단

#### 1-1 문장

문장 끝에 공백 두칸은 줄 바꿈 기능을 합니다. (문장 끝 띄어쓰기 2칸 ==  `<br>`)

* (참고) Typora의 경우 공백 2개 입력 후 Shift + Enter 누르기

```HTML
<!-- Markdown -->
<!-- 공백이 없을 경우 -->
공백이(띄어쓰기 없음)
없을 경우
<!-- 공백 있을 경우 (혹은 `<br>` 삽입) -->
공백이(공백)(공백)
있을 경우
```

**OUTPUT**

공백이 없을 경우

공백이  
있을 경우

#### 1-2 문단

문단과 문단은 하나 이상의 빈 줄로 구분합니다. (한 줄 공백 => `<p></p>`)

```html
<!-- Markdown -->
<!-- 빈줄이 없을 경우 -->
빈줄이
없을 경우
<!-- 빈줄이 있을 경우 -->
빈줄이

있을 경우
```

**OUTPUT**

빈줄이

없을 경우

빈줄이

<br/>

있을 경우

<br/>

### 2. 제목

#### 2-1 `#`을 이용

```html
<!-- Markdown -->
# H1
## H2
### H3
#### H4
##### H5
###### H6
```

**OUTPUT**

# H1

## H2

### H3

#### H4

##### H5

###### H6

#### 2-2 `-` 또는 `=`를 이용

```html
<!-- Markdown -->
H1
=======
H2
-------
```

**OUTPUT**

# H1

## H2

<br/>

### 3. 구분선(수평선)

`---`,  `___`, `***`  를 이용하여 구분선을 넣을 수 있습니다.

```html
<!-- Markdown -->
하이픈
---
언더스코어
___
애스터리스크
***
```

**OUTPUT**

하이픈

---

언더스코어

___

애스터리스크

***

<br/>

### 4. 목록

#### 4-1 순서 없는 목록

`*`,  `+`, `-` 를 사용하여 순서 없는 목록을 만듭니다.

```HTML
<!-- Markdown -->
* ORDER 1
  + ORDER 1-1
  + ORDER 1-2
  + ORDER 1-3
    - ORDER 1-3-1
	- ORDER 1-3-2
* ORDER 2
```

**OUTPUT**

- ORDER 1
  - ORDER 1-1
  - ORDER 1-2
  - ORDER 1-3
    - ORDER 1-3-1
    - ORDER 1-3-2
- ORDER 2

#### 4-2 순서 있는 목록

`1.` , `2.`, `3.`  을 이용하여 순서 있는 목록을 만듭니다.

순서 없는 목록과 섞어서 사용 가능합니다.

```html
<!-- Markdown -->
1. ORDER 1
2. ORDER 2
3. ORDER 3
  * ORDER 3-A
  * ORDER 3-B
```

**OUTPUT**

1. ORDER 1
2. ORDER 2
3. ORDER 3
   * ORDER 3-A
   * ORDER 3-B

<br/>

### 5. 강조

`*`, `_` 로 강조하고 싶은 부분을 감싸서 사용할 수 있습니다.

* 1개 사용 => 이탤릭체
* 2개 사용 => 볼드체
* 3개 사용 => 이탤릭체 + 볼드체

```HTML
<!-- Markdown -->
Hello *World*  
Hello **World**  
Hello ***World***  

Hello _World_  
Hello __World__  
Hello ___World___
```

**OUTPUT**

Hello *World* 
Hello **World** 
Hello ***World*** 



Hello _World_ 
Hello __World__
Hello ___World___   

<br/>

### 6. 인용

`>`를 사용하여 인용구를 작성할 수 있습니다.

```html
<!-- Markdown -->
> 인용구 입니다.
> # H1
> * a
> * b
>> 이중 인용구
```

**OUTPUT**

> 입용구입니다.
>
> # H1
>
> * a
>
> * b
>
>   >이중 인용구

<br/>

### 7. 링크 & 이미지

#### 7-1 인라인 링크

`[화면에 표시될 글자](URI)` 로 사용합니다.

`[화면에 표시될 글자](URI "툴팁")` 툴팁 자리에 텍스트를 넣으면 html title속성으로 들어갑니다.

```html
<!-- Markdown -->
[naver](https://www.naver.com)
[naver2](https://www.naver.com "네이버")
```

**OUTPUT**

[naver](https://www.naver.com)
[naver2](https://www.naver.com "네이버")

#### 7-2 참조 링크

`[화면에 표시될 글자][1]`,  `[1]:URI "툴팁" `  로 사용합니다.

```html
<!-- Markdown -->
[daum][1]
[1]:https://daum.net "다음"
```

**OUTPUT**

[daum][1]

[1]: https://daum.net "다음"

#### 7-3 URI 링크

`<주소>` 로 사용합니다.

```html
<!-- Markdown -->
<https://github.com>
```

**OUTPUT**

<https://github.com>

#### 7-4 이미지 링크

링크 앞에 `!` 붙여서 사용합니다.

> 이미지도 마찬가지로 인라인 링크, 참조 링크, URI 링크 모두 사용 가능합니다.

```html
<!-- Markdown -->
![puppy-1903313_640](https://user-images.githubusercontent.com/31085727/39238230-b2ebb084-48b8-11e8-9e06-0a1743b253e7.jpg "강아지")
```

**OUTPUT**

![puppy-1903313_640](https://user-images.githubusercontent.com/31085727/39238230-b2ebb084-48b8-11e8-9e06-0a1743b253e7.jpg "강아지")

<br/>

### 8. 이스케이프 & 코드 블록

#### 8-1 이스케이프

`\`를 앞에 붙여 특수문자를 표시할 수 있습니다.

```html
<!-- Markdown -->
\# H1
\* ORDER1
```

**OUTPUT**

\# H1

\* ORDER1

#### 8-2 인라인 코드 블럭

\`\`  로 글자를 감싸서 문장 내 코드를 삽입 할 수있습니다.

```html
<!-- Markdown -->
Javascript 에서 log 표시 방법은 `console.log()` 입니다.
```

**OUTPUT**

Javascript 에서 log 표시 방법은 `console.log()` 입니다.

#### 8-3 코드 블럭

문장 앞에 공백 4개 또는 탭 1개를 붙여 코드 블럭을 생성할 수 있습니다. (스페이스 코드블록)

코드를 \``` 또는 \~~~ 로 감싸서 코드 블럭을 생성할 수 있습니다. (언어지정 코드블록)

* 언어지정 코드 블록의 경우 하이라이트 기능을 끄고 싶다면 {.no-hightlight} 사용합니다.

```html
<!-- Markdown -->
​```javascript
console.log("Hello World");
​```

​```{.no-hightlight}
console.log("Hello World");
​```
```

**OUTPUT**

```javascript
console.log("Hello World");
```

```{.no-hightlight}
console.log("Hello World");
```

<br/>

<br/>

## C. 마크다운(Markdown) Extension

* 마크 다운 추가 기능.
* 몇몇 에디터에서 동작하지 않을 수 있습니다.

<br/>

### 1. 테이블

`|`, `-` 를 적절히 활용하여 표를 만들 수 있습니다.

* `:` 를 이용하여 정렬할 수 있습니다.(`:` 가 글자 위치)

```html
<!-- Markdown -->
Title1|Title2
-|-
content1|content2
content3|content4

Title1|Title2|Title3
:-|:-:|-:
content1|content2|content3
```

**OUTPUT**

| Title1   | Title2   |
| -------- | -------- |
| content1 | content2 |
| content3 | content4 |

<br/>

| Title1   |  Title2  |   Title3 |
| :------- | :------: | -------: |
| content1 | content2 | content3 |

<br/>

### 2. 각주

`word[^1]`와 `[^1]:`를 통해 구현합니다.

```html
<!-- Markdown -->
Markdown[^1] 정리 거의 다 끝나가니 포기하지 마세요.
[^1]: 마크업 언어의 일종으로 일반 텍스트 문서의 양식을 편집하는 문법입니다.
```

**OUTPUT**

Markdown[^1] 정리 거의 다 끝나가니 포기하지 마세요.

[^1]: 마크업 언어의 일종으로 일반 텍스트 문서의 양식을 편집하는 문법입니다.

<br/>

### 3. 목차

`[TOC]` 를 입력하면 문서 내 헤딩 태그들을 이용하여 목차가 자동 생성됩니다.

```html
<!-- Markdown -->
[TOC]
```

**OUTPUT**

[TOC]

<br/>

## 링크

* [컴공녀의 개발 블로그](https://simhyejin.github.io/2016/06/30/Markdown-syntax/#internal-link "컴공녀의 개발 블로그")  

* [DANIEL KU](http://danielku.com/posts/2014-02-13-markdown/ "DANIEL KU") 

* [위키독스](https://wikidocs.net/1678 "위키독스")

