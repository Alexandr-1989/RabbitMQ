Задание 1. Установка RabbitMQ  
  
Используя Vagrant или VirtualBox, создайте виртуальную машину и установите RabbitMQ.  
Добавьте management plug-in и зайдите в веб-интерфейс.  
Итогом выполнения домашнего задания будет приложенный скриншот веб-интерфейса RabbitMQ.  
Ответ:  
<img width="1720" height="738" alt="Screenshot_1" src="https://github.com/user-attachments/assets/d7d1f806-0348-4fb0-9f93-33c526fdc0fb" />

  
Задание 2. Отправка и получение сообщений  
  
Используя приложенные скрипты, проведите тестовую отправку и получение сообщения.  
Для отправки сообщений необходимо запустить скрипт producer.py.  
Для работы скриптов вам необходимо установить Python версии 3 и библиотеку Pika.  
Также в скриптах нужно указать IP-адрес машины, на которой запущен RabbitMQ, заменив localhost на нужный IP.  
  
$ pip install pika  
  
   
Зайдите в веб-интерфейс, найдите очередь под названием hello и сделайте скриншот.  
После чего запустите второй скрипт consumer.py и сделайте скриншот результата выполнения скрипта  
В качестве решения домашнего задания приложите оба скриншота, сделанных на этапе выполнения.  
Для закрепления материала можете попробовать модифицировать скрипты, чтобы поменять название очереди и отправляемое сообщение.  
Ответ:  
Отправка:  
  <img width="2022" height="913" alt="Screenshot_3" src="https://github.com/user-attachments/assets/dce22f7f-83d8-4855-b202-dd145c7f71a7" />
Получение:  
  
<img width="1026" height="454" alt="Screenshot_5" src="https://github.com/user-attachments/assets/f5dc5373-1eaf-4c18-84ba-46c3a3457f41" />
Задание 3. Подготовка HA кластера  
Используя Vagrant или VirtualBox, создайте вторую виртуальную машину и установите RabbitMQ. Добавьте в файл hosts название и IP-адрес каждой машины, чтобы машины могли видеть друг друга по имени.  
  
Пример содержимого hosts файла:  
  
$ cat /etc/hosts  
192.168.0.10 rmq01  
192.168.0.11 rmq02  
После этого ваши машины могут пинговаться по имени.  
  
Затем объедините две машины в кластер и создайте политику ha-all на все очереди.  
  
В качестве решения домашнего задания приложите скриншоты из веб-интерфейса с информацией о доступных нодах в кластере и включённой политикой.  
  
Также приложите вывод команды с двух нод:  
  
$ rabbitmqctl cluster_status  
Для закрепления материала снова запустите скрипт producer.py и приложите скриншот выполнения команды на каждой из нод:  
  
$ rabbitmqadmin get queue='hello'  
После чего попробуйте отключить одну из нод, желательно ту, к которой подключались из скрипта, затем поправьте параметры подключения в скрипте consumer.py на вторую ноду и запустите его.  
  
Ответ:    
<img width="1074" height="467" alt="Screenshot_6" src="https://github.com/user-attachments/assets/7c999a4d-7c56-4625-a52e-58ffe7d0d6db" />  
  
Делаем политику через вкладку admin-politicies  
<img width="1241" height="483" alt="Screenshot_7" src="https://github.com/user-attachments/assets/76e1285b-be33-46bd-b7f7-b05e3d07c7fd" />  
<img width="957" height="973" alt="Screenshot_9" src="https://github.com/user-attachments/assets/e6d28f30-24e9-4a43-ac81-5754c7a16f99" />  
<img width="790" height="935" alt="Screenshot_10" src="https://github.com/user-attachments/assets/5c0c0c28-1e12-485b-8740-17c0e2507609" />  
  
Запускаем скрипт producer.py  
<img width="918" height="113" alt="Screenshot_11" src="https://github.com/user-attachments/assets/a9baddf9-31f9-4e36-a76e-55ed48ea1cc5" />
<img width="1203" height="136" alt="Screenshot_12" src="https://github.com/user-attachments/assets/a85f50db-fbf0-45af-a496-06b14ab0ccbe" />

Отключаем одну ноду   
<img width="1079" height="434" alt="Screenshot_13" src="https://github.com/user-attachments/assets/a2bfa50f-79e3-4a7c-8c2a-1167056c0d9a" />
<img width="592" height="97" alt="Screenshot_14" src="https://github.com/user-attachments/assets/c7bc0f31-f19a-4113-90c6-c743b1c452c8" />



