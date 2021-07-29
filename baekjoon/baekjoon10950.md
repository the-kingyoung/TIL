# 기본부터 하기 위한 백준 자바 천천히 풀어나가기
--------------------------------------------

# 문제
 - 두 정수 A와 B를 입력받은 다음, A+B를 출력하는 프로그램을 작성하시오.
 
# 입력
 첫째 줄에 테스트 케이스의 개수 T가 주어진다.

각 테스트 케이스는 한 줄로 이루어져 있으며, 각 줄에 A와 B가 주어진다. (0 < A, B < 10)

# 출력
 - 각 테스트 케이스마다 A+B를 출력한다.
 
 
~~~java

import java.util.Scanner;

public class baekjoon0005 {

	public static void main(String[] args) {

		Scanner scan = new Scanner(System.in);
		
		int c = scan.nextInt();
		int arr[] = new int[c];
		
		for(int i = 0; i < c; i++) {
			int a = scan.nextInt();
			int b = scan.nextInt();
			
			arr[i] = a+b;

		}
		scan.close();
		
		for(int j : arr) {
			System.out.print(j+", ");
		}
	}

}
~~~