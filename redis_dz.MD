## 1) Установил REDIS7 и настроил Шардированый кластер
![image](https://github.com/sukhanovgit/otus/assets/102989024/5a276d5e-5f88-49e3-b4ae-c9f4ff3ae9d1)
![image](https://github.com/sukhanovgit/otus/assets/102989024/5a205644-38cf-41c6-9fa9-0c18a9a09567)
## 2) При попытке добавить JSON получил ошибку
Ошибка ERR unknown command 'JSON.SET'
##### Решение:
#### 2.1) Скачать Module RedisJSON и распаковать
wget https://github.com/RedisJSON/RedisJSON/archive/refs/tags/v2.4.7.tar.gz
sudo tar xzf v2.4.7.tar.gz
#### 2.2) Установить 
sudo apt-get install -y libclang-dev cargo
#### 2.3) Перейти в распакованную папку и выполнить build
cd RedisJSON-2.4.7/
cargo build --release
#### 2.4) Скопировать готовый модуль в /usr/lib и предоставить на него права доступа
cd target/release/
cp librejson.so /usr/lib
chmod 777 /usr/lib/librejson.so
#### 2.5) добавить в конфиг redis 
vi /etc/redis/redis.conf
значение:
loadmodule /usr/lib/librejson.so
#### 2.6) Перезапустить сервис 
systemctl restart redis.service
## 3) Добавил большой JSON 
![image](https://github.com/sukhanovgit/otus/assets/102989024/da71556f-87ea-4892-b928-738b324e129b)
