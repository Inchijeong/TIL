# [React] 개념 및 개발환경 구축



> 생활코딩의 [React] 를 학습하고 정리한 글입니다.
>
> 일부 이미지는 영상의 이미지를 캡처하였습니다.
>
> [생활코딩 React](https://opentutorials.org/module/4058)



HTML의 사용자 정의 태그(컴포넌트) 단위로 쪼개어 관리하면 다음과 같은 장점이 생긴다.

1. 가독성
2. 재사용성
3. 유지보수



## 리액트란?

- 프론트엔드 라이브러리
- 복잡한 UI를 캡슐화된 컴포넌트로 관리



## 설치

1.  Node.js 설치
2. npm 설치
3. react-create-app 설치



-g : global 옵션, 어디서든 설치한 프로그램을 사용할 수 있다.

@2.1.8 : 버전 명시

```shell
npm install -g create-react-app@2.1.8
```



설치 이후 디렉토리 생성

```shell
mkdir react-app
cd react-app
create-react-app .
```



*참조*

`npx` 는 일회용으로 해당 프로그램의 최신 버전을 설치 받아 실행하고 삭제한다.

```shell
npx create-react-app my-app
```



## 실행

```shell
npm run start
```



## 종료

Ctrl + c



## improt

`import` 바로 뒤에 오는것은 지금 파일에서 가져온 파일을 사용할 별칭.

`from` 바로 뒤에 오는것은 사용할 파일의 위치 및 이름.

```js
import App from './App';
```



## JavaScript 코딩하는 법

실제 보고있는 화면은 public 디렉토리에 있는 index.html 파일인데

recat 는 우리가 만든 컴포넌트들을 id가 `root` 인 태그 안에 들어가도록 해놨다.



_public/index.html_

```html
...
<div id="root"></div>
...
```



우리가 작업할 공간은 src 디렉토리이다.



_src/index.js_

```js
...
ReactDOM.render(<App />, document.getElementById('root'));
...
```

위 부분이 사용자 정의 컴포넌트인 `App`을 `root`에 코드이다.



_src/App.js_

```javascript
import React from 'react';
import logo from './logo.svg';
import './App.css';

function App() {
  return (
    <div className="App">
      hello react
    </div>
  );
}

export default App;
```

className 이 `App`인 태그 안의 코드를 지우고 위와같이 `hello react` 를 입력하면 바뀐 결과 값을 볼 수 있다.



## CSS 코딩하는 법

_src/index.css_

```css
body {
  background-color: powderblue;
}
```

위의 코드를 작성하고 실행 결과를 보면 배경화면이 바뀐것을 볼 수 있다.

이후 진행을 위해 index.css 와 App.css 파일의 내용을 지워준다.



## 배포하는 법



아래의 방법으로 실행해서 Network 탭을 열어준다.

그 후 Empty Cache And Hard Reload 를 해보면 대략 2MB의 resources를 받는다.

이는 React가 사용할 수 있는 기능들을 설치하기 때문이다.

```shell
npm run start
```



하지만 배포할시 이런 용량을 사용자에게 주어서는 안된다.

아래의 명령을 실행해 본다.

```shell
npm run build
```

build 디렉토리가 생성되고 각 파일들이 압축된다.



아래의 명령을 통해 일회성 서버를 열어본다.

```shell
npx serve -s build
```



그 후 위에서 했던것 처럼 Network 탭에서 용량을 확인해보면 대략 150KB 로 용량이 줄어든 것을 확인할 수 있다.

