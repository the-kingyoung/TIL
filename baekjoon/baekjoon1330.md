# 기본부터 하기 위한 백준 자바 천천히 풀어나가기
--------------------------------------------

# 문제
 - 두 정수 A와 B가 주어졌을 때, A와 B를 비교하는 프로그램을 작성하시오. 
 
# 입력
 첫째 줄에 A와 B가 주어진다. A와 B는 공백 한 칸으로 구분되어져 있다.

# 출력
 - 첫째 줄에 다음 세 가지 중 하나를 출력한다.

 * A가 B보다 큰 경우에는 '>'를 출력한다.
 * A가 B보다 작은 경우에는 '<'를 출력한다.
 * A와 B가 같은 경우에는 '=='를 출력한다.
 
 
~~~java

import java.util.Scanner;

public class Main{

	public static void main(String[] args){
	
		Scanner scan = new Scanner(System.in);
		
		int A = scan.nextInt();
		int B = scan.nextInt();
		
		scan.close();
		
		if(A>B) System.out.println(A+">"+B);
		else if(A<B) System.out.println(A+"<"+B);
		else System.out.println(A+"=="+B);

	}
}
~~~