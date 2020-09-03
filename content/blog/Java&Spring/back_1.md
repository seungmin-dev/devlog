---
title: 🔌Spring framework & MVC 2 Pattern
date: 2020-09-03 17:09:80
category: Java&Spring
draft: false
---

## Spring Framework

#### 자바 플랫폼을 위한 <u>_오픈소스 애플리케이션 프레임워크_</u> 로서 '스프링'이라고도 불린다.

스프링 버전은 2004년 3월에 1.0, 가장 최근 버전은 2017년 9월의 5.0

<br><br>

### IOC

스프링 프레임워크는 IOC기반.  
`IOC` - _(Inversion of Control)_ 기존 사용자가 모든 작업을 제어하던 것을 특별한 객체에 모든 것을 위임하여 객체의 생성부터 생명주기 등 모든 객체에 대한 제어권이 넘어간 것을 <u>**IOC, 제어의 역전**</u>이라고 한다.

#### IOC는 **DI**와 **DL**에 의해 구현된다.

> **`DL`** - _(Dependency Lookup)_ 의존성 검색

    IOC 컨테이너는  각 컨테이너에서 관리해야 하는 객체들을 관리하기 위한 별도의 저장소를 가지게 되는데, 이 IOC 컨테이너가 관리중인 객체 저장소에서 객체를 검색하여 참조하는 방법.(컨테이너에서 제공하는 api를 이용하여 찾고자 하는 bean을 lookup하는 방법)

> **`DI`** - _(Dependency Injection)_ 의존성 주입

    객체가 서로 의존하는 관계가 되게 의존성을 주입하는 것. 객체지향 프로그램에서 의존성이란 하나의 객체가 어떠한 다른 객체를 사용하고 있음을 의미. IOC에서의 DI는 '각 클래스 사이에 필요로 하는 의존관계를 빈(bean) 설정 정보를 바탕으로 컨테이너가 자동으로 연결'해주는 것

<br><br>

---

<br>

### Spring Framework의 특징 **POJO**

`POJO` - _(Plain Old Java Object)_ `getter/setter`를 가진 단순 자바 오브젝트. 이러한 단순 오브젝트는 의존성이 없고 추후 테스트 및 유지보수가 편리한 유연성의 장점을 가진다. 이러한 장점들로 인해 객체지향적인 다양한 설계와 구현이 가능해지고 POJO 기반의 Framework가 조명을 받고 있음.

### Spring Framework의 특징 **AOP**

`AOP` - _(Aspect Oriented Programming)_ 관점 지향 프로그래밍. AOP↔OOP. 무분별하게 중복되는 코드를 한 곳에 모아 중복되는 코드를 제거할 수 있고 공통기능을 한 곳에 보관함으로써 공통 기능 하나의 수정으로 모든 핵심기능들의 공통기능을 수정할 수 있어 요율적인 유지보수가 가능하며 재활용성이 극대화.

### Spring Framework의 특징 **MVC(Pattern 2)**

- **Model** - 데이터처리를 담당하는 부분. Model = Service + DAO
- **View** - 사용자 Interface를 담당하며 사용자에게 보여지는 부분
- **Controller** - View에서 받은 요청을 가공, Model(Service 영역)에 이를 전달. 또한 model로부터 받은 결과를 View로 넘겨주는 역할. Model과 View의 정보에 대해 알고 있어야 한다.  
  <br><br>

---

<br>

## MVC Pattern 2

#### **M**odel, **V**iew, **C**ontroller

#### 개발 형태의 일종

> 두 모델의 큰 차이점은 JSP가 <u>결과의 출력 뿐만 아니라 요청에 대한 모든 로직들을 처리하냐</u>, <u>결과의 출력만 담당하냐</u>의 차이.

- **_`Model`_** - 데이터베이스와의 관계를 담당, 클라이언트의 요청에서 필요한 자료를 데이터베이스로부터 추출하거나 수정하여 Controller로 전달
- **_`View`_** - 사용자한테 보여지는 UI 화면, 주로 .jsp파일로 작성, Controller에서 어떤 View 컴포넌트를 보여줄지 결정
- **_`Controller`_** - Model, View를 지시 및 전달 담당, 클라이언트의 요청을 받고, 적절한 Model에 지시 내리며, Model에서 전달된 데이터를 적절한 View에 전달

### ➡ 이렇게 작업을 분할하면 추후 유지보수할 때 용이

<br>

> - `MVC 1 Pattern`은 **View**와 **Controller**가 같이 있는 형태
> - 규모가 작고 유지보수보단 빠른 개발이 필요할 때 사용. 그러나 추후 유지보수 시 Controller와 View가 함께 있다보니 소스가 지저분하고 고치기 힘들다.  
>   (뷰와 로직을 모두 JSP 페이지 하나에서 처리하는 구조)
> - JSP + 자바빈 혹은 서비스 클래스

> - `MVC 2 Pattern`은 **Model, View, Controller**가 모두 **모듈화**되어 있는 상태
> - 서비스 + JSP + 자바빈 혹은 서비스 클래스
> - 요청이 들어오면 요청에 대한 로직 처리는 이를 처리할 모델인 '서비스 클래스 혹은 자바빈'이 담당하고, 요청 결과는 유저에게 결과를 보여줄 뷰단인 JSP에 출력되며, 이를 위한 모든 흐름 제어는 컨트롤러인 서블릿에서 담당한다.

<br><br>

---

<br>

> **참고 블로그**

    - https://goddaehee.tistory.com/156 => 스프링 용어 설명
    - https://khj93.tistory.com/entry/Spring-Spring-Framework%EB%9E%80-%EA%B8%B0%EB%B3%B8-%EA%B0%9C%EB%85%90-%ED%95%B5%EC%8B%AC-%EC%A0%95%EB%A6%AC => 스프링 용어 설명 자세히
    - https://hsp1116.tistory.com/9
