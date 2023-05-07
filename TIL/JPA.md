# JPA ( Java Persistence API )
---
> 자바 진영에서 **ORM ( Object-Relational Mapping )**
기술 표준으로 사용되는 **인터페이스의 모음**

## 🤔 ORM?
### 객체와 DB 테이블을 매핑하는 기술
**Ex) user 테이블의 모든 정보 조회**
기존 = ```SELECT * FROM user```
ORM = ```user.findAll()```
> 위와 같이 **user 객체와 user 테이블을 매핑**하여,
**_findAll()_**이라는 메소드를 통해 정보를 조회한다.

### 장점
- SQL 문이 아니라 **Method로 DB를 조작**하므로 비즈니스 로직 개발에 집중 가능
- 코드의 **가독성**이 올라감
- **DBMS의 변경**이 일어나도 쿼리 수정이 필요 없음
### 단점
- 규모가 크고 복잡하여 설계가 잘못되면, **속도 저하 및 일관성이 무너짐**
- 복잡하고 **무거운 쿼리는 별도의 튜닝**이 필요함

### JPA( ORM )를 사용하는 이유
- **반복적인 CRUD SQL문** 처리
- **패러다임 불일치**
> **패러다임 불일치란?**
관계형 데이터베이스 = _어떻게 데이터를 저장할지에 초점_
객체지향 프로그래밍 언어 = _상속, 추상화, 캡슐화, 다형성 등 기능 제공_
>
위와 같이 **각자의 패러다임이 달라, 객체를 DB에 저장할 때 여러 문제가 발생**한다.
이를 **패러다임 불일치**라고 한다.
## Hibernate
> ### JPA ( Interface ) 를 구현한 구현체

개발된 지 10년이 넘었고 대중적으로 가장 많이 사용되는 **JPA 구현체** 중 하나
![](https://velog.velcdn.com/images/rkadl9999/post/8107449f-cbe9-4023-aa71-157062b40914/image.png)
[이미지 출처](https://code-lab1.tistory.com/288)
위와 같이 JPA의 구현체로는 Hibernate 말고도 EclipseLink, DataNucleus 등이 있다.

## Spring Data JPA
> ### Spring에서 JPA를 사용하기 쉽도록 만든 모듈

### 구현체 교체의 용이성
- Hibernate 대신 **새로운 JPA 구현체를 사용**하고 싶을 때 쉽게 교체 가능
- Spring Data JPA 내부에서 **구현체 매핑**을 지원
### 저장소 교체의 용이성
- 관계형 데이터베이스 외에 **다른 저장소로 쉽게 교체**하기 위함
- Spring Data 하위 프로젝트들은 **기본적인 CRUD 인터페이스가 동일**
Ex) MongoDB로 변경시, Spring Data MongoDB로 의존성만 교체
