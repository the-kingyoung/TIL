# SQL에서 행을 열로 바꾸는 방법

 - 방법 1
	select
	  extract(year from order_date) "year",
	  case when extract(month from order_date) =  1 then order_amt end as "Jan",
	  case when extract(month from order_date) =  2 then order_amt end as "Feb",
	  case when extract(month from order_date) =  3 then order_amt end as "Mar",
	  case when extract(month from order_date) =  4 then order_amt end as "Apr",
	  case when extract(month from order_date) =  5 then order_amt end as "May",
	  case when extract(month from order_date) =  6 then order_amt end as "Jun",
	  case when extract(month from order_date) =  7 then order_amt end as "Jul",
	  case when extract(month from order_date) =  8 then order_amt end as "Aug",
	  case when extract(month from order_date) =  9 then order_amt end as "Sep",
	  case when extract(month from order_date) = 10 then order_amt end as "Oct",
	  case when extract(month from order_date) = 11 then order_amt end as "Nov",
	  case when extract(month from order_date) = 12 then order_amt end as "Dec"
	from orders	
	
 - 방법 2
 	select
	  "year",
	  case when mm =  1 then order_amt end as "Jan",
	  case when mm =  2 then order_amt end as "Feb",
	  case when mm =  3 then order_amt end as "Mar",
	  case when mm =  4 then order_amt end as "Apr",
	  case when mm =  5 then order_amt end as "May",
	  case when mm =  6 then order_amt end as "Jun",
	  case when mm =  7 then order_amt end as "Jul",
	  case when mm =  8 then order_amt end as "Aug",
	  case when mm =  9 then order_amt end as "Sep",
	  case when mm = 10 then order_amt end as "Oct",
	  case when mm = 11 then order_amt end as "Nov",
	  case when mm = 12 then order_amt end as "Dec"
	from (select extract(year from order_date) "year",
	             extract(month from order_date) as mm, order_amt
	      from orders
	      where order_date between '2013-01-01' and '2014-12-31') as t;
	      
	      