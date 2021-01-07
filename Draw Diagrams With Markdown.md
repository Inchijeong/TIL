- [Back](https://support.typora.io/)

# Draw Diagrams With Markdown

August 15, 2016 by typora.io

Typora supports some Markdown extensions for diagrams, once they are enabled from preference panel.

When exporting as HTML, PDF, epub, docx, those rendered diagrams will also be included, but diagrams features are not supported when exporting markdown into other file formats in current version. Besides, you should also notice that diagrams is not supported by standard Markdown, CommonMark or GFM. Therefore, we still recommend you to insert an image of these diagrams instead of write them in Markdown directly.

# Sequence Diagrams

This feature uses [js-sequence](https://bramp.github.io/js-sequence-diagrams/), which turns the following code block into a rendered diagram:

~~~gfm
```sequence
Alice->Bob: Hello Bob, how are you?
Note right of Bob: Bob thinks
Bob-->Alice: I am good thanks!
```
~~~

![Node.js 시퀀스](https://support.typora.io/media/diagrams/js-sequence.png)

For more details, please see [this syntax explanation](https://bramp.github.io/js-sequence-diagrams/#syntax).

# Flowcharts

이 기능은 다음 코드 블록을 렌더링 된 다이어그램으로 변환하는 [순서도 .js를](http://flowchart.js.org/) 사용합니다 .

~~~gfm
```flow
st=>start: Start
op=>operation: Your Operation
cond=>condition: Yes or No?
e=>end

st->op->cond
cond(yes)->e
cond(no)->op
```
~~~

![순서도](https://support.typora.io/media/diagrams/flowchart.png)

# 인어

Typora 는 시퀀스 다이어그램, 순서도, Gantt 차트, 클래스 및 상태 다이어그램, 파이 차트를 지원 하는 [mermaid](https://mermaid-js.github.io/mermaid/#/) 와도 통합됩니다 .

## 시퀀스 다이어그램

자세한 내용은 [이 지침을](https://mermaid-js.github.io/mermaid/#/sequenceDiagram) 참조하십시오 .

~~~gfm
```mermaid
%% Example of sequence diagram
  sequenceDiagram
    Alice->>Bob: Hello Bob, how are you?
    alt is sick
    Bob->>Alice: Not so good :(
    else is well
    Bob->>Alice: Feeling fresh like a daisy
    end
    opt Extra response
    Bob->>Alice: Thanks for asking
    end
```
~~~

![인어 시퀀스](https://support.typora.io/media/diagrams/mermaid-sequence.png)

## 순서도

자세한 내용은 [이 지침을](https://mermaid-js.github.io/mermaid/#/flowchart) 참조하십시오 .

~~~gfm
```mermaid
graph LR
A[Hard edge] -->B(Round edge)
    B --> C{Decision}
    C -->|One| D[Result one]
    C -->|Two| E[Result two]
```
~~~

![인어 순서도](https://support.typora.io/media/diagrams/mermaid-flowchart.png)

## 간트 차트

자세한 내용은 [이 지침을](https://mermaid-js.github.io/mermaid/#gantt) 참조하십시오 .

~~~gfm
```mermaid
%% Example with selection of syntaxes
        gantt
        dateFormat  YYYY-MM-DD
        title Adding GANTT diagram functionality to mermaid

        section A section
        Completed task            :done,    des1, 2014-01-06,2014-01-08
        Active task               :active,  des2, 2014-01-09, 3d
        Future task               :         des3, after des2, 5d
        Future task2               :         des4, after des3, 5d

        section Critical tasks
        Completed task in the critical line :crit, done, 2014-01-06,24h
        Implement parser and jison          :crit, done, after des1, 2d
        Create tests for parser             :crit, active, 3d
        Future task in critical line        :crit, 5d
        Create tests for renderer           :2d
        Add to mermaid                      :1d

        section Documentation
        Describe gantt syntax               :active, a1, after des1, 3d
        Add gantt diagram to demo page      :after a1  , 20h
        Add another diagram to demo page    :doc1, after a1  , 48h

        section Last section
        Describe gantt syntax               :after doc1, 3d
        Add gantt diagram to demo page      : 20h
        Add another diagram to demo page    : 48h
```
~~~

![인어 간트](https://support.typora.io/media/diagrams/mermaid-Gantt-chart.png)

## 클래스 다이어그램

자세한 내용은 [이 지침을](https://mermaid-js.github.io/mermaid/#/classDiagram) 참조하십시오 .

~~~gfm
```mermaid
classDiagram
      Animal <|-- Duck
      Animal <|-- Fish
      Animal <|-- Zebra
      Animal : +int age
      Animal : +String gender
      Animal: +isMammal()
      Animal: +mate()
      class Duck{
          +String beakColor
          +swim()
          +quack()
      }
      class Fish{
          -int sizeInFeet
          -canEat()
      }
      class Zebra{
          +bool is_wild
          +run()
      }
```
~~~

![클래스 다이어그램](https://support.typora.io/media/new-80/class-diagram.png)

## 상태 다이어그램

자세한 내용은 [이 지침을](https://mermaidjs.github.io/#/stateDiagram) 참조하십시오 .

~~~gfm
```mermaid
stateDiagram
    [*] --> Still
    Still --> [*]

    Still --> Moving
    Moving --> Still
    Moving --> Crash
    Crash --> [*]
```
~~~

![상태 다이어그램](https://support.typora.io/media/new-80/state-diagram.png)

## 파이 차트

~~~gfm
```mermaid
pie
    title Pie Chart
    "Dogs" : 386
    "Cats" : 85
    "Rats" : 150 
```
~~~

![파이 차트](https://support.typora.io/media/new-80/pie-chart.png)

[Github에서](https://github.com/typora/wiki-website) 호스팅됩니다 .

<iframe id="_atssh615" title="AddThis 유틸리티 프레임" src="https://s7.addthis.com/static/sh.f48a1a04fe8dbf021b4cda1d.html#rand=0.411534069529085&amp;iit=1600965632071&amp;tmr=load%3D1600965632026%26core%3D1600965632059%26main%3D1600965632064%26ifr%3D1600965632078&amp;cb=0&amp;cdn=0&amp;md=0&amp;kw=&amp;ab=-&amp;dh=support.typora.io&amp;dr=https%3A%2F%2Fwww.google.com%2F&amp;du=https%3A%2F%2Fsupport.typora.io%2FDraw-Diagrams-With-Markdown%2F&amp;href=https%3A%2F%2Fsupport.typora.io%2FDraw-Diagrams-With-Markdown%2F&amp;dt=Draw%20Diagrams%20With%20Markdown&amp;dbg=0&amp;cap=tc%3D0%26ab%3D0&amp;inst=1&amp;jsl=0&amp;prod=undefined&amp;lng=ko&amp;ogt=&amp;pc=men&amp;pub=ra-5ed23a5bcf8c017f&amp;ssl=1&amp;sid=5f6ccc00082e4cbc&amp;srf=0.01&amp;ver=300&amp;xck=0&amp;xtr=0&amp;og=&amp;csi=undefined&amp;rev=v8.28.7-wp&amp;ct=1&amp;xld=1&amp;xd=1" style="height: 1px; width: 1px; position: absolute; top: 0px; z-index: 100000; border: 0px; left: 0px;"></iframe>



[
  ](https://support.typora.io/Draw-Diagrams-With-Markdown/#)