# About Vue Emit

 - Props : 부모 컴포넌트에서 자식 컴포넌트로 데이터를 전달할 때 사용
 - Emit : 자식 컴포넌트에서 부모 컴포넌트로 데이터를 전달할 때 사용
 
	## 주요 사항 ##
	1. 전달 키와 받는 키가 동일해야 한다.
	2. 받는 키를 등록해줘야 한다.
	
# 부모 Component
	metods: {
		setInput(value){
			this.value=value;
		}
	}
 setInput() 메서드 안에 value 는 자식 Component에서 받아오는 키 값이 된다.
 
# 자식 Component
	methods: {
		onEmit(){
			this.$emit("setInput", this.value);
		}
	}
 자식 Component에서 보내고자 하는 키 값과 보낼 메서드를 emit해준다.
 이 때 value 외에 키값을 더 보내고 싶다면 , this.value2, this.value3 과 같이 작성해주고
 부모 Component에서도 setInput(value, value2, value3)과 같이 받아주면 된다.
 
 복습