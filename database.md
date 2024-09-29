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
excercises 5:Subqueries
1. select name from country where iso_country in (select iso_country from airport where name like
"%satsuma%");
2. select name from airport where iso_country in (select iso_country from country where name = "Monaco");
3. select screen_name from game where id in (select game_id from goal_reached where goal_id in (select id from goal where name="CLOUDS"));
4. select name from country where iso_country not in (select iso_country from airport);
5. select name from goal where id not in (select goal_id from goal_reached where game_id in(select
 id from game where screen_name="Heini"));
1.<img width="1440" alt="Screenshot 2024-09-29 at 18 16 38" src="https://github.com/user-attachments/assets/49cd24a4-4d7d-4ae3-98d1-af20fd5cb638">
2.<img width="1440" alt="Screenshot 2024-09-29 at 18 16 58" src="https://github.com/user-attachments/assets/53ff8c67-8d93-4e1e-85a5-8f5d7136f988">
3.<img width="1440" alt="Screenshot 2024-09-29 at 18 17 16" src="https://github.com/user-attachments/assets/97b14801-281e-4577-97fc-518d2a29a85c">
4.<img width="1440" alt="Screenshot 2024-09-29 at 18 17 36" src="https://github.com/user-attachments/assets/4d98114d-1461-4da0-9bb9-a4ebb3102044">
5.<img width="1440" alt="Screenshot 2024-09-29 at 18 17 58" src="https://github.com/user-attachments/assets/2bd54afd-eb54-4de6-acfc-bdc019f48feb">
Exercises 6: Aggregate Queries
1. select max(elevation_ft) from airport;
2. select continent,count(*) from country group by continent;
3. select game.screen_name,count(*) from goal_reached,game where goal_reached.game_id
=game.id group by game_id;
4.select screen_name from game where co2_consumed in(select min(co2_consumed) from game);
5.select country.name, count(*) from airport, country where airport.iso_country = country.iso_country group by country.iso_country order by count(*) desc limit 50;
6.select country.name,count(*) from country,airport where country.iso_country=airport.iso_country group by name having count(*) > 1000;
7.select name from airport where elevation_ft in(select max(elevation_ft) from airport);
8.select name from country where iso_country in(select iso_country from airport where elevation_ft in(select max(elevation_ft
) from airport));
9.select count(*) from game,goal_reached where game.screen_name="Vesa" and game.id=goal_reached.game_id;
10.select name from airport where latitude_deg in (select min(latitude_deg) from airport);
   1.<img width="1440" alt="Screenshot 2024-09-29 at 22 37 22" src="https://github.com/user-attachments/assets/bcdef5ab-2070-41f0-99ee-6d9dfc0781de">
   2.<img width="1440" alt="Screenshot 2024-09-29 at 22 37 44" src="https://github.com/user-attachments/assets/d876a6cf-c76c-4745-b226-b698012cdd00">
   3.<img width="1440" alt="Screenshot 2024-09-29 at 22 38 03" src="https://github.com/user-attachments/assets/8b16e4b5-7367-4517-80d9-057baea4f987">
4.<img width="1440" alt="Screenshot 2024-09-29 at 22 38 22" src="https://github.com/user-attachments/assets/376bdd3d-11b0-4ca4-8466-297a6d828c2c">
5.<img width="1440" alt="Screenshot 2024-09-29 at 22 38 47" src="https://github.com/user-attachments/assets/b92ff291-9672-4d7c-ab6f-082edb6e1744">
6.<img width="1440" alt="Screenshot 2024-09-29 at 22 39 11" src="https://github.com/user-attachments/assets/faf4bd53-2c86-499d-a53e-18dc5da800a6">
7.<img width="1440" alt="Screenshot 2024-09-29 at 22 39 32" src="https://github.com/user-attachments/assets/9a40f8c7-b431-4c8b-8133-1855d6be0fdc">
8.<img width="1440" alt="Screenshot 2024-09-29 at 22 39 54" src="https://github.com/user-attachments/assets/e28ab406-1419-4d78-9dd2-0c35db33811c">
9.<img width="1440" alt="Screenshot 2024-09-29 at 22 40 17" src="https://github.com/user-attachments/assets/b57af1fe-f885-40df-b4de-c4f021517dd5">
10.<img width="1440" alt="Screenshot 2024-09-29 at 22 40 48" src="https://github.com/user-attachments/assets/52bea3b7-802e-488c-a357-5468b8cfd3fd">
Exercises 7: Update Queries
1.update game set  location = (select ident from airport where name = "Nottingham Airport"), co2_consumed = co2_consumed+500 where screen_name = "Vesa";
2.goal_reached
3.delete from goal_reached; select * from goal_reached;
4.delete from game; select * from game;
1.<img width="1440" alt="Screenshot 2024-09-29 at 23 02 12" src="https://github.com/user-attachments/assets/a5ff5ecd-64e8-41c9-bb17-543fcaecbc16">
2.<img width="1440" alt="Screenshot 2024-09-29 at 23 01 41" src="https://github.com/user-attachments/assets/db472be2-cf9a-43a8-9eef-3bd287057c6a">




