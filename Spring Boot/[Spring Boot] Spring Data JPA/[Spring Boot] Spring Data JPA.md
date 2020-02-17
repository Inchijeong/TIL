# [Spring Boot] Spring Data JPA



## JAP 란?

* JPA(Java Persistence API)는 Java를 이용해서 데이터를 관리(유지)하는 기법을 하나의 스펙으로 정리한 표준이다. 

* JPA를 이용하면 다양한 데이터베이스에 종속적인 SQL문 없이 개발 가능하다.

* ORM(Object Relational Mapping) 은 객체지향과 관계형 데이터베이스를 매핑시킨다는 추상화된 개념이다.

* 쉽게 말해 JAP는 ORM을 JAVA 언어에서 구현하기 위한 스펙인것이다.



## 엔티티(Entity), 엔티티 매니저(EntityManager)



### 엔티티란?

데이터베이스상에서 관리하는 대상. '상품', '회사', '직원' 등을 예로 들 수 있다.

JAP에서 '하나의 엔티티 타입을 생성한다' 라는 의미는 '하나의 클래스'를 작성한다는 의미이다.



### 엔티티 매니저란?

엔티티 객체들을 관리하는 역할. 여기서 관리란 'Life Cycle'.

영속 컨텍스트(Persistence Context)라는 곳에 넣어두고 객체들의 생사를 관리한다.











































