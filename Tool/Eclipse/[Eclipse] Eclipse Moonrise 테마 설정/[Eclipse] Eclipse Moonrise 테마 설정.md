# [Eclipse] Eclipse Moonrise & RainbowDrops 테마 설정

이클립스(Eclipse)에 UI Theme를 설정해보겠습니다.

기존 Darkest Dark 테마를 사용하다가 이번에 이클립스를 재설치하면서 새로운 테마를 찾았습니다.

테마 설정 방법은 대부분 비슷하니 이 설치법으로 다른 테마를 사용하셔도 좋습니다.  

저는 Moonrise 테마와 RainbowDrops 테마의 Syntax Highlighting Scheme를 사용합니다.

[나는 개발자다](https://dream-kwon.tistory.com/38)님의 블로그를 보고 적용하였습니다.



## Moonrise & RainbowDrops 미리보기

![1](1.png)



## Moonrise UI Theme 설치

1. 이클립스 실행

2. 상단 메뉴의 Help - Eclipse Marketplace... 클릭

   ![2](2.png)

3. 'moonrise' 검색

4. Eclipse Moonrise UI Theme 의 Install 클릭

   ![3](3.png)

5. 설치 완료되면 이클립스 재시작  
   


## Moonrise UI Theme 설정

1. 상단 메뉴의 Window - Preferences

   ![4](4.png)

2. General - Appearance 클릭

3. Theme: MoonRise (standalone) 클릭

4. Apply and Close

   ![5](5.png)

  


## RainbowDrops Theme 설치

1. <http://www.eclipsecolorthemes.org/?view=theme&id=24587> 사이트에 접속

2. Eclipse Preferences 클릭

   * 아래 파일을 직접 받으셔도 됩니다.

   *  [RainbowDrops.epf](RainbowDrops.epf) 

   ![6](6.png)

   


## Syntax Highlighting Scheme 적용

1. 이클립스 실행

2. 상단 메뉴의 File - Import... 클릭

![7](7.png)

3. General - Preferences 선택 후 Next

![8](8.png)

4. 아까 다운받은 theme-24587 (혹은 RainbowDrops.epf) 불러오기 후 Finish

![9](9.png)

  

## Moonrise 개인적인 색상 변경

너무 어두워서 잘 보이지 않거나 뚜렷하게 보고 싶은 경우를 수정했습니다.

↓ 아래 설정 모두 공통 하위에 있습니다.

(공통) Window - Preferences - General - 

* 커밋되지 않은 파일 색상 변경

  Appearance - Colors and Fonts - Git - Uncommitted Change (Foreground) - RGB(255, 255,128)

* 파일 비교시 변경된 글자 색상 변경

  Appearance - Colors and Fonts - Text - Edition Color - RGB(128, 128, 255)

* 콘솔 텍스트 색상 변경

  Run/Debug - Console - Standard Out text color - RGB(192, 192, 192)

* 드래그 했을때 글자 색 변경

  Editors - Text Editors - Appearance color options: Selection foreground color - RGB(210, 220, 225)




## 링크

* [Eclipse Moonrise UI Theme](https://marketplace.eclipse.org/content/eclipse-moonrise-ui-theme)
* [RainbowDrops](http://www.eclipsecolorthemes.org/?view=theme&id=24587)



