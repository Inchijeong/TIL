# Tistory + Typora 이용하여 마크다운 사용하기



**목차**

[TOC]



## ! 추가

2019년 3월 21일 기준

(#1 스킨사용시)

Typora로 작성된 글을 전체 복사하여

Tistory 글쓰기 누르고 붙여넣는 방법이 제일 좋은것 같습니다.





## markdown.css 다운로드 및 티스토리 업로드



1. 아래 링크로 들어가서 

   https://github.com/sindresorhus/github-markdown-css

   [github-markdown.css](https://github.com/sindresorhus/github-markdown-css/blob/gh-pages/github-markdown.css) 위 파일을 받아주도록 합시다.

   

   이름을 markdown.css 파일로 변경하였습니다.

   상단에 아래 코드를 추가해줍니다.

```css
@font-face {
    ...
}

/* 추가할 코드 시작 부분 */
.markdown-body {
  box-sizing: border-box;
  min-width: 100px;
  max-width: 980px;
  margin: 0 auto;
  padding: 15px;
}

@media (max-width: 767px) {
  .markdown-body {
    padding: 15px;
  }
}
/* 추가할 코드 끝 부분 */

.markdown-body .octicon {
	...
}
```

2. 블로그관리 홈에 들어갑니다.

3. 우측 사이드 메뉴에 꾸미기 > 스킨 편집을 선택합니다.



![스크린샷, 2019-03-21 09-51-41](스크린샷, 2019-03-21 09-51-41.png)

4. 우측 사이드 상단에 html 편집을 선택합니다.  ![스크린샷, 2019-03-21 09-54-25](스크린샷, 2019-03-21 09-54-25.png)

5. 파일 업로드 선택 > 추가 > markdown.css 업로드

6. HTML 탭 선택 > `</head>` 바로 위에

    `<link rel="stylesheet" href="./images/markdown.css">`

   를 추가합니다.

![스크린샷, 2019-03-21 10-10-02](스크린샷, 2019-03-21 10-10-02.png)

7. 저장하면 티스토리 준비는 끝납니다.



## Typora 내보내기 + markdown.css 적용



1. 상단 메뉴들 중 파일 선택 > 내보내기 > HTML (without styles)

   ![2](2.png)

2. 글쓰기에 들어가 글쓰기 박스 우측 상단에 HTML 체크박스를 클릭합니다.

3. 아까 저장했던 HTML 파일의 `<body></body>`  안의 부분을 복사합니다.

4. 아래와 같이 `<article class="markdown-body"></article>` 사이에

   3 에서 저장했던 코드를 붙여 넣습니다.

   ```css
   <article class="markdown-body">
   	/* 코드 붙여넣기할 위치 */
   </article>
   ```

5. 제목을 입력하고 발행을 해줍니다.

   

## Github Issues를 이용하여 Image 업로드



1. 개인적으로 블로그 이미지 URI를 관리할 Repository 생성하였습니다.

2. 상단 부분에 Issues 탭을 선택하고 블로그에 올리고 싶은 이미지를 

   드래그앤드랍으로 Write 부분에 집어 넣어줍니다.

   ![스크린샷, 2019-03-21 10-30-52](스크린샷, 2019-03-21 10-30-52.png)

3. 변환된 텍스트를 블로깅할 이미지 자리에 넣어서 사용하면 됩니다.



> 관리를 위하여 각 게시물의 제목을 넣어서 저장시켜줬습니다.
>
> 저장하지 않아도 이미지는 사용 가능합니다.



## 참조 사이트

[구월에작은섬](https://marlinbar.tistory.com/69 "구월에작은섬")

[Regyu.log](https://regyu.tistory.com/2 "Regyu.log")

