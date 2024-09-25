Step 1:
SELECT *
FROM crime_scene_report
WHERE type = "murder"
	AND date = "20180115"
	AND city = "SQL City";

Step 2:
SELECT *
FROM person
WHERE address_street_name = "Northwestern Dr"
ORDER BY address_number DESC limit 50;

Step 3:
SELECT *
FROM person
WHERE name LIKE '%Annabel%'
AND address_street_name = "Franklin Ave";

Step 4:
SELECT *
FROM interview
WHERE person_id IN ("14887", "16371");

Step 5:
SELECT *
FROM get_fit_now_check_in
WHERE membership_id LIKE '48Z%'
AND check_in_date = "20180109";

Step 6:
SELECT *
FROM drivers_license
WHERE gender = "male"
AND plate_number LIKE '%H42W%';

Step 7:
SELECT *
FROM person
WHERE license_id IN ("423327", "664760");

Step 8:
SELECT *
FROM get_fit_now_member
WHERE person_id IN ("51739", "67318");

Step 9:
INSERT INTO solution VALUES (1, 'Jeremy Bowers'); 
SELECT value FROM solution;

![image](https://github.com/user-attachments/assets/827c7d20-9d8d-4775-ad1c-d216eb0f1dd5)

Step 10:
SELECT *
FROM interview
WHERE person_id = "67318";

Step 11:
SELECT *
FROM drivers_license
WHERE gender = "female"
	AND hair_color = "red"
	AND height BETWEEN 65 AND 67
	AND car_make = "Tesla"
	AND car_model = "Model S";

Step 12:
SELECT *
FROM person
WHERE license_id IN ("202298", "291182", "918773");

Step 13:
SELECT 
	person_id, 
    event_name, 
    COUNT(*) AS event_count
FROM facebook_event_checkin
WHERE person_id IN ("78881", "90700", "99716")
GROUP BY person_id, event_name;

Step 14:
INSERT INTO solution VALUES (1, 'Miranda Priestly');
SELECT value FROM solution;

![image](https://github.com/user-attachments/assets/e45b671c-f395-4d59-9978-9c3d73369bf6)

