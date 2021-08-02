# 기본부터 하기 위한 백준 자바 천천히 풀어나가기
--------------------------------------------

# 문제
 - N개의 정수가 주어진다. 이때, 최솟값과 최댓값을 구하는 프로그램을 작성하시오.
 
# 입력
 첫째 줄에 정수의 개수 N (1 ≤ N ≤ 1,000,000)이 주어진다. 둘째 줄에는 N개의 정수를 공백으로 구분해서 주어진다. 모든 정수는 -1,000,000보다 크거나 같고, 1,000,000보다 작거나 같은 정수이다.

# 출력
 - 첫째 줄에 주어진 정수 N개의 최솟값과 최댓값을 공백으로 구분해 출력한다.
 
 
~~~java

import java.util.Arrays;
import java.util.Scanner;

public class baekjoon0009 {

	public static void main(String[] args) {

		Scanner scan = new Scanner(System.in);

		int a = scan.nextInt();
		int[] array = new int[a]; // 배열의 갯수를 정해준다.

		for (int i = 0; i < a; i++) {
			array[i] = scan.nextInt(); // 배열에 입력받은 값을 넣어준다.
		}

		scan.close();
		Arrays.sort(array);
		System.out.println("최소값 : " + array[0] + "\n최대값 : " + array[a - 1]);

	}

}
~~~