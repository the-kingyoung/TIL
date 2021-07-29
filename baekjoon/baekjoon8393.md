# 기본부터 하기 위한 백준 자바 천천히 풀어나가기
--------------------------------------------

# 문제
 - n이 주어졌을 때, 1부터 n까지 합을 구하는 프로그램을 작성하시오.
 
# 입력
 - 첫째 줄에 n (1 ≤ n ≤ 10,000)이 주어진다.
 
# 출력
 - 1부터 n까지 합을 출력한다.
 
 
 
~~~java

import java.util.Scanner;

public class baekjoon0006 {

	public static void main(String[] args) {

		Scanner scan = new Scanner(System.in);

		int a = scan.nextInt();
		scan.close();
		int total = 0;

		for (int i = 1; i <= a; i++) {
			total += i;
		}
		System.out.println("1부터 " + a + "까지의 총 합은 " + total);

	}

}

~~~