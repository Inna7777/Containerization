# Создаем контейнер.
* команда: lxc-create -t ubuntu -n my-container
* ![Alt text](<container1.jpg>)

# Открываем конфигурационный файл и вносим ограничение на ОЗУ =256M
* команда: nano /var/lib/lxc/my-container/config
* ![Alt text](<container2.jpg>)

# Проверяем, что ограничение работает.
1. команда останавливаем контейнер, чтобы ограничения вступили в силу: lxc-stop -n my-container.
2. команда запускает контейнер : lxc- start -n my-container
3. команда входа внутрь контейнера:
 lxc-attach -n my-container
 4. команда просмотра сколько ОЗУ может использовать контейнер:
 free -m
* ![Alt text](<container3.jpg>)