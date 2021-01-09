çabukk derste çözmeden

```sql
select 
  name,
  car.id as car_id,
  car.model as car_model,
  manufacture.year as manufacture_year,
  array(select as struct p.id, (timestamp_add(p.date, interval 3 hour)) as date from unnest(purchase) as p) as date_modified
from `dsmbootcamp.fatih_altinpinar.semi_structured_hw`
cross join unnest (car) as car
cross join unnest (manufacture) as manufacture on car.id = manufacture.id;
```
