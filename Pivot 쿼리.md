# About Pivot query

	SELECT
		*
	FROM
	PIVOT(그룹함수(집계 컬럼) FOR 피벗대상컬럼 IN ([피벗컬럼값]...)) AS pivot_result

 - 그룹함수는 SUM(), COUNT, AVG() 등을 사용할 수 있다.
 - 피벗컬럼값은 한번 지정하면 데이터가 존재하지 않아도 고정적으로 출력된다.
 
	
