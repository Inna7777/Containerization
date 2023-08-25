### Запускаем контейнер с именем "some-mysql" на базе образа MySQL версии 8.0.31, устанавливаем переменную окружения MYSQL_ROOT_PASSWORD со значением "my-secret-pw", и запускает контейнер в фоновом режиме (-d)
* docker run --name some-mysql -e MYSQL_ROOT_PASSWORD=my-secret-pw -d mysql:8.0.31
###  Запускаем контейнер с именем "myphp" на базе образа phpMyAdmin, который будет связан с контейнером "some-mysql" через ссылку на базу данных "db". Контейнер  доступен по порту 8081 на хостовой машине (-p 8081:80)
![Alt text](<docker_container.jpg>)
### Результат:
![Alt text](<docker_container2.jpg>)

### Создаем новую директорию
* mkdir my_new_directory
![Alt text](<new_dir.jpg>)

### Docker-compose
### Создаем файл yml.
* nano docker_comp.yml  
version: ‘3.9’  
services:
  db:
    image: mariadb:10.10.2   
    restart: always  
    environment:  
      MYSQL_ROOT_PASSWORD: 12345
  adminer:  
    image: adminer:4.8.1  
    restart: always  
    ports:  
      - "6080:8080"
* сохраняем файл и запускаем контейнер
* docker-compose -f docker_comp.yml up
![Alt text](<docker-compose1.jpg>)
![Alt text](<docker-compose2.jpg>)
### Результат:
![Alt text](<db.jpg>)
![Alt text](<db_open.jpg>)

### Удаляем все контейнеры
* docker rm $(docker ps -aq) --force
### Удаляем все образы
* docker rmi $(docker images -q) --force

