# 기본부터 하기 위한 백준 자바 천천히 풀어나가기
--------------------------------------------

# 문제
 - N을 입력받은 뒤, 구구단 N단을 출력하는 프로그램을 작성하시오. 출력 형식에 맞춰서 출력하면 된다.
 
# 입력
 첫째 줄에 N이 주어진다. N은 1보다 크거나 같고, 9보다 작거나 같다.
 
# 출력
 - 출력형식과 같게 N*1부터 N*9까지 출력한다.
 
 
~~~java

import java.util.Scanner;

public class baekjoon0003 {

	public static void main(String[] args) {
		
		Scanner scan = new Scanner(System.in);
		
		int n = scan.nextInt();
		
		scan.close();
		
		for(int i=1; i<10; i++) {
			System.out.println(n+"X"+i+"="+(n*i));
		}
	}

}
~~~