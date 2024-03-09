# 1t-DE-4.4-BigData
Задание на курсах 1t "Инженер данных". 4.4 Введение в Hadoop

Задание
Что может быть прекраснее летнего корпоратива? Особенно если корпоратив пройдет в Таиланде! Да-да, отчетный период показал очень хорошую прибыль вашей компании — и не без вашего участия! Чтобы поощрить за труд и терпение, ваш начальник решил организовать корпоратив прямо на островах. По приезду на место первое, что попало на глаза вам и вашим коллегам, — это цирковое шоу слонов. Зрелище было замечательным, у вас возникла невольная ассоциация и вы воскликнули: «О, оживший Hadoop!». Что же, инициатива, как говорится, ложится на плечи инициатора. Теперь ваш начальник под двойным впечатлением поставил вам первоочередную задачу после отпуска — завести hadoop для задач вашей компании. 
Беремся за дело — и уже по традиции ищем нужный образ docker. Находим его здесь:  GitHub - tech4242/docker-hadoop-hive-parquet: Hadoop, Hive, Parquet and Hue in docker-compose v3.
Устанавливается он весьма просто:
1.	git clone  GitHub - tech4242/docker-hadoop-hive-parquet: Hadoop, Hive, Parquet and Hue in docker-compose v3 (в заранее созданной папке)
2.	cmd → docker-compose up
Отлично, как только образ собран, а контейнер поднят — заходим по http://localhost:8888/hue и попадаем в HUE. Придумываем произвольную пару логина-пароля для будущей авторизации и приступаем к работе. 
В интерфейсе hue пока для нас мало интересного, переходим в раздел «files» и наблюдаем примерно такую картину:
 
Это ваша личная папка в файловой системе hadoop(hdfs), и сейчас мы будем учиться с ней работать!
•	На время забываем про hue и вспоминаем уроки литературы — переходим на следующий ресурс и скачиваем все доступные тома произведения «Война и мир» Л.Н. Толстого:  Лев Николаевич Толстой - Информация об авторе, биография, дата и место рождения, род деятельности, награды и премии, годы творчества.
•	Далее подключаемся к контейнеру «datanode-1», создаем внутри папку и переносим в нее скачанные файлы.
•	Файлы предварительно «схлопываем» в один.
•	Загружаем полученный файл на hdfs в вашу личную папку.
•	Если все пройдет удачно, то по возвращению в hue вас ждет сюрприз: вы увидите полное произведение «Война и мир» на hdfs (не забудьте обновить страницу). На самом деле интерфейс HUE поддерживает возможность переноса небольших(!) файлов с помощью drag&drop — но для нас это слишком просто.
•	Возвращаемся в терминал и продолжаем изучать hdfs — попробуйте выполнить команду, которая
выводит содержимое вашей личной папки. Обратите внимание на права доступа к вашим
файлам — их явно недостаточно, если вы решите поделиться столь важной книгой с вашим коллегой — давайте изменим права доступа к нашему файлу. Установите режим доступа, который дает полный доступ для владельца файла, а для сторонних пользователей возможность читать и выполнять.
•	Попробуйте заново использовать команду для вывода содержимого папки и обратите
внимание как изменились права доступа к файлу.
•	Теперь попробуем вывести на экран информацию о том, сколько места на диске
занимает наш файл. Желательно, чтобы размер файла был удобочитаемым.
•	На экране вы можете заметить 2 числа. Первое число — это фактический размер файла,
а второе — это занимаемое файлом место на диске с учетом репликации — измените фактор репликации на 2.
•	Повторите команду, которая выводит информацию о том, какое место на диске
занимает файл и убедитесь, что изменения произошли.
•	И финальное — напишите команду, которая подсчитывает количество строк в произведении «Война и мир».
В качестве результатов вашей работы запишите ваши команды и вывод этих команд в отдельный файл.
Результат выполнения задания необходимо выложить в github/gitlab и указать ссылку на Ваш репозиторий (не забудьте: репозиторий должен быть публичным).

