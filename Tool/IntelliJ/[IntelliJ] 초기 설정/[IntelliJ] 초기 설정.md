# [IntelliJ] 초기 설정





## License Server

1. IntelliJIDEALicenseServer_windows_amd64 실행
2. IntelliJ IDEA실행
3. Server 주소에 1에서 실행된 서버 URL 입력



## Import

시작 화면에서 Import 할 수 있다.

* Import 할때 workspace가 아닌 프로젝트를 선택하도록 한다.



## JDK

File - Project Structure - Project - Project SDK

설치 받은 JDK를 등록하도록 하자.

![이미지 5](이미지 5.jpg)

## Lombok

File - Settings - Plugins

*lombok* 검색.

![이미지 1](이미지 1.jpg)

제일 많이 받은거 설치.

![이미지 2](이미지 2.jpg)



## Maven View

View - Tool Windows - Maven Project

우측 메뉴가 생기며 props 를 선택할 수 있다.

![이미지 3](이미지 3.jpg)



## Maven Auto Import

File - Settings - Build, Execution, Deployment - Build Tools - Maven - Importing

Import Maven projects automatically V 체크.

![이미지 4](이미지 4.jpg)



> 메이븐이 빌드되면 USER/{ID}/.m2 파일에 라이브러리들이 저장된다.



## Run Configuration

Run - Edit Configurations

 혹은 초록 화살표 옆에있는 상자 클릭 - Edit Configurations



![이미지 6](이미지 6.jpg)



\+ 버튼 클릭 - Tomcat Server - Local - 환경설정 후 Apply

![이미지 7](이미지 7.jpg)





