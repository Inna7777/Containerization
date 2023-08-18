### Запустите контейнер с использованием образа "cowsay".
* docker run docker/whalesay cowsay Hello, Docker!
![Alt text](<docker1.jpg>)

### Запустить контейнер с рисунком дракона:
* docker run docker/whalesay cowsay -f tux "Hello, Docker!"
![Alt text](<docker2.jpg>)

### Просмотр созданных контейнеров
* docker ps -a
![Alt text](<docker3.jpg>)

### Удаление контейнера 
* docker rm 
![Alt text](<docker4.jpg>)

### Отображение всех образов
* docker images
![Alt text](<do.jpg>)

### Запускаем контейнер Docker с образом Ubuntu версии 22.10.
* docker run -it -h GB --name gb-test ubuntu:22.10
* "gb-test" -задаем ему имя 
* -it  запускает контейнер в интерактивном режиме Опция * -h  имя хоста в контейнере .
![Alt text](<docker6.jpg>)

### Создаем директорию в контейнере
![Alt text](<docker8.jpg>)
### Создаем файл в созданной дирректориию
![Alt text](<docker10.jpg>)
### Вносим запись в файл
![Alt text](<docker11.jpg>)

### Выходим из контейнера, останавливает, запускаем , входи снова, удаляем.
![Alt text](<docker12.jpg>)

### Удалим контейнер и создадим его заново, используя те же команды:
* docker stop gb-test
* docker rm gb-test
* docker run -it -h GB --name gb-test ubuntu:22.10
![Alt text](<docker13.jpg>)


### Создадим на хосте новую дирректорию c файлом test.txt
* mkdir myfile/folder
* и подмонтировали ее в контейнер
* затем добавили данные в подмантированную директорию echo "$HOSTNAME" >> /home/test.txt
![Alt text](<docker7.jpg>)
* изменения видны на хостовой машине
![Alt text](<docker14.jpg>)

### Cоздали контейнер и монтировали папку docker-mount-example внутрь контейнера. Затем мы монтировали файл test.txt из домашней директории внутрь этой папки в контейнере. При просмотре содержимого файла в контейнере, вы увидите данные из файла в домашней директории.
![Alt text](<docker16.jpg>)