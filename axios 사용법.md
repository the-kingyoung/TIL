# Axios란?

 - Axios는 브라우저, Node.js를 위한 Promise API를 활용하는 HTTP 비동기 통신 라이브러리
 - 즉, 백앤드와 프론트앤드의 통신을 쉽게 하기 위해 Ajax와 더불어 사용
 
# Axios 특징
 - 운영 환경에 따라 브라우저의 XMLHttpRequest객체 또는 Node.js의 http api 사용
 - Promise(ES6) API 사용
 - 요청과 응답 데이터의 변형
 - HTTP 요청 취소
 - HTTP 요청과 응답을 JSON 형태로 자동 변경 - 복습
 
## 예제 코드
	import axios from 'axios';

	axios.get('주소')
	.then((Response)=>{
    console.log(Response.data);
	}).catch((Error)=>{
    console.log(Error);
	})
	
	- POST형태 => 새로운 리소스(Create)를 생성할 때 사용
		axios.post("url주소",{
    		data객체
    	},[,config])
    	
    	- post 메서드의 두번째 인자는 본문으로 보낼 데이터를 설정한 객체 리터럴을 전달
    	  로그인, 회원가입 등 사용자가 생성한 파일을 서버에다가 업로드 할 때 사용
    	  
    	  
# EventBus 
컴포넌트간 데이터 전달

복습