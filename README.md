# databases
week 3

exercises 2

#1
<img width="416" alt="image" src="https://github.com/user-attachments/assets/aeb67c71-9e1c-4a22-b0fa-4a716543657f">

#2
<img width="416" alt="image" src="https://github.com/user-attachments/assets/d0737c32-49ca-4fb9-a6cb-53f530bc8342">

#3
<img width="415" alt="image" src="https://github.com/user-attachments/assets/b79b56d4-e239-46f2-acce-1a8e14fffdb5">

#4
<img width="416" alt="image" src="https://github.com/user-attachments/assets/f8e13b8d-d8fd-4c4a-9ea8-c7937fe550cc">

#5
<img width="416" alt="image" src="https://github.com/user-attachments/assets/c79f4ab2-21c8-4ac2-9001-7d72a334b4ae">

#6#7#8#9
<img width="415" alt="image" src="https://github.com/user-attachments/assets/1025e189-4fd4-4631-b2a8-cb4ae93fbac8">


week 3

exercise 3

#1
<img width="416" alt="image" src="https://github.com/user-attachments/assets/a0e346ee-b32d-4596-857c-a6b7f114acf5">

#2
<img width="416" alt="image" src="https://github.com/user-attachments/assets/f023a91c-7194-4feb-98ff-14865c0f75d8">

#3
<img width="416" alt="image" src="https://github.com/user-attachments/assets/29f13f93-4f96-4cb8-a87a-26e912694d20">

#4
<img width="416" alt="image" src="https://github.com/user-attachments/assets/847c2fa7-175c-45f0-8c42-0ee21aa608b3">

#5
<img width="416" alt="image" src="https://github.com/user-attachments/assets/7183a95c-c484-47f6-952b-cec735a41efc">

#6
<img width="416" alt="image" src="https://github.com/user-attachments/assets/61ac187c-5c90-4ad5-ad55-1d1abb702028">

#7
<img width="416" alt="image" src="https://github.com/user-attachments/assets/0dfff475-a9f4-42bf-90dd-b56bf92390a4">

#8
<img width="416" alt="image" src="https://github.com/user-attachments/assets/9a36ec0d-1209-47a7-a95b-f59bada3bbd6">

#9
<img width="416" alt="image" src="https://github.com/user-attachments/assets/5daa7c18-b354-4406-8216-886bc8d10109">

#10
<img width="416" alt="image" src="https://github.com/user-attachments/assets/47f5d9eb-2237-426b-99c0-e63eac240809">

weeek 4

exercises 4

#1
select country.name as "country name", airport.name as "airport name" 
from country inner join airport on airport.iso_country = country.iso_country
where country.name = "Finland" and scheduled_service = "yes";

<img width="1020" alt="Screenshot 2024-10-01 at 11 11 32" src="https://github.com/user-attachments/assets/185bfbbd-ca45-4f77-8849-e9105ba658d9">

#2
select screen_name, airport.name from game inner join airport on location = ident;

<img width="1194" alt="Screenshot 2024-10-01 at 11 13 34" src="https://github.com/user-attachments/assets/b3cf784f-ada7-43be-840c-311f42c64ecf">


#3
select screen_name, country.name
from game inner join airport on location = ident inner join country on airport.iso_country = country.iso_country;

<img width="1333" alt="Screenshot 2024-10-01 at 11 15 29" src="https://github.com/user-attachments/assets/79c4bb2b-efc0-4795-a5ec-2e938e9a8af0">


#4
select airport.name, screen_name from airport left join game on ident = location where name like "%Hels%";
<img width="1317" alt="Screenshot 2024-10-01 at 11 16 52" src="https://github.com/user-attachments/assets/5fdf46c8-65b0-4390-894a-01e7c7d8a391">



#5
select name, screen_name from goal left join goal_reached on goal.id = goal_id  left join game on game.id = game_id;

<img width="1321" alt="Screenshot 2024-10-01 at 11 17 38" src="https://github.com/user-attachments/assets/c6bf313a-2452-4de5-a3b8-9e4b81cc9f0e">


week 4

exercises 5

#1

select name from country where iso_country in(select iso_country from airport where name like "Satsuma%");
<img width="1324" alt="Screenshot 2024-10-01 at 11 19 10" src="https://github.com/user-attachments/assets/1c352502-d636-46fe-b64c-f09d0bfa5625">

#2
select name from airport where iso_country in(select iso_country from country where name = "Monaco");
<img width="1327" alt="Screenshot 2024-10-01 at 11 19 52" src="https://github.com/user-attachments/assets/d23dfe0f-e7ba-403d-834a-9c88dd4ae344">



#3
select screen_name from game where id in (select game_id
from goal_reached where goal_id in(select id from goal where name = "CLOUDS"));
<img width="988" alt="Screenshot 2024-10-01 at 11 20 22" src="https://github.com/user-attachments/assets/2ec6078f-b47e-40f3-9257-5c6e664083bd">

#4
select country.name from country where iso_country not in (select airport.iso_country from airport);
<img width="1322" alt="Screenshot 2024-10-01 at 11 21 05" src="https://github.com/user-attachments/assets/992708f0-5dbd-42c0-8320-acc30287b487">

#5
select name from goal where id not in(select goal.id from goal, goal_reached, game
where game.id = game_id and goal.id = goal_id and screen_name = "Heini");

<img width="1183" alt="Screenshot 2024-10-01 at 11 21 41" src="https://github.com/user-attachments/assets/56a7ecdc-83bf-43a6-8759-145ea5ac8f85">


