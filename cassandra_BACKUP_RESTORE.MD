## 1) выполняю бэкап
![image](https://github.com/sukhanovgit/otus/assets/102989024/806ec255-068d-43fd-acdc-249001450d18)


## 2) проверяю файлы бэкапа
![image](https://github.com/sukhanovgit/otus/assets/102989024/f7d57ee6-d0f8-430b-a6fc-d7361819db90)

## 3) drop table
![image](https://github.com/sukhanovgit/otus/assets/102989024/b5534edc-3357-48c4-8fad-5ce1c1418587)

## 4) restore from snapshot
![image](https://github.com/sukhanovgit/otus/assets/102989024/7fd4bbfe-5152-4d31-9185-d4045582dff3)

Снапшот восстанавливает только те данные которые были на его ноде. Соответсвенно бэкап нужно запускать на всех нодах кластера самостоятельно. И восстанавливать тоже на каждой ноде по отдельности. С одной стороны очнь не удобно. С другой стороны мы может восстановить именно проблемную Ноду, а не все. 
