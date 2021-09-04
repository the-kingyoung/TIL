# 기본부터 하기 위한 백준 자바 천천히 풀어나가기
--------------------------------------------

# 문제
 - 정수 X에 사용할 수 있는 연산은 다음과 같이 세 가지 이다.

X가 3으로 나누어 떨어지면, 3으로 나눈다.
X가 2로 나누어 떨어지면, 2로 나눈다.
1을 뺀다.
정수 N이 주어졌을 때, 위와 같은 연산 세 개를 적절히 사용해서 1을 만들려고 한다. 연산을 사용하는 횟수의 최솟값을 출력하시오.
 
# 입력
 - 첫째 줄에 1보다 크거나 같고, 106보다 작거나 같은 정수 N이 주어진다.
 
# 출력
 - 첫째 줄에 연산을 하는 횟수의 최솟값을 출력한다. //휴가
 
 
 
~~~java

import java.util.Scanner;

public class baekjoon0024 {
	
	static Integer[] kk;
	
	public static void main(String[] args) {

		Scanner scan = new Scanner(System.in);

		int N = scan.nextInt();
		
		kk = new Integer[N+1];
		kk[0] = kk[1] = 0;
		
		System.out.println(accu(N));

	}
	
	static int accu(int N) {
		if(kk[N] == null) {
			if(N%6 == 0) {
				kk[N] = Math.min(accu(N-1), Math.min(accu(N/3), accu(N/2)))+1;
			}
			
			else if(N%3 == 0) {
				kk[N] = Math.min(accu(N/3), accu(N-1)) +1;
			}
			else if(N%2 == 0) {
				kk[N] = Math.min(accu(N/2), accu(N-1))+1;
			}
			else {
				kk[N] = accu(N-1)+1;
			}
		}
		return kk[N];
	}
}
~~~