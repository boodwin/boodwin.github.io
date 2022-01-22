---
layout: post
title: SQL Murder Mystery
category: sql
---

[SQL Murder Mystery](https://mystery.knightlab.com/walkthrough.html)

```sql
SELECT p.name, dl.height, dl.hair_color, dl.car_make, dl.car_model, 
f.event_name, f.date
FROM person p
JOIN drivers_license dl
  ON p.license_id = dl.id
JOIN facebook_event_checkin f
  ON f.person_id = p.id
WHERE dl.car_make like '%Tesla%'
and dl.car_model = 'Model S'
AND dl.hair_color = 'red'
AND dl.gender = 'female'
```
```sql
SELECT p.name, i.transcript
FROM get_fit_now_member gfnm
JOIN person p
  ON p.id = gfnm.person_id
JOIN drivers_license dl
  ON p.license_id = dl.id	
JOIN interview i
  ON p.id =i.person_id
WHERE gfnm.membership_status = 'gold'
AND gfnm.id like '48Z%'
AND dl.plate_number like '%H42W%'
```

