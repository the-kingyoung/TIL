# Spring vs Spring boot
	spring boot는 쉽게 만들 수 있고
	단독적으로 만들 수 있으며 상용화 수준까지 만들 수 있고
	스프링 기반 어플리케이션을 만들 수 있다.
	=> 간단하다는 것을 강조!
	
	가장 큰 차이는 dependency!
	spring은 모든 dependency를 버전까지 정확하게 기입해야하는 점과는 달리
	boot는 훨씬 짧고 권장 버전으로 자동 설정이 가능하다.
	spring-boot-starter-data-jpa
	spring-boot-starter-security
	spring-boot-starter-test
	spring-boot-starter-web
	spring-boot-starter-thymeleaf
	이것을 걸면 알아서 의존성이 걸려있는 것들을 넣어준다.
	
	configuration 역시
	spring 기반에서는 anotation을 달고 bean을 설정해주며 매우 긴 편이지만
	boot는 config파일을 따로 작성할 필요가 없고 application.properties만 적용을 하면 된다.
	요즘은 application.yml을 더 많이 사용하는 추세 (중복제거도 가능하고 depth로 표현을 하기 때문에 spring, data source, tab이 space 두번만 누르면 알아서)
	
	embedded server 내장 서버
	boot는 내장 서버를 가지고 있기 때문에 서버 구동시간이 절반 가까이 단축 된다.
	내장 서블릿 컨테이너 덕분에 jar 파일로 간단하게 배포가 가능하다.
	
	정리를 해보자면
	boot는
	1. 간편한 설정
	2. 편리한 의존성 관리 & 자동 권장 버전 관리
	3. 내장 서버로 인한 간단한 배포 서버 구축
	4. 스프링 security, data JPA 등의
		다른 스프링 프레임워크 요소를 쉽게 사용

 
