# 기본부터 하기 위한 백준 자바 천천히 풀어나가기
--------------------------------------------

# 문제
 - 두 정수 A와 B를 입력받은 다음, A+B를 출력하는 프로그램을 작성하시오.
 
# 입력
 입력은 여러 개의 테스트 케이스로 이루어져 있다.

각 테스트 케이스는 한 줄로 이루어져 있으며, 각 줄에 A와 B가 주어진다. (0 < A, B < 10)

입력의 마지막에는 0 두 개가 들어온다.

# 출력
 - 각 테스트 케이스마다 A+B를 출력한다.
 
 
~~~java

import java.util.Scanner;

public class baekjoon0008 {

	public static void main(String[] args) {

		Scanner scan = new Scanner(System.in);

		while(true) {
			int a = scan.nextInt();
			int b = scan.nextInt();
			
			if(a==0 && b==0) {
				scan.close();
				System.out.println("계산이 종료됩니다.");
				break;
			}
			System.out.println("정답은 "+(a+b)+"입니다.");		
			System.out.println("0, 0 을 입력 시 종료됩니다.");
		}
		
		


	}

}
~~~