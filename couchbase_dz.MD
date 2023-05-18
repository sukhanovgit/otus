## 1) Развернул кластер на 2х хостах 
![image](https://github.com/sukhanovgit/otus/assets/102989024/97869246-8a56-457f-ade5-d7b1aaa21914)

## 2) Залил сэмпл данных
![image](https://github.com/sukhanovgit/otus/assets/102989024/ccab738d-3863-4a77-b69e-b7b8dc01f906)

## 3) Проверям отказоустойчивость
# запрос данных
![image](https://github.com/sukhanovgit/otus/assets/102989024/012bb472-81a0-4a9e-8b2c-3a68c904e246)
# выключаю сеть на первой ноде
![image](https://github.com/sukhanovgit/otus/assets/102989024/e37ee784-8f9c-407d-8860-b78f907626f3)
# запрос перестал работать
![image](https://github.com/sukhanovgit/otus/assets/102989024/4f479fb7-899a-4ac1-84ce-46dada60ff8d)
так как мы потеряли индексы которые были на первой ноде
![image](https://github.com/sukhanovgit/otus/assets/102989024/4d1f6b00-f4da-47ef-b604-c1ce45a8d5cc)
вернул сеть на ноду, всё заработало. недоступность была из-за того что минимально нужно 3 ноды в кластере
![image](https://github.com/sukhanovgit/otus/assets/102989024/f9273527-2955-4aec-946b-952867120562)



