# [React] Create



> 생활코딩의 [React] 를 학습하고 정리한 글입니다.
>
> 일부 이미지는 영상의 이미지를 캡처하였습니다.
>
> [생활코딩 React](https://opentutorials.org/module/4058)



우선 이전에 만들었던 메뉴를 클릭했을때 나오는 설명을 Read 기능이라 생각하자.

그 밖에 CRUD 모두를 사용할 수 있게 메뉴를 추가하자.



_step1_



_/src/component/Control.js_

```react
import React, { Component } from 'react';

class Control extends Component {
  render(){
    console.log('Subject render');
    return(
      <ul>
        <li><a href="/create">create</a></li>
        <li><a href="/update">update</a></li>
        <li><input type="button" value="delete"></input></li>
      </ul>
    );
  }
}

export default Control;
```



App.js에 만든 Control.js 를 import 시켜야한다.



_/src/App.js_

```react
import React, { Component } from 'react';
import Subject from './components/Subject';
import TOC from './components/TOC';
import Content from './components/Content';
import Control from './components/Control';
import './App.css';

class App extends Component {
  constructor(props){
    super(props);
    this.state = {
      mode:'read', // 1
      selected_content_id:2,
      subject:{title:'WEB', sub:'World wide web!'},
      welcome:{title:'Welcome', desc:'Hello, React!'},
      contents:[
        {id:1, title:'HTML', desc:'HTML is for information'},
        {id:2, title:'CSS', desc:'CSS is for design'},
        {id:3, title:'JavaScript', desc:'JavaScript is for interactive'},
      ]
    }
  }
  render() {
	...
    return (
        <Control onChangeMode={function(_mode){
          this.setState({
            mode:_mode
          });
        }.bind(this)}></Control>  // 2
        <Content title={_title} desc={_desc}></Content>
      </div>
    );
  }
}

export default App;

```



컨트롤러를 눌렀을때 아래의 폼이 바뀌도록 이벤트 핸들러를 만든다.



_참고_

이벤트가 일어났을때 실행되는 함수를 핸들러라고도 한다.



_/src/component/Control.js_

```react
import React, { Component } from 'react';

class Control extends Component {
  render(){
    console.log('Subject render');
    return(
      <ul>
        <li><a href="/create" onClick={function(e){
          e.preventDefault();
          this.props.onChangeMode('create');
        }.bind(this)}>create</a></li>
        <li><a href="/update" onClick={function(e){
          e.preventDefault();
          this.props.onChangeMode('update');
        }.bind(this)}>update</a></li>
        <li><input onClick={function(e){
          e.preventDefault();
          this.props.onChangeMode('delete');
        }.bind(this)} type="button" value="delete"></input></li>
      </ul>
    );
  }
}

export default Control;
```



이제 create, update, delete 를 순서대로 눌러보면 mode 값이 변경되는 것을 확인할 수 있다.



![[React] Create]([React] Create.png)



_step2_



mode 에 따라 `Content` 가 각각의 기능을 담당하는 `Content` 로 바꿔보자.

우선 이전에 사용했던 Content.js 를 ReadContent.js 로 변경하자.



_/src/component/ReadContent.js_

```react
import React, { Component } from 'react';

class ReadContent extends Component {
  render(){
    console.log('Content render');
    return (
        <article>
            <h2>{this.props.title}</h2>
            {this.props.desc}
        </article>
    );
  }
}

export default ReadContent;
```



마찬가지로 CreateContent.js 생성해 준다.



_/src/component/CreateContent.js_

```react
import React, { Component } from 'react';

class CreateContent extends Component {
  render(){
    console.log('Content render');
    return (
        <article>
            <h2>Create</h2>
            <form>
              
            </form>
        </article>
    );
  }
}

export default CreateContent;
```



_/src/App.js_

```react
...
import ReadContent from './components/ReadContent';
import CreateContent from './components/CreateContent';
...
        <ReadContent title={_title} desc={_desc}></ReadContent>
...
```



이제 mode에 따라 다른 태그를 사용해야하기 때문에 `_article` 이라는 태그를 동적으로 할당하자.



_/src/App.js_

```react
class App extends Component {
  ...
  render() {
    console.log('App render');
    var _title, _desc, _article = null;  // 1
    if(this.state.mode === 'welcome'){
      _title = this.state.welcome.title;
      _desc = this.state.welcome.desc;
      _article = <ReadContent title={_title} desc={_desc}></ReadContent>; // 2
    } else if(this.state.mode === 'read'){
      var i = 0;
      while(i < this.state.contents.length){
        var data = this.state.contents[i];
        if(data.id === this.state.selected_content_id){          
          _title = data.title;
          _desc = data.desc;
          break;
        }
        i++;
      }
      _article = <ReadContent title={_title} desc={_desc}></ReadContent>; // 2
    } else if(this.state.mode === 'create'){           // 2
      _article = <CreateContent></CreateContent>;
    }
    console.log('render', this);
    return (
      <div className="App">
        ...
        <Control onChangeMode={function(_mode){
          this.setState({
            mode:_mode
          });
        }.bind(this)}></Control>
        {_article}                // 3
      </div>
    );
  }
}
```



이제 컨트롤러를 누를때 마다 `_article` 부분이 각기 다른 `Content` 로 변경될 것이다.



step3



CreateContent.js 의 폼을 완성해주자.



_/src/component/CreateContent.js_

```react
import React, { Component } from 'react';

class CreateContent extends Component {
  render(){
    console.log('Content render');
    return (
        <article>
            <h2>Create</h2>
            <form action="/create_process" method="post"  // 1
              onSubmit={function(e){
                e.preventDefault();
                alert('Submit!!');
              }.bind(this)}
            >
              <p>
                <input type="text" name="title" placeholder="title"></input>
                </p>
              <p>
                <textarea name="desc" placeholder="description"></textarea>
                </p>
              <p>
                <input type="submit"></input>
              </p>
            </form>
        </article>
    );
  }
}

export default CreateContent;
```



1 의 속성들은 HTML 이 form 태그의 기본 속성들이다.



_참고_

input 의 **placeholder** 속성은 값이 없을때 기본값을 설정해 준다.





_step4_



form 에서 입력받은 값을 App.js 에서 얻고싶다.



_/src/component/CreateContent.js_

```react
...
            <form action="/create_process" method="post"
              onSubmit={function(e){
                e.preventDefault();
                alert('Submit!!');
                this.props.onSubmit(
                  e.target.title.value,
                  e.target.desc.value
                );
              }.bind(this)}
            >
...
```



event 가 form인 경우에는 target 속성에 name 속성에 지정했던 값이 value 값으로 저장되어 있다.



_/src/App.js_

```react
...
	} else if(this.state.mode === 'create'){
      _article = <CreateContent onSubmit={function(_title, _desc){
        // add content to this.state.contents
        console.log(_title, _desc);
      }.bind(this)}></CreateContent>;
    }
...
```



폼을 완성하여 submit을 하면 `_title` 과  `_desc` 을 console 에서 확인해 볼 수 있다.



_step5_



이제 입력 받은 내용을 `contents` 에 추가해보자.



_/src/App.js_

```react
...
class App extends Component {
  constructor(props){
    super(props);
    this.max_content_id = 3; // 1
	....
  }
	...
    } else if(this.state.mode === 'create'){
      _article = <CreateContent onSubmit={function(_title, _desc){
        // add content to this.state.contents
        this.max_content_id = this.max_content_id+1; // 1
        this.state.contents.push(
          {id:this.max_content_id, title:_title, desc:_desc}
        );          // 2
        this.setState({
          contents:this.state.contents          
        });         // 2
        console.log(_title, _desc);
      }.bind(this)}></CreateContent>;
    }
    console.log('render', this);
...
```



1 은 신규 콘텐츠마다 아이디 값을 늘려주기 위해 사용하는 변수이다.

2 는 입력받은 콘텐츠를 저장시킨다.



물론 위에 방식으로 사용이 가능하나 좋은 방법이 아니다. 

`push` 의 경우에는 원본 데이터를 변경시킨다.

`concat` 을 사용해서 새로운 데이터를 만들어 교체한다.



따라서, state 값을 변경할때는 새로운 데이터를 만들어 교체하는 방법을 사용하도록 하자.

`push` 를 사용할 경우 나중에 성능상 문제를 야기할 수 있다.





## Create 구현 : ShouldComponentUpdate 부터 이어서..



















