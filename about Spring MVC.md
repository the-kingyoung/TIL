# About Spring MVC

## MVC 구성요소에 대한 설명
 - 모델-뷰-컨트롤러라는 응용 프로그램을 세가지의 구성요소로 나눈다.
 
  - 컨트롤러 : 모델에 명령을 보냄으로써 모델의 상태를 변경할 수 있다.(ex. 워드 프로세서에서 문서를 편집하는 것) 
  	또, 컨트롤러가 관련된 뷰에 명령을 보냄으로써 모델의 표시 방법을 바꿀 수 있다.(문서를 스크롤 하는 것)
  
  - 모델 : 모델의 상태에 변화가 있을 때 컨트롤러와 뷰에 이를 통보한다. 이와 같은 통보를 통해서 뷰는 최신의 결과를 보여줄수 있고,
  		  컨트롤러는 모델의 변화에 따른 적용 가능한 명령을 추가, 제거, 수정할 수 있다.
  		  어떤 MVC 구현에서는 통보 대신 뷰나 컨트롤러가 직접 모델의 상태를 읽어 오기도 한다.
  		  
  - 뷰 : 사용자가 볼 결과물을 생성하기 위해 모델로부터 정보를 얻어 온다.
  
## Controller
 - 클라이언트에서 요청이 들어올 때, 해당 요청을 수행할 비즈니스 로직을 제어하는 객체이다.
   스프링에서는 컨트롤러에서 세부적으로 서비스 레이어를 만들어 해당 요청사항을 객체 지향적인 방식으로 좀 더 세분화하여 관리한다.
   
   * 비즈니스 로직 : 컴퓨터 프로그램에서 실세계의 규칙에 따라 데이터를 생성, 표시, 저장, 변경하는 부분
   				 사용자에게 보여지지 않는 부분에서 데이터를 처리하는 코드라고 보면 된다.

## Service
 - 서비스 레이어단에서 세분화된 비즈니스 로직을 처리하는 객체이다.
 - 서비스는 비즈니스 로직이 들어가는 부분이다.
 - Controller가 Request를 받으면 적절한 Service에 전달하고 전달 받은 Service는 비즈니스 로직을 처리한다.
 - DAO로 데이터베이스를 접근하고 DTO로 데이터를 전달받은 다음, 적절한 처리를 해 반환한다.
 
## DAO
 - DB를 사용해 데이터를 조회하거나 조작하는 기능을 전담하도록 만든 객체이다.
 - DB에 접근하는 객체를 뜻함!
 - DAO의 사용 이유는 효율적인 커넥션 관리와 보안성 때문

## VO
 - 각 계층간 데이터 교환을 위한 자바 객체를 의미
 - 이 객체는 데이터를 각 레이어 간에 전달하는 목적을 가지고 있으며, 객체의 속성과 getter, setter만 가지고 있다.
 - 계층간 데이터 겨환을 위한 자바 빈즈이다.
 - 이 객체는 데이터베이스 레코드의 데이터를 맵핑하기 위한 데이터 객체를 말한다.
 
 
 
 
===========================================================================================================복습
1) DispatcherServlet
 - 가장 앞서 요청을 받아들이기 때문에 Front Controller라고 불림
 - 스프링 프레임워크의 중심이 되는 서블릿, 클라이언트의 모든 요청을 받아 흐름을 제어
 - 각 컨트롤러에 요청을 전달하고 컨트롤러가 반환한 결과값을 View에 전달하여 응답
 - web.xml에 정의되어 있으며, 보통 servlet-context.xml 설정 파일을 읽어 컨테이너를 구동

2) HandlerMapping
 - 클라이언트의 요청 URL을 처리할 컨트롤러를 결정해 DispatcherServlet에 반환
 - @Controller 어노테이션이 적용된 객체의 @RequestMapping 값을 이용해 요청을 처리할 컨트롤러 탐색

