# MYSQL-1
Weekly trend analysis
select
-- week(created_at) as wk,
min(date(created_at)) as beg_date_week,
Count(case when device_type='desktop' then website_session_id else null end) as dtop_sessions,
Count(case when device_type='mobile' then website_session_id else null end) as mob_sessions
from website_sessions
where created_at>'2012-04-15'
and created_at<'2012-06-09'
and utm_source='gsearch'
and utm_campaign='nonbrand'
group by week(created_at)
