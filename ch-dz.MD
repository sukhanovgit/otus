## 1) Установил СН на google cloud Ubuntu Host
   
syhanov1987@instance-1:~$ clickhouse-client 
ClickHouse client version 23.4.2.11 (official build).
Connecting to localhost:9000 as user default.
Password for user (default): 
Connecting to localhost:9000 as user default.

## 2) Выполнил импорт тестовой БД 

![image](https://user-images.githubusercontent.com/102989024/236794983-3b72a582-3211-43eb-a3f9-bd468c87845c.png)

## 3) Выполнил запросы к БД

![image](https://user-images.githubusercontent.com/102989024/236795920-164185e5-f483-4756-89d0-eac2ce2ba425.png)

## 4) Залил examle data set и выполнил оптимизацию 

![image](https://user-images.githubusercontent.com/102989024/236801970-50cda8c8-329a-4e1d-abf9-b722a7aebbe4.png)
![image](https://user-images.githubusercontent.com/102989024/236802310-10a965ab-102d-4ac0-8aba-bd971f91950e.png)
выполнил запрос чтобы оценить скорость выполнения 
![image](https://user-images.githubusercontent.com/102989024/236802756-87785fd9-8577-4816-bb59-2aa3312f320d.png)
