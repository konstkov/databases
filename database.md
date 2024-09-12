select * from goal;
select name from airport where iso_country = "FI";
select name from airport where iso_country="FI" order by name;
select name, type from airport where iso_country="FI" order by type, name;
select name from country where name like "F%";
select name from country where name like "%F%";
select location from game where screen_name= "Vesa";
select co2_consumed from game where screen_name="Ilkka";
select co2_budget from game where screen_name="Heini";
select co2_consumed,co2_budget,screen_name,@co2_left:="2000" as co2_left from game where screen_name="Ilkka";

<img width="1440" alt="database screenshot 1" src="https://github.com/user-attachments/assets/db85c092-dbd0-4f7c-92ca-2b3ff6e1f8ad">
<img width="1440" alt="database screenshot 2 " src="https://github.com/user-attachments/assets/1097f30e-ee80-4070-ad24-61150ef6c574">
<img width="1440" alt="database screenshot 3 " src="https://github.com/user-attachments/assets/a392f06d-33a8-4606-9966-592072448f8c">
<img width="1440" alt="database screenshot 4 " src="https://github.com/user-attachments/assets/bf2b1931-baa1-4e13-9e09-578c24b68612">
<img width="1440" alt="database screenshot 5" src="https://github.com/user-attachments/assets/53bcd1a9-5f87-466b-9f56-5ab5dd838427">
<img width="1440" alt="database screenshot 6" src="https://github.com/user-attachments/assets/6965d2b4-5904-4945-abcb-625137e31267">
<img width="1440" alt="database screenshot 7" src="https://github.com/user-attachments/assets/4e7a8253-3d8b-4ee9-b71f-2675bdb24875">
<img width="1440" alt="database screenshot 8" src="https://github.com/user-attachments/assets/ea616210-f1b0-4b28-b63c-e19921568ae9">
<img width="1440" alt="database screenshot 9" src="https://github.com/user-attachments/assets/26512990-ce93-45d4-8f26-d5c8f7faf690">
<img width="1440" alt="database screenshot 10" src="https://github.com/user-attachments/assets/743b43df-8569-4047-9bf3-71f6dc9cbeec">
