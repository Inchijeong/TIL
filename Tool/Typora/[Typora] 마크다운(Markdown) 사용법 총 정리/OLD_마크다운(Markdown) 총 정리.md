# 마크다운(Markdown) 총정리

마크다운(Markdown)에 대해 알아보겠습니다.

<br/>

## 마크다운(Markdown) 이란?

* 마크업 언어의 일종으로 일반 텍스트 문서의 양식을 편집하는 문법입니다.

* 텍스트를 HTML로 변환하는 언어입니다.

<br/>

## 마크다운(Markdown) 사용법

### 1. 문장 & 문단

- 문장 끝에 공백 두칸은 줄 바꿈 기능을 합니다.

  (문장 끝 띄어쓰기 2칸 ==  `<br>`)

  + 공백 없을 경우

    ```HTML
    <!-- Markdown -->
    Hello World(띄어쓰기 없음)
    Hi MD
    <!-- HTML -->
    <p>Hello World Hi MD</p>
    ```


---

**OUTPUT**

Hello World Hi md

---

+ 공백 있을 경우 (혹은 `<br>` 삽입)

  + *(참고) Typora의 경우 공백 2개 입력 후 Shift + Enter 누르기*
  
  ```html
  <!-- Markdown -->
  Hello World(공백)(공백)
  Hi MD
  <!-- HTML -->
  <p>Hello World<br>Hi MD</p>
  ```

---

**OUTPUT**

Hello World  
Hi MD

---

- 문단과 문단은 하나 이상의 빈 줄로 구분합니다.

  (한 줄 공백 => `<p></p>`)

  + 빈줄 없을 경우

    ```html
    <!-- Markdown -->
    Hello World
    Hi MD
    <!-- HTML -->
    <p>Hello World Hi MD</p>
    ```

---

**OUTPUT**

Hello World Hi MD

---

+ 빈줄 있을 경우

  ```html
<!-- Markdown -->
  Hello World
  
  Hi MD
  <!-- HTML -->
  <p>Hello World</p><p>Hi MD</p>
  ```

---

**OUTPUT**

Hello World
Hi MD

---

<br/>

### 2. 제목

* `#` 을 이용하는 방법 

  ```html
  <!-- Markdown -->
  # H1
  ## H2
  ### H3
  #### H4
  ##### H5
  ###### H6
  <!-- HTML -->
  <h1>H1</h1>
  <h2>H2</h2>
  <h3>H3</h3>
  <h4>H4</h4>
  <h5>H5</h5>
  <h6>H6</h6>
  ```

---

**OUTPUT**

# H1

## H2

### H3

#### H4

##### H5

###### H6

---

* `-` 나 `=` 를 이용하는 방법

  ```html
  <!-- Markdown -->
  H1
  =======
  H2
  -------
  <!-- HTML -->
  <h1>H1</h1>
  <h1>H2</h1>
  ```

---

**OUTPUT**

# H1

## H2



---

<br/>

### 3. 구분선(수평선)

* `---`,  `___`, `***`  를 이용하여 구분선을 넣을 수 있습니다.

  ```html
  <!-- Markdown -->
  하이픈
  ---
  언더스코어
  ___
  애스터리스크
  ***
  <!-- HTML -->
  <p>하이픈</p>
  <hr>
  <p>언더스코어</p>
  <hr>
  <p>애스터리스크</p>
  <hr>
  ```

---

**OUTPUT**

하이픈

---

언더스코어

___

애스터리스크

***



---

<br/>

### 4. 목록

- `*`,  `+`, `-` 를 사용하여 순서 없는 목록을 만듭니다.

  ```HTML
  <!-- Markdown -->
  * ORDER 1
    + ORDER 1-1
    + ORDER 1-2
    + ORDER 1-3
      - ORDER 1-3-1
  	- ORDER 1-3-2
  * ORDER 2
  <!-- HTML -->
  <ul>
      <li><p>ORDER 1</p></li>
      <ul>
          <li><p>ORDER 1-1</p></li>
          <li><p>ORDER 1-2</p></li>
          <li><p>ORDER 1-3</p></li>
          <ul>
              <li><p>ORDER 1-3-1</p></li>
              <li><p>ORDER 1-3-2</p></li>
          </ul>
      </ul>
      <li><p>ORDER 2</p></li>
  </ul>
  ```

---

**OUTPUT**

- ORDER 1
  - ORDER 1-1
  - ORDER 1-2
  - ORDER 1-3
    - ORDER 1-3-1
    - ORDER 1-3-2
