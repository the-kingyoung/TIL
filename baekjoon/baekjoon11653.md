# 기본부터 하기 위한 백준 자바 천천히 풀어나가기
--------------------------------------------

# 문제
 - 정수 N이 주어졌을 때, 소인수분해하는 프로그램을 작성하시오.
 
# 입력
 - 첫째 줄에 정수 N (1 ≤ N ≤ 10,000,000)이 주어진다.
 
 
 
~~~java

import java.util.Scanner;

public class baekjoon0020 {
	public static void main(String[] args) {

		Scanner scan = new Scanner(System.in);

		int n = scan.nextInt();

		for (int i = 2; i <= Math.sqrt(n); i++) {
			while (n % i == 0) {
				System.out.println(i);
				n /= i;
			}
		}
		if (n != 1) {
			System.out.println(n);
		}
	}

}
~~~