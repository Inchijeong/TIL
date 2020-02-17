# [HTML] 개념 및 총정리



**목차**

[TOC]



## HTML 이란

*HyperText Markup Language* 의 약자로 웹 브라우저 위에서 동작하며, 웹 페이지의 구조를 표현하는 언어입니다.



## 요소(Elements)란

HTML 은 **요소(Elements)** 혹은 태그(tag)라 불리는 것으로 이루어져 있습니다.

`<a href="https//www.naver.com"></a>` 와 같이 요소는 여는 요소와 닫는 요소로 구성됩니다.

`<img src=""/>` 와 같이 닫는 요소가 없는 요소도 있습니다.

* 끝에 붙는 `/`는 선택사항입니다.
* 닫는 요소가 없는 요소를 빈 요소라고 합니다.

또한, href 와 같이 요소의 추가적인 정보를 넣을때 사용하는 것을 **속성(attribute)** 이라고 합니다. 



## HTML 기본 구조

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
</head>
<body>
</body>
</html>
```

위 예제처럼 기본적으로 `<html>`  안에 `<head>` 와 `<body>` 가 존재합니다.



### DTD(Doctype)

제일 상단에 있는 `<!DOCTYPE html>` 는 *Document Type Definition* 로 문서의 형식을 지정합니다.

HTML 에도 다양한 표준이 존재하는데 이를 웹 브라우저에게 인식시키기 위해 사용하고 있습니다.

`<!DOCTYPE html>` 는 HTML5 를 가리킵니다.



### \<head\>

`<head>` 에는 문서에 대한 정보를 나타내는 부분이 되며,

 아래 요소들 외에도 `style` 나 `script` 와 같은 요소들이 위치할 수 있습니다.



* `<meta>` 는 문서에 대한 정보를 저장하고 있습니다.

* `<title>` 은 제목 표시줄에 표시될 제목이 들어갑니다.



### \<body\>

`<body>` 에는 웹 브라우저에서 사용자가 보는 실제로 보는 내용이 들어갑니다.



* `<h1> ~ <h6>` 는 제목을 사용할 때 쓰는 요소로 `<h1>` 이 가장 큰 글씨고 숫자가 커질 수록 부제가 됩니다.
* `<p>` 는 단락을 나눌 때 사용하는 요소입니다.
* `<a>` 는 링크를 이동시킬 때 사용하는 요소입니다.
* `<img>` 는 이미지를 삽입할 때 사용하는 요소입니다.
* `<button>` 은 버튼을 표시할 때 사용하는 요소입니다.
* `<ul>`  순서 없는 리스트, `<ol>` 은 순서 있는 리스트를 표현하며,  `<li>` 를 넣어 각각 아이템이 됩니다.
* `<br>` 은 줄 바꿈을 해주는 요소입니다.
* `<table>` 은 표를 삽입할 때 사용하며, 구성으로 `<thead>`, `<tbody>`, `<tfoot>` 으로 첫줄, 중간 여러줄, 마지막 줄을 사용합니다. 그리고 가로 한 줄은 `<tr>` , 한 칸은 `<td>` 로 표시하나 제목 칸은 `<th>` 로 표시합니다.



그 외에도 다양한 요소들이 존재합니다.

이는 필요에 따라 하나씩 찾아보며 사용해보는게 중요할것 같습니다.



## 참조사이트

[생활코딩](https://opentutorials.org/course/1)

[zerocho](https://www.zerocho.com/)

[w3schools](https://www.w3schools.com/)

