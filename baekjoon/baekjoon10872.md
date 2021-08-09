# 기본부터 하기 위한 백준 자바 천천히 풀어나가기
--------------------------------------------

# 문제
 - 0보다 크거나 같은 정수 N이 주어진다. 이때, N!을 출력하는 프로그램을 작성하시오.
 
# 입력
 첫째 줄에 정수 N(0 ≤ N ≤ 12)가 주어진다.

# 출력
 - 첫째 줄에 N!을 출력한다.
 
 
~~~java

import java.util.Scanner;

public class baekjoon0016 {
	public static void main(String[] args) {

		Scanner scan = new Scanner(System.in);
		
		int x = scan.nextInt();
		
		scan.close();
		
		int fac = 1;
		
		while(x != 0) {
			fac = fac*x;
			x--;
		}
		System.out.println(fac);
	}
}

}
~~~