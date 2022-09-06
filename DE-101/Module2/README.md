# HOMEWORK_02
### 02_01_SQL training
select
extract('year'from o.order_date),  
count(order_id) as number_orders,
sum(sales) as revenue
FROM public.orders o
where category in ('Furniture', 'Technology')
group by extract('year'from o.order_date)
having sum(sales) >5
order by revenue desc 

select 
distinct category,
count(order_id) as number_orders,
sum(sales) as revenue
from orders o
group by distinct category

select
count(*),
count(distinct o.order_id),
sum(sales)
from orders o inner join returns r on o.order_id = r.order_id 

select date_trunc('day',now())
