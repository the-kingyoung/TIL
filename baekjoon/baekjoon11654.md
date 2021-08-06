# 기본부터 하기 위한 백준 자바 천천히 풀어나가기
--------------------------------------------

# 문제
 - 알파벳 소문자, 대문자, 숫자 0-9중 하나가 주어졌을 때, 주어진 글자의 아스키 코드값을 출력하는 프로그램을 작성하시오.
 
# 입력
 - 알파벳 소문자, 대문자, 숫자 0-9 중 하나가 첫째 줄에 주어진다.
 
 
 
~~~java

import java.util.Scanner;

public class baekjoon0013 {
	public static void main(String[] args) {
		Scanner scan = new Scanner(System.in);
		
		int code = scan.next().charAt(0);
		
		System.out.println("아스키 코드는 " + code);
	}
}
~~~