# [Spring] Scheduling



스케쥴러 사용시 서버 실행 이후 특정 메소드를 사용하고 싶다면 다음과 같이 bean을 등록한다.



```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xmlns:task="http://www.springframework.org/schema/task"
       xsi:schemaLocation="http://www.springframework.org/schema/beans
						http://www.springframework.org/schema/beans/spring-beans-4.2.xsd
						http://www.springframework.org/schema/task
						http://www.springframework.org/schema/task/spring-task-4.2.xsd">
    <task:scheduled-tasks>
        <task:scheduled ref="TestScheduler" method="cron" cron="0 0 10,14 * * MON-FRI"/>
    </task:scheduled-tasks>
    
	<bean class="kr.co.test.TestScheduler" init-method="cron"></bean>  <!-- 1 -->
    
</beans>
```



1을 보면 `TestScheduler`의 `cron` 메소드를 실행시킨다.