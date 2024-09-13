# Investment-Project

This is a personal project focused on investments. I took two datasets and using SQL:
Here I will find the companies that have been invested in for each sector inside the USA. I Will inner join both table to show the companies investested for a certain deptarment or category within a state. 

select * from tutorial.crunchbase_investments
select * from tutorial.crunchbase_companies

select  
  i.company_name, 
  d.funding_total_usd,
  d.status,
  i.company_country_code,
  i.funded_at, 
  i.company_category_code, 
  i.company_state_code, 
  i.investor_name,
  i.investor_category_code,
  d.founded_at,
  a.price_amount
from tutorial.crunchbase_investments as i
  inner join tutorial.crunchbase_companies_clean_date as d
  ON i.company_permalink = d.permalink
  inner join tutorial.crunchbase_acquisitions as a
  on d.permalink = a.company_permalink
  where country_code = 'USA'
;

Next I will use analytics and a data vizulization tool that is found here https://public.tableau.com/app/profile/robel.h2839/viz/InvestmentDashboard_17206636297300/Dashboard3. 
The final results are found above. 
