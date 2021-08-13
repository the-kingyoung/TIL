# 기본부터 하기 위한 백준 자바 천천히 풀어나가기
--------------------------------------------

# 문제
 - 주어진 수 N개 중에서 소수가 몇 개인지 찾아서 출력하는 프로그램을 작성하시오.
 
# 입력
 첫 줄에 수의 개수 N이 주어진다. N은 100이하이다. 다음으로 N개의 수가 주어지는데 수는 1,000 이하의 자연수이다.
# 출력
 - 주어진 수들 중 소수의 개수를 출력한다.
 
 
~~~java

import java.util.Scanner;

public class baekjoon0017 {
	public static void main(String[] args) {

		Scanner scan = new Scanner(System.in);

		int x = scan.nextInt();

		int count = 0;

		for (int i = 0; i < x; i++) {
			boolean num = true;

			int y = scan.nextInt();

			if (y == 1) {
				continue;
			}
			for (int j = 2; j <= Math.sqrt(y); j++) {
				if (y % j == 0) {
					num = false;
					break;
				}
			}
			if (num) {
				count++;
			}

		}
		System.out.println(count);
	}
}
~~~