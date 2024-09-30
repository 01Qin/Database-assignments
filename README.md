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

#2
select screen_name, airport.name from game inner join airport on location = ident;

![image](https://github.com/user-attachments/assets/42ee9c50-a3e6-4875-80d9-50ff1e748812)

#3
select screen_name, country.name
from game inner join airport on location = ident inner join country on airport.iso_country = country.iso_country;

![image](https://github.com/user-attachments/assets/cff522ce-5f8c-44e5-b0ca-2f9f0e941d4f)

#4
select airport.name, screen_name from airport left join game on ident = location where name like "%Hels%";

![image](https://github.com/user-attachments/assets/5e5d7bbd-fcb7-40d6-9a0b-91d6ca6d9f33)

#5
select name, screen_name from goal left join goal_reached on goal.id = goal_id  left join game on game.id = game_id;

![image](https://github.com/user-attachments/assets/fb45083b-5e43-4cdc-98ff-a2d70158339e)

week 4

exercises 5

#1

select name from country where iso_country in(select iso_country from airport where name like "Satsuma%");

![image](https://github.com/user-attachments/assets/06e94733-748f-4557-b9cb-c56c73366d6d)

#2
select name from airport where iso_country in(select iso_country from country where name = "Monaco");

![image](https://github.com/user-attachments/assets/618063c5-94d3-4117-ae4f-25b9a5f39485)

#3
select screen_name from game where id in (select game_id
from goal_reached where goal_id in(select id from goal where name = "CLOUDS"));

![image](https://github.com/user-attachments/assets/17649e1b-27a4-4825-95fe-bf171e17b39c)

#4
select country.name from country where iso_country not in (select airport.iso_country from airport);

![image](https://github.com/user-attachments/assets/60f748e6-d73c-4ff0-a8cd-dcd4196f23b8)

#5
select name from goal where id not in(select goal.id from goal, goal_reached, game
where game.id = game_id and goal.id = goal_id and screen_name = "Heini");

![image](https://github.com/user-attachments/assets/23ed5086-f4ee-4cce-89a2-5fb11e138fbe)

