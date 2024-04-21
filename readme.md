#Установка

открыть содержимое папки 8.1 и запустить команду docker compose up --build -d

соберется и запустится проект.  Его можно будет запустить по адресу

0.0.0.0:8080

а по адресу 0.0.0.0:8092
запускается phpmyadmin.

логин: laravel
пароль: password

для базы данных тоже. 

нужно дать права для папки storage
chmod -R 777 ./src/storage

в настройках phpstorm выбрать
PHPSTORM - phpstorm
host: 192.168.0.100
post: 9003

в Servers прописать хост

192.168.0.100

и настроить mapping на папку src
и src public

при необходимости раздавать права доступа при помощи 
chmod -R 777 ./storage  или вне контейнера для всей папки src

sudo chmod -R 777 ./src

для установки чистого laravel нужно
удалить содержимое src 
подплючиться к php контейнеру и выполнить

composer create-project laravel/laravel .

в .env файле прописать 

DB_CONNECTION=mysql
DB_HOST=db
DB_PORT=3306
DB_DATABASE=laravel
DB_USERNAME=laravel
DB_PASSWORD=password