3) HandlerAdapter
 - DispatcherServlet의 처리 요청을 변환해서 컨트롤러에게 전달
 - 컨트롤러의 응답 결과를 DispatcherServlet이 요구하는 형식으로 변환

4) Controller
 - 실제 클라이언트의 요청을 처리한 뒤, 처리 결과를 void, String, ModelAndView 형태로 반환
 - GET, POST 방식 등 전송 방식에 대한 처리를 어노테이션으로 처리

5) ViewResolver
 - 컨트롤러의 처리 결과를 보여줄 뷰를 결정

# 스프링 MVC가 처리해주는 작업
 - URI를 분석해서 적절한 컨트롤러를 결정
 - 컨트롤러에 필요한 메소드를 호출
 - 컨트롤러의 결과 데이터를 뷰로 전달
 - 처리 결과를 보여줄 적절한 뷰를 결정
 
# 개발자가 직접 해야하는 작업
 - 특정 URI에 동작하는 컨트롤러를 설계
 - 컨트롤러 내에 원하는 결과를 메서드로 설계
 - 서비스 객체의 생성
 - DAO 객체의 생성(Mybatis 사용시 X)
 - 뷰에서 전달받은 데이터의 출력

## Maven Dependency(?)
 - 스프링 MVC 사용시 JSP/Servlet 버전을 상향시킬 필요가 있음
 
================================================================================================================================
# 스프링 MVC 구현 방법

1) 컨트롤러 설계/구현
 - @Controller어노테이션을 클래스에 적용
 - @RequestMapping 어노테이션을 이용해서 처리할 요청 경로 지정
 - 클라이언트의 요청을 처리할 메서드를 구현하고, 뷰 이름 리턴
 - 리턴시 Redirect 형식으로 리턴한다면 다시 컨트롤러로 요청
 
2) 컨트롤러 - @RequestMapping 어노테이션
 - 리턴타입에 따른 경로 변경
 - RequestMapping 요청 방식 (GET, POST)
================================================================================================================================

## DTO/VO 객체를 이용
 - 폼데이터의 이름과 동일한 필드명을 가진 DTO/VO 객체를 이용해 데이터 처리 가능
 - 알아서 Getter / Setter 메서드를 이용해 데이터를 처리하기 때문에 가장 많이 사용되는 방법이다.
 - DTO/VO를 이용할 경우 컨트롤러 뿐 아니라 이후 보내지는 jsp페이지까지 데이터가 유효하다.
 
 % DTO/VO객체를 이용하여 데이터를 처리할 때 주의할 점이 있다.
 컨트롤러 이후 jsp 페이지로 객체가 보내질 때 객체의 이름은 클래스이름의 맨 앞 대문자만 소문자로 대치된 이름으로
 객체가 넘어가게 된다. @ModelAttribute 라는 어노테이션으로 보내지는 객체의 이름을 변경할 수 있다.
================================================================================================================================복습
## 서비스와 DAO 차이
 - DAO는 단일 데이터 접근/갱신만 처리한다.
 - Service는 여러 DAO를 호출하여 여러번의 데이터 접근/갱신을 하며 그렇게 읽은 데이터에 대한 비즈니스 로직을 수행하고
   그것을 하나의(또는 여러개의) 트랜잭션으로 묶는다.
   
   즉, 서비스가 트랜잭션 단위!
   DAO와 서비스가 완전히 동일해지는 경우도 발생을 하는데 이것은 해당 비즈니스 로직이 '단일 DB 접근'으로 끝나기 때문이다.
   
   만약 DAO의 메서드 하나에 다중 DB접근 로직이 들어갔고, 서비스는 단순히 그 DAO메서드를 호출하는 통로 역할만 한다면
   DAO측 모듈화가 제대로 안된 접근 방식일 가능성이 높다.
================================================================================================================================

## VO와 DTO의 차이
 - DTO는 읽고 쓰는 것이 가능하지만 VO는 읽기만 가능 


