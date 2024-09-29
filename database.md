tentti excercises 2 (viikko 3):
1.select * from goal;
2.select name from airport where iso_country = "FI";
3.select name from airport where iso_country="FI" order by name;
4.select name, type from airport where iso_country="FI" order by type, name;
5.select name from country where name like "F%";
6.select name from country where name like "%F%";
7.select location from game where screen_name= "Vesa";
8.select co2_consumed from game where screen_name="Ilkka";
9.select co2_budget from game where screen_name="Heini";
10.select co2_consumed,co2_budget,screen_name,@co2_left:="2000" as co2_left from game where screen_name="Ilkka";

1.<img width="1440" alt="database screenshot 1" src="https://github.com/user-attachments/assets/db85c092-dbd0-4f7c-92ca-2b3ff6e1f8ad">
2.<img width="1440" alt="database screenshot 2 " src="https://github.com/user-attachments/assets/1097f30e-ee80-4070-ad24-61150ef6c574">
3.<img width="1440" alt="database screenshot 3 " src="https://github.com/user-attachments/assets/a392f06d-33a8-4606-9966-592072448f8c">
4.<img width="1440" alt="database screenshot 4 " src="https://github.com/user-attachments/assets/bf2b1931-baa1-4e13-9e09-578c24b68612">
5.<img width="1440" alt="database screenshot 5" src="https://github.com/user-attachments/assets/53bcd1a9-5f87-466b-9f56-5ab5dd838427">
6.<img width="1440" alt="database screenshot 6" src="https://github.com/user-attachments/assets/6965d2b4-5904-4945-abcb-625137e31267">
7.<img width="1440" alt="database screenshot 7" src="https://github.com/user-attachments/assets/4e7a8253-3d8b-4ee9-b71f-2675bdb24875">
8.<img width="1440" alt="database screenshot 8" src="https://github.com/user-attachments/assets/ea616210-f1b0-4b28-b63c-e19921568ae9">
9.<img width="1440" alt="database screenshot 9" src="https://github.com/user-attachments/assets/26512990-ce93-45d4-8f26-d5c8f7faf690">
10.<img width="1440" alt="database screenshot 10" src="https://github.com/user-attachments/assets/743b43df-8569-4047-9bf3-71f6dc9cbeec">
excercises 4:join
1. select country.name as "country name", airport.name as "airport name" from airport inner join country on country.iso_country=airport.iso_country where airport.iso_country = "FI" and airport.scheduled_service="yes";
2.select screen_name, name from game inner join airport on airport.ident=game.location;
3.select game.screen_name,country.name from game inner join airport on airport.ident=game.location inner join country on country.iso_country=airport.iso_country;
4.select airport.name,game.screen_name from airport left join game on game.location=airport.ident where name like "%hels%";
5.select goal.name,game.screen_name from goal left join goal_reached on goal_reached.goal_id=goal.id left join game on game.id=goal_reached.game_id;
1. <img width="1440" alt="Screenshot 2024-09-29 at 16 18 03" src="https://github.com/user-attachments/assets/cb768e36-1d02-4712-9387-5dc666db764a">
2. <img width="1440" alt="Screenshot 2024-09-29 at 16 18 48" src="https://github.com/user-attachments/assets/bc3a9c1f-00b3-4bfe-9580-bed71f286c6e">
3. <img width="1440" alt="Screenshot 2024-09-29 at 16 19 14" src="https://github.com/user-attachments/assets/abfcca70-e4ec-4b98-a296-d0ff905adac3">
4. <img width="1440" alt="Screenshot 2024-09-29 at 16 19 37" src="https://github.com/user-attachments/assets/e25e9090-9c9c-4bf0-a11d-db7c321d24d5">
5. <img width="1440" alt="Screenshot 2024-09-29 at 16 20 57" src="https://github.com/user-attachments/assets/c73dcc40-543a-4093-81a8-413e42e4f59b">

