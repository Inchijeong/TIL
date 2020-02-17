# [React] State



> 생활코딩의 [React] 를 학습하고 정리한 글입니다.
>
> 일부 이미지는 영상의 이미지를 캡처하였습니다.
>
> [생활코딩 React](https://opentutorials.org/module/4058)



Component를 사용자가 조작할 수 있도록 하는 것은 __Props__이다.

사용자는 알 필요 없고 보여줄 필요없이 내부에서 사용하는 속성은 __State__이다.



_/src/App.js_

```react
...
<Subject title="WEB" sub="world wide web!"></Subject>
...
```

우리는 이전에 props를 통해 `title` 과 `sub` 라는 속성을 통해 값을 주고 동적인 컴포넌트를 만들었다.



우선은 state를 통해 기본값을 줘보자.



_/src/App.js_

```react
...
class App extends Component {
  constructor(props){
    super(props);
    this.state = {
      subject:{title:'WEB', sub:'World wide web!'}
    }
  }  // 1
  render() {
    return (
      <div className="App">
        <Subject
          title={this.state.subject.title}
          sub={this.state.subject.sub}>
        </Subject>                          <!-- 2 -->
		...
      </div>
    );
  }
}
...
```



1 에서 state 값이 저장되고 2 에서 값을 전달하고 있다.

`constructor`는 객체가 생성될때 객체의 속성을 초기화하는 역할을 한다.

state 값을 줄때 형식적으로 다음과 같이 생성자 안에서 사용하도록 하자.

```react
constructor(props){
	super(props);
	this.state = {}
}
```



다양한 객체를 전달하고 싶다면 state에 배열을 저장한다.



_/src/App.js_

```react
...
class App extends Component {
  constructor(props){
    super(props);
    this.state = {
      subject:{title:'WEB', sub:'World wide web!'},
      contents:[
        {id:1, title:'HTML', desc:'HTML is for information'},
        {id:2, title:'CSS', desc:'CSS is for design'},
        {id:3, title:'JavaScript', desc:'JavaScript is for interactive'},
      ] // 1
    }
  }
  render() {
    return (
      <div className="App">
        ...
        <TOC data={this.state.contents}></TOC>    <!-- 2 -->
		...
      </div>
    );
  }
}
...
```



위에서와 마찬가지로 1에서 저장하고 2에서 state값을 전달하고 있다.



_/src/components/TOC.js_

```react
...
class TOC extends Component {
  render(){
    var lists = [];
    var data = this.props.data;
    var i = 0;
    while(i < data.length){
      lists.push(<li><a href={data[i].id}>{data[i].title}</a></li>)
      i++;
    }
    return(
        <nav>
            <ul>
                {lists}
            </ul>
        </nav>
    );
  }
}
...
```



위처럼 반복문을 사용하여 활용할 수 있는데 이때 반복해서 태그를 생성하면 콘솔에 다음과 같은 경고가 뜬다.

> Warning: Each child in a list should have a unique "key" prop.

이는 React에서 반복문으로 만들어진 태그에 각각에 고유값을 요구하는 것이다.

다음과 같이 태그에 우리가 지정한 고유값을 저장하면 경고는 사라진다.

```react
...
    while(i < data.length){
      lists.push(<li key={data[i].id}><a href={data[i].id}>{data[i].title}</a></li>)
      i++;
    }
...
```



*정리*

1. props는 부모가 자식 컴포넌트에게 정보를 전달할때 사용한다.
2. state는 자신 안에서 어떤 정보를 이용할때 사용한다.































