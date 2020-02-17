# [React] 컴포넌트 제작 그리고 Props



> 생활코딩의 [React] 를 학습하고 정리한 글입니다.
>
> 일부 이미지는 영상의 이미지를 캡처하였습니다.
>
> [생활코딩 React](https://opentutorials.org/module/4058)



## 컴포넌트화



_/pulbic/pure.html_

```html
<html>
    <body>
        <header>
            <h1>WEB</h1>
            world wide web!
        </header>        

        <nav>
            <ul>
                <li><a href="1.html">HTML</a></li>
                <li><a href="2.html">CSS</a></li>
                <li><a href="3.html">JavaScript</a></li>
            </ul>
        </nav>

        <article>
            <h2>HTML</h2>
            HTML is HyperText Markup Language.
        </article>
    </body>
</html> 
```

위 코드를 React를 사용하여 일부를 컴포넌트화 시켜보자.



_/src/App.js_

```react
import React, { Component } from 'react';
import './App.css';

class Subject extends Component {
  render(){
    return(
      <header>
          <h1>WEB</h1>
          world wide web!
      </header>
    );
  }
} // 1

class App extends Component {
  render() {
    return (
      <div className="App">
        <Subject></Subject> // 2
      </div>
    );
  }
}

export default App;
```



1 에서 만든 컴포넌트를 2 에서 사용하고 있다.

App.js와 같이 js안에 html을 사용하는 React는 유사 자바스크립트이다.(JSX)

React가 JavaScript로 자동으로 컨버팅 시켜주는 것이다.



_참고_

컴포넌트를 만들때는 하나의 최상위 태그만 존재해야 한다.

아래와 같은 경우 에러가 난다.

```react
class App extends Component {
  render() {
    return (
      <div className="App"></div>
      <div></div>
    );
  }
}
```



이제 나머지 태그도 컴포넌트화 시켜 완성시켜보자.



_/src/App.js_

```react
import React, { Component } from 'react';
import './App.css';

class Subject extends Component {
  render(){
    return(
      <header>
          <h1>WEB</h1>
          world wide web!
      </header>
    );
  }
}

class TOC extends Component {
  render(){
    return(
      <nav>
          <ul>
              <li><a href="1.html">HTML</a></li>
              <li><a href="2.html">CSS</a></li>
              <li><a href="3.html">JavaScript</a></li>
          </ul>
      </nav>
    );
  }
}

class Content extends Component {
  render(){
    return (
      <article>
          <h2>HTML</h2>
          HTML is HyperText Markup Language.
      </article>
    );
  }
}

class App extends Component {
  render() {
    return (
      <div className="App">
        <Subject></Subject>
        <TOC></TOC>
        <Content></Content>
      </div>
    );
  }
}

export default App;
```



## props



아래와 같이 컴포넌트로 만든 태그에 동적인 값을 주어 사용하고 싶다.

_/src/App.js_

```react
...
<Subject title="WEB" sub="world wide web!"></Subject>
...
```



그러면 `Subject`를 다음과 같이 바꿔 사용할 수 있다.

_/src/App.js_

```react
...
class Subject extends Component {
  render(){
    return(
      <header>
          <h1>{this.props.title}</h1>
          {this.props.sub}
      </header>
    );
  }
}
...
```



이로서 우리는 props를 사용하여 동적인 컴포넌트를 만들었다.

_/src/App.js_

```react
...
<Subject title="WEB" sub="world wide web!"></Subject>
<Subject title="React" sub="For UI"></Subject>
...
```



## Component 파일로 분리하기



src에 components 디렉토리를 생성한다. 그리고 그 아래 TOC.js파일을 생성.

_/src/components/TOC.js_

```react
import React, { Component } from 'react'; // 1

class TOC extends Component {
  render(){
    return(
      <nav>
          <ul>
              <li><a href="1.html">HTML</a></li>
              <li><a href="2.html">CSS</a></li>
              <li><a href="3.html">JavaScript</a></li>
          </ul>
      </nav>
    );
  }
}

export default TOC; // 2
```



1 에서 `import React` 는 React를 사용하기위해 기본적인 것이고

 `import { Component }`는 컴포넌트를 사용하기 위함이다.

2 는 이렇게 만든 TOC를 다른 곳에서 사용하기 위함이다.



이제 App.js 에 있는 `Class TOC` 를 지워주고 방금만든 TOC.js 를 `import` 시켜주자.

_/src/App.js_

```react
import React, { Component } from 'react';
import TOC from './components/TOC';
import './App.css';
...
```



마찬가지로 다른 컴포넌트도 파일로 쪼개주면 최종적으로 다음과 같이 짧은 코드가 완성된다.

/src/App.js

```react
import React, { Component } from 'react';
import Subject from './components/Subject';
import TOC from './components/TOC';
import Content from './components/Content';
import './App.css';

class App extends Component {
  render() {
    return (
      <div className="App">
        <Subject title="WEB" sub="world wide web!"></Subject>
        <Subject title="React" sub="For UI"></Subject>
        <TOC></TOC>
        <Content title="HTML" desc="HTML is HyperText Markup Language."></Content>
      </div>
    );
  }
}

export default App;
```



그리고 다음과 같이 컴포넌트들을 분리해서 관리할 수 있게 되었다.



![[React] 컴포넌트 제작 그리고 Props]([React] 컴포넌트 제작 그리고 Props.png)
