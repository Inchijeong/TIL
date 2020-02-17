## [Spring Boot] 프로젝트 생성 및 테스트



new -> Spring Start Project



![[Spring Boot] 프로젝트 생성 및 테스트]([Spring Boot] 프로젝트 생성 및 테스트.png)



![[Spring Boot] 프로젝트 생성 및 테스트2]([Spring Boot] 프로젝트 생성 및 테스트2.png)



프로젝트를 생성할때 라이브러리를 받기 때문에 시간이 많이 걸린다.

하지만 이후 다시 같은 라이브러리를 사용하면 시간이 단축된다.





_/src/main/resources/application.properties_

설정을 지정하는 파일



_org.zerock.ServletInitializer.java_

서블릿을 실행하는 역할



다음 명령어로 실행 가능함.

Run as -> Spring Boot App



Console 탭에서 포트 번호와 실행 시간을 확인할 수 있다.

```
Tomcat started on port(s): 8080 (http) with context path ''
Started Boot01Application in 1.545 seconds (JVM running for 2.065)
```



_참고_

포트번호를 변경하려면

_application.properties_

```properties
server.port=8000
```



MVC의 컨트롤러를 빈으로 추가해보자.



![[Spring Boot] 프로젝트 생성 및 테스트3]([Spring Boot] 프로젝트 생성 및 테스트3.png)



_org.zerock.controller.SampleController_

```java
package org.zerock.controller;

import org.springframework.web.bind.annotation.RestController;

@RestController
public class SampleController {

}
```



_참고_

기본 패키지가 아닌 패키지에 작성한 코드를 스프링에서 사용하고자 한다면,

`@ComponentScan` 어노테이션을 이용한다.

_org.sample_ 패키지 하위에 있는 클래스를 인식시키고 싶다면 다음과 같이 작성한다.

_org.zerock.ServletInitializer.java_

```java
@SpringBootApplication
@ComponentScan(basePackages={"org.sample", "org.zerock"})
public class Boot01Application {

	public static void main(String[] args) {
		SpringApplication.run(Boot01Application.class, args);
	}

}
```



이제 화면에 Hello World 를 출력해보자.



_org.zerock.controller.SampleController_

```java
package org.zerock.controller;

import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.RestController;

@RestController
public class SampleController {
	
	@GetMapping("/hello")
	public String sayHello() {
		return "Hello World";
	}
}
```



![[Spring Boot] 프로젝트 생성 및 테스트4]([Spring Boot] 프로젝트 생성 및 테스트4.png)



만약 실행이 되지않는다면 Sprig Boot 를 Stop 시키고 재시작해본다.



테스트 코드를 작성해본다.

`testHello` 는 성공적인 테스트 결과이고`testHello2` 는 실패한 테스트 결과이다.

두 결과를 비교해 보자.



_/src/test/java/org.zerock.SampleControllerTests.Java_

```java
package org.zerock;

import static org.springframework.test.web.servlet.request.MockMvcRequestBuilders.get;
import static org.springframework.test.web.servlet.result.MockMvcResultMatchers.content;

import org.junit.jupiter.api.Test;
import org.junit.runner.RunWith;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.boot.test.autoconfigure.web.servlet.WebMvcTest;
import org.springframework.test.context.junit4.SpringRunner;
import org.springframework.test.web.servlet.MockMvc;
import org.zerock.controller.SampleController;

@RunWith(SpringRunner.class)
@WebMvcTest(SampleController.class)
public class SampleControllerTests {
	
	@Autowired
	MockMvc mock;
	
	@Test
	public void testHello() throws Exception{
		
		mock.perform(get("/hello")).andExpect(content().string("Hello World"));
	}
	@Test
	public void testHello2() throws Exception{
		
		mock.perform(get("/hello")).andExpect(content().string("false"));
	}
	
}
```