- ORDER 2

---

- `1.` , `2.`, `3.`  을 이용하여 순서 있는 목록을 만듭니다.

- 순서 없는 목록과 섞어서 사용 가능합니다.

  ```html
  <!-- Markdown -->
  1. ORDER 1
  2. ORDER 2
  3. ORDER 3
    * ORDER 3-A
    * ORDER 3-B
  <!-- HTML -->
  <ol>
      <li><p>ORDER 1</p></li>
      <li><p>ORDER 2</p></li>
      <li><p>ORDER 3</p></li>
      <ul>
          <li><p>ORDER 3-A</p></li>
          <li><p>ORDER 3-B</p></li>
      </ul>
  </ol>
  ```

---

**OUTPUT**

1. ORDER 1
2. ORDER 2
3. ORDER 3
   * ORDER 3-A
   * ORDER 3-B

---

<br/>

### 5. 강조

* `*`, `_` 로 강조하고 싶은 부분을 감싸서 사용할 수 있습니다.

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
  <!-- HTML -->
  <p>Hello <em>World</em></p>
  <p>Hello <strong>World</strong></p>
  <p>Hello <strong><em>World</em></strong></p>
  
  <p>Hello <em>World</em></p>
  <p>Hello <strong>World</strong></p>
  <p>Hello <strong><em>World</em></strong></p>
  ```

---

**OUTPUT**

Hello *World* 
Hello **World** 
Hello ***World*** 



Hello _World_ 
Hello __World__
Hello ___World___   

---

<br/>

### 6. 인용

* `>`를 사용하여 인용구를 작성할 수 있습니다.

  ```html
  <!-- Markdown -->
  > 인용구 입니다.
  > # H1
  > * a
  > * b
  >> 이중 인용구
  <!-- Html -->
  <blockquote>
      <P>인용구 입니다.</P>
      <h1>H1</h1>
      <ul>
          <li>ORDER1</li>
          <li>ORDER2</li>
      </ul>
      <blockquote>이중인용구</blockquote>
  </blockquote>
  ```

---

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

---

<br/>

### 7. 링크 & 이미지

* 인라인 링크는 `[화면에 표시될 글자](URI)` 로 사용합니다.

  * `[화면에 표시될 글자](URI "툴팁")` 툴팁 자리에 텍스트를 넣으면 html title속성으로 들어갑니다.

  ```html
  <!-- Markdown -->
  [naver](https://www.naver.com)
  [naver2](https://www.naver.com "네이버")
  <!-- Html -->
  <a href="https://www.naver.com" target="_blank">naver</a>
  <a href="https://www.naver.com" target="_blank" title="네이버">naver</a>
  ```

  

---

**OUTPUT**

[naver](https://www.naver.com)
[naver2](https://www.naver.com "네이버")

---



* 참조 링크는 `[화면에 표시될 글자][1]`,  `[1]:URI "툴팁" `  로 사용합니다.

  ```html
  <!-- Markdown -->
  [daum][1]
  [1]:https://daum.net "다음"
  <!-- Html -->
  <a href="https://daum.com" target="_blank" title="다음">daum</a>
  ```

---

**OUTPUT**

[daum][1]



[1]: https://daum.net "다음"

---

* URI 링크는 `<주소>` 로 사용합니다.

  ```html
  <!-- Markdown -->
  <https://github.com>
  <!-- Html -->
  <a href="https://github.com" target="_blank">https://github.com</a>
  ```

---

**OUTPUT**

<https://github.com>

---

* 이미지의 경우 링크 앞에 `!` 붙여서 사용합니다.

  * 이미지도 마찬가지로 인라인 링크, 참조 링크, URI 링크 모두 사용 가능합니다.

  ```html
  <!-- Markdown -->
  ![puppy-1903313_640](https://user-images.githubusercontent.com/31085727/39238230-b2ebb084-48b8-11e8-9e06-0a1743b253e7.jpg "강아지")
  <!-- Html -->
  <img src="https://user-images.githubusercontent.com/31085727/39238230-b2ebb084-48b8-11e8-9e06-0a1743b253e7.jpg" alt="강아지"/>
  ```

---

**OUTPUT**

![puppy-1903313_640](https://user-images.githubusercontent.com/31085727/39238230-b2ebb084-48b8-11e8-9e06-0a1743b253e7.jpg "강아지")

---

<br/>

### 8.  이스케이프 & 코드 블록

* `\` 를 앞에 붙여 특수문자를 표시할 수 있습니다.(이스케이프)

  ```html
  <!-- Markdown -->
  \# H1
  \* ORDER1
  <!-- Html -->
  <p># H1</p>
  <p>* ORDER1</p>
  ```

---

**OUTPUT**

\# H1

\* ORDER1

---

* 인라인 코드 블럭

  * \`\`  로 글자를 감싸서 문장 내 코드를 삽입 할 수있습니다.

    ```html
    <!-- Markdown -->
    Javascript 에서 log 표시 방법은 `console.log()` 입니다.
    <!-- Html -->
    <p>Javascript 에서 log 표시 방법은 <code>console.log()</code> 입니다.</p>
    ```

---

**OUTPUT**

Javascript 에서 log 표시 방법은 `console.log()` 입니다.

---

* 코드 블럭

  * 문장 앞에 공백 4개 또는 탭 1개를 붙여 코드 블럭을 생성할 수 있습니다.(스페이스 코드블록)
  * 코드를 \``` 또는 \~~~ 로 감싸서 코드 블럭을 생성할 수 있습니다.(언어지정 코드블록)
    * 언어지정 코드 블록의 경우 하이라이트 기능을 끄고 싶다면 {.no-hightlight} 사용합니다.

  ```html
  <!-- Markdown -->
  ​```javascript
  console.log("Hello World");
  ​```
  
  ​```{.no-hightlight}
  console.log("Hello World");
  ​```
  <!-- Html -->
  <pre>
  	<code>
  		console.log("Hello World");
  	</code>
  </pre>
  ```

---

**OUTPUT**

```javascript
console.log("Hello World");
```

```{.no-hightlight}
console.log("Hello World");
```

---

<br/>

## 마크다운(Markdown) Extension

* 마크 다운 추가 기능.
* 몇몇 에디터에서 동작하지 않을 수 있습니다.



<br/>

### 9. 테이블

* `|`, `-` 를 적절히 활용하여 표를 만들 수 있습니다.

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
  <!-- Html -->
  <figure>
      <table>
          <thead>
              <tr>
                  <th>Title1</th>
                  <th>Title2</th>
              </tr>
          </thead>
          <tbody>
              <tr>
                  <td>content1</td>
                  <td>content2</td>
              </tr>
              <tr>
                  <td>content3</td>
                  <td>content4</td>
              </tr>
          </tbody>
      </table>
  </figure>
  
  <figure>
      <table>
          <thead>
              <tr>
                  <th style='text-align:left;' >Title1</th>
                  <th style='text-align:center;' >Title2</th>
                  <th style='text-align:right;' >Title3</th>
              </tr>
          </thead>
          <tbody>
              <tr>
                  <td style='text-align:left;' >content1</td>
                  <td style='text-align:center;' >content2</td>
                  <td style='text-align:right;' >content3</td>
              </tr>
          </tbody>
      </table>
  </figure>
  ```

---

**OUTPUT**

| Title1   | Title2   |
| -------- | -------- |
| content1 | content2 |
| content3 | content4 |



| Title1   |  Title2  |   Title3 |
| :------- | :------: | -------: |
| content1 | content2 | content3 |

---

<br/>

### 10. 각주

* 각주

  ```html
  <!-- Markdown -->
  Markdown[^1] 정리 거의 다 끝나가니 포기하지 마세요.
  [^1]: 마크업 언어의 일종으로 일반 텍스트 문서의 양식을 편집하는 문법입니다.
  ```

---

**OUTPUT**

Markdown[^1] 정리 거의 다 끝나가니 포기하지 마세요.



[^1]: 마크업 언어의 일종으로 일반 텍스트 문서의 양식을 편집하는 문법입니다.

---

<br/>

### 11. 목차

* `[TOC]` 를 입력하면 문서 내 헤딩 태그들을 이용하여 목차가 자동 생성됩니다.

  ```html
  <!-- Markdown -->
  [TOC]
  ```

---

**OUTPUT**

[TOC]

---



## 참조 사이트

* [컴공녀의 개발 블로그](https://simhyejin.github.io/2016/06/30/Markdown-syntax/#internal-link "컴공녀의 개발 블로그")  

* [DANIEL KU](http://danielku.com/posts/2014-02-13-markdown/ "DANIEL KU")  

* [위키독스](https://wikidocs.net/1678 "위키독스")

