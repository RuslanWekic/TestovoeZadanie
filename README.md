## Здравствуйте! Меня зовут Ахкамов Руслан, этот репозиторий создан для прохождения собеседования 
Я первый раз заполняю свой репозиторий на GitHub, приношу извинения за ошибки в оформлении и орфографии!

1) Настройка сетевого интерфейса; 

Первым делом проверяем ip адрес в терминале командой ``` ifconfig ```

<img width="925" height="618" alt="Screenshot from 2025-11-03 18-53-46" src="https://github.com/user-attachments/assets/389d9bdf-c611-4051-9677-ef7ead71db95" />

Прописываем статичный ip адрес через настройки Ubuntu, делаем максимально простым способом, заходим в правом верхнем углу в настройки подключений, далее нажимаем на икноку шестерёнки

<img width="639" height="515" alt="Screenshot from 2025-11-04 02-41-51" src="https://github.com/user-attachments/assets/566151e8-50c6-4f1c-8720-c9fe007ac749" />

Проваливаемся в настройки подключения, переходим в пункт IPv4, выбираем режим Manual и прописываем ip адрес, маску, шлюз (в моём случае шлюзом выступает роутер), прописываем DNS (публичный адрес Google)

<img width="910" height="636" alt="Screenshot from 2025-11-04 02-43-53" src="https://github.com/user-attachments/assets/a9c2c6c4-e41b-49a6-ad0c-319f60e52024" />

Проверяем через консоль изменился ли ip адрес, чтобы не писать большую команду используем сокращённую ```ip a```

<img width="910" height="636" alt="Screenshot from 2025-11-04 02-44-20" src="https://github.com/user-attachments/assets/7f4147c0-8f6a-449e-9243-da330b93d4d6" />

Ура! Ip адрес сменился на выбранный, переходим ко второму заданию


##
2) Обновление системы и установка базовых утилит

Обновляем систему до последнего состояния, вводим в терминале команды:

```
sudo apt update

sudo apt upgrade
```

<img width="1738" height="1040" alt="Screenshot from 2025-11-04 02-55-43" src="https://github.com/user-attachments/assets/0fbe2a64-b912-4904-a727-ad94704a2108" />

После обновления и установки всех новых пакетов, переходим к установке утилит которые помогут в будущем при работе

Список устанавливаемых утилит:

Nethogs - отображает сетевой трафик от конкретных приложений.

Traceroute - помогает проверить сетевую доступность конечного узла, позволяет отследить цепочку до маршрутизатора через которые прошёл пакет, удобнее команды ping.

Wine - позволяет открывать приложения Windows, эмилируя среду для приложения. Не все утилиты и приложения могут быть кроссплатформенным.

Unzip - распаковщик архивов формата ZIP

Atop - занимается сбором статистики и наблюдением за системой в реальном времени, благодаря сбору статистики можно просмотреть загруженность процессов на промежутке времени

Git - система контроля версий 

Dhstop - анализатор DNS-траффика, может пригодится при работе с AD

Powertop - утилита для мониторинга потребления мощности разными процессами

Iptables - утилита для управления работой межсетевого экрана, пригодится в дальнейших задачах

Команды установки утилит и скриншоты:
```
sudo apt install nethogs

sudo apt install traceroute
```

<img width="1287" height="659" alt="Screenshot from 2025-11-05 18-02-30" src="https://github.com/user-attachments/assets/9f0033a7-daef-4c09-90f6-729cabfda49a" />

```sudo apt install wine```

<img width="1287" height="89" alt="Screenshot from 2025-11-05 18-03-381" src="https://github.com/user-attachments/assets/f90cf06a-4ea5-4159-a408-1c6c55a5750c" />

```sudo apt install unzip```

<img width="1287" height="264" alt="Screenshot from 2025-11-05 18-06-111" src="https://github.com/user-attachments/assets/42ed05d6-99ae-4936-a32e-0e76f6f4cc43" />

```sudo apt install atop```

<img width="1287" height="560" alt="Screenshot from 2025-11-05 18-07-310" src="https://github.com/user-attachments/assets/be817a44-e34f-44aa-938e-f4cfde5df5b8" />

```sudo apt install git```

<img width="1287" height="385" alt="Screenshot from 2025-11-05 18-11-39" src="https://github.com/user-attachments/assets/60fc285e-cd48-464c-96d1-1113bb5dfacc" />

```sudo apt install dnstop```

<img width="1287" height="516" alt="Screenshot from 2025-11-05 18-17-17" src="https://github.com/user-attachments/assets/155d85e4-80ca-4c04-8736-8f7defc84abc" />

```sudo apt install powertop```

<img width="1287" height="561" alt="Screenshot from 2025-11-05 18-17-45" src="https://github.com/user-attachments/assets/1061b4c1-72f7-47ee-9c5b-f43b8c71abba" />

```sudo apt-get install iptables```

<img width="1133" height="367" alt="Screenshot from 2025-11-05 20-04-22" src="https://github.com/user-attachments/assets/2ee94683-6835-4f27-a559-b6fa42a98d22" />

##
3. Настройка часового пояса и синхронизации времени

Чтобы установить часовой пояс пишем команду ```timedatectl list-timezones```

<img width="1156" height="1009" alt="Screenshot from 2025-11-05 00-27-03" src="https://github.com/user-attachments/assets/2a3ae0e1-074d-434e-9868-2351e4330431" />

Изучаем на наличие необходимую временную зону (нам нужна Asia/Yekaterinburg), пишем команду ```sudo timedatectl list-timezone Asia/Yekaterinburg``` чтобы выбрать необходимую временную зону. 

<img width="1156" height="1009" alt="Screenshot from 2025-11-05 00-28-52" src="https://github.com/user-attachments/assets/5e9538ab-62af-4d2c-a9aa-06c7ef9c897a" />

Проверяем применились ли изменения командой ```timedatectl```

<img width="1156" height="268" alt="Screenshot from 2025-11-05 00-30-331" src="https://github.com/user-attachments/assets/7a9e5cf5-9d07-49e7-aaee-335ace4eda73" />

Также видно что уже настроен NTP, но это из-за предустановленных настроек, перенастраиваем вручную. Для этого необходимо обновить/установить службу systemd-timesyncd. Я устанавливаю командой ```sudp apt install systemd-timesyncd```, потому что все мои попытки настроить
NTP по другому не увенчались успехом и строка NTP service всегда была n/a, из-за этого было принято решение настроить через эту службу. Для настройки открываем конфигурационный файл timesyncd.conf 

<img width="1287" height="659" alt="Screenshot from 2025-11-05 16-59-56" src="https://github.com/user-attachments/assets/08f2da2e-67da-408e-9e5f-a7eeb8b36b4b" />

Редактируем файл прописывая:``` #NTP=pool.ntp.org, #FallbackNTP=ntp.ubuntu.com```

Сохраняем изменения в файле и перезапускаем службу командой ```sudo systemctl restrat systemd-timesyncd```, далее проверяем что получилось командой ```timedatectl```

<img width="1287" height="659" alt="Screenshot from 2025-11-05 17-01-03" src="https://github.com/user-attachments/assets/364054f0-1a9a-4f67-be07-1e61a4e0883c" />

##
4) Настройка SSH-доступа

Для настройки ssh, устанавливаем openssh-server командной ```sudo apt-get install openssh-server```

<img width="1287" height="561" alt="Screenshot from 2025-11-05 19-40-20" src="https://github.com/user-attachments/assets/04fd9bac-c38b-4c6e-97d6-a4d8ea65b811" />

Включаем службу командой ```sudo systemctl enable ssh```

<img width="1287" height="561" alt="Screenshot from 2025-11-05 19-41-06" src="https://github.com/user-attachments/assets/16ec9235-72d8-47fc-aad7-b0565b9d37bf" />

Ищем нужный файл конфигурации sshd_config командой, ```cd /etc/ssh``` проваливаеимся в подпапку, с помощью ```ls``` отображаеи список файлов, открываем нужный файл в режиме изменения ```sudo nano /etc/ssh/sshd_config```

<img width="1272" height="305" alt="Screenshot from 2025-11-05 19-44-43" src="https://github.com/user-attachments/assets/e484f0a4-6f74-4739-9673-222334eae10d" />

Меняем номер порта для подключения с 22 на 1337

<img width="1138" height="1008" alt="Screenshot from 2025-11-05 19-45-59" src="https://github.com/user-attachments/assets/5a74bbad-f50b-4396-a893-5766afb88502" />

Ставим значения ```PermitRootLogin no, PubkeyAuthentication no, PasswordAuthentication no,``` расскоментируем строку ```#LogLevel INFO```, также ставим значение ```LoginGrace 1m```, всё это необходимо для улучшения безопасности ssh подключения

<img width="1138" height="1008" alt="Screenshot from 2025-11-05 19-54-49" src="https://github.com/user-attachments/assets/9a8fef9f-86d5-4d8b-b282-c1ad8ffeef07" />

<img width="1138" height="1008" alt="Screenshot from 2025-11-05 19-56-01" src="https://github.com/user-attachments/assets/be00a96e-76ae-4911-8e4e-7d0a84a8e07c" />

<img width="1138" height="1008" alt="Screenshot from 2025-11-05 20-00-56" src="https://github.com/user-attachments/assets/fd4704e2-5d44-4f7c-bbd7-1ab72ea4c954" />

<img width="1138" height="1008" alt="Screenshot from 2025-11-05 20-01-59" src="https://github.com/user-attachments/assets/c14db916-44a0-48a0-b2ed-4ea01836157f" />

Также надо добавить учетную запись пользователя с помощью которой будем подключаться, для этого пишем команду ```AllowUsers ruslan```

<img width="902" height="886" alt="Screenshot from 2025-11-05 20-27-35" src="https://github.com/user-attachments/assets/ceddf6cb-f8fd-4115-b4cd-5b04cb23b0af" />

После всего сохраняем файл и перезапускаем службу ssh

<img width="1317" height="387" alt="Screenshot from 2025-11-05 20-29-15" src="https://github.com/user-attachments/assets/e1d9aadc-dce8-4c9d-adf2-523691c62235" />

Теперь генерируем ключ подключения командой ```ssh-keygen```

<img width="1317" height="387" alt="Screenshot from 2025-11-05 20-29-54" src="https://github.com/user-attachments/assets/aedf7d97-7c1d-4437-b39a-b69825fafda6" />

Позже я заметил что ssh слушает 22 порт вместо настроенного 1337

<img width="1090" height="446" alt="Screenshot from 2025-11-06 00-28-501" src="https://github.com/user-attachments/assets/58a689c3-794d-4631-b26a-c63b6e18dbf3" />

Решил посмотреть какой порт слушается командной ```systemctl cat ssh.socket```, увидел что всё также 22 порт, решил перезагрузить командной ```daemon-reload```

<img width="1090" height="1009" alt="Screenshot from 2025-11-06 00-47-06" src="https://github.com/user-attachments/assets/01dfa808-a94b-49a2-8171-ff9d13d35f59" />

Также перезапустил ```ssh.socket```

<img width="1090" height="1009" alt="Screenshot from 2025-11-06 00-47-27" src="https://github.com/user-attachments/assets/d3a08bf2-4eb2-4c8f-8ca1-58d7653b8e25" />

Также за кадров вводил команды чтобы порт был разрешён бранмауэром командой ```ufw portd 1337```, а также добавил ip адрес компьютера в конфиг файл ssh чтобы он его слушал командой ```ListenAddress 192.168.1.100```, не уверен что у меня получилось нормально настроить ssh подключение потому что мне не удалось подключиться с виндовой машины

##
5. Установка и настройка fail2ban

Устанавливаем fail2ban командой ```sudo apt-get install fail2ban```

<img width="985" height="360" alt="Screenshot from 2025-11-05 22-55-29" src="https://github.com/user-attachments/assets/af3c78c7-e196-49bd-ba5b-352ff856a751" />

Открываем конфиг файл(называется тюрьма) командой ```sudo nano /etc/fail2ban/jail.conf```

<img width="985" height="360" alt="Screenshot from 2025-11-05 22-56-17" src="https://github.com/user-attachments/assets/f2cb5877-39a8-45cc-9ab6-f62abb3bb0f5" />

Думаю внести изменения и читаю в одной из инструкций что не нужно вносить изменения в этом файл, закрываю его и октрываю другой тоже тюрьма только точка локал. Команда ```sudo nano /etc/fail2ban/jail.local```

<img width="1435" height="1054" alt="Screenshot from 2025-11-05 23-06-13" src="https://github.com/user-attachments/assets/91624c86-e2c4-4426-b08c-7c9aedf0c8aa" />

Уже в этом файле прописываю белый лист айпишников, время на попытку ввода пароля, максимальное количество попыток ввода пароля и время бана для айпишника которого нет в белом листе

<img width="1793" height="1009" alt="Screenshot from 2025-11-06 01-02-54" src="https://github.com/user-attachments/assets/587e2d3e-f86b-4cff-96e0-28c610ee7a02" />

Пытаюсь проверить всё ли работает, вроде работает, естественно перед этим ребутаю службу, а потом смотрю статус

<img width="797" height="253" alt="Screenshot from 2025-11-05 23-13-38" src="https://github.com/user-attachments/assets/fede128b-4668-49d5-8286-a299eb8360d2" />

##
6. Установка и настройка nftables 

Устанавливаем ```nftables командной sudo apt install nftables```

<img width="1793" height="1009" alt="Screenshot from 2025-11-06 01-05-49" src="https://github.com/user-attachments/assets/7f99dfcf-a58f-4d06-b776-267fb4f6426b" />

Проверяем статус службы ```sudo systemctl status nftables ```

<img width="1793" height="1009" alt="Screenshot from 2025-11-06 03-49-35" src="https://github.com/user-attachments/assets/b7016c87-c147-49c2-bc6c-2bf5445006d5" />

Включаем службу в автозапуске ```sudo systemctl --now nftables ``` и открываем конфиг файл ```sudo nano systemctl /etc/nftables.conf```

<img width="1793" height="1009" alt="Screenshot from 2025-11-06 03-54-43" src="https://github.com/user-attachments/assets/ed52e1d0-a756-4e8f-b3f5-d10c187137d7" />

Разрешаем лупбэк, установленные соединения и порт ssh, блокируем всё остальное и разрешаем входящий трафик. Команды: ```iif lo; ct state established, related; tcp dport 1337; type filter hook output priority 0.```

<img width="1793" height="1009" alt="Screenshot from 2025-11-06 04-08-25" src="https://github.com/user-attachments/assets/a769b6e5-6c11-41d1-845a-3614d7210df2" />

Проверяем статус службы ```sudo systemctl status nftables```

<img width="1793" height="1009" alt="Screenshot from 2025-11-06 04-09-14" src="https://github.com/user-attachments/assets/76d6e966-1db4-4e21-96f4-1264394c6101" />

Вовсе не уверен что сделал правильно, имеются сомнения.

##
7. Установка Zabbix Agent

Качаем заббикс агента для убунты комадной(очень лень писать такую большую команду)```wget https://repo.zabbix/com/zabbix/7.0/ububntu/pool/main/z/zabbix-release/zabbix-release_7.0-1+ubuntu24.04_all.deb```

<img width="1793" height="1009" alt="Screenshot from 2025-11-06 04-37-48" src="https://github.com/user-attachments/assets/522cef07-f282-42b9-99c5-fbf731ba7f0b" />

Устанавливаем что скачали```sudo dpkg -i zabbix-release_7.0-1+ubuntu24.04_all.deb```

<img width="1793" height="1009" alt="Screenshot from 2025-11-06 04-38-41" src="https://github.com/user-attachments/assets/9f17a333-25aa-4b33-8e4e-83ca180a20ec" />

Делай апдейт всего``` sudo apt update и sudo apt upgrade ```для перестраховки и сразу же запускаем установку службы заббикса командой ``` sudo apt install zabbix-agent```

<img width="1793" height="1009" alt="Screenshot from 2025-11-06 04-40-00" src="https://github.com/user-attachments/assets/72c34523-6a66-46b3-a9be-b69d724ebc85" />

<img width="1793" height="1009" alt="Screenshot from 2025-11-06 04-42-13" src="https://github.com/user-attachments/assets/55d933f9-b967-499b-86a3-5f338bd8d4db" />

Открываем конфиг файл ```sudo nano /etc/zabbix/zabbix_agentd.conf```

<img width="1793" height="1009" alt="Screenshot from 2025-11-06 04-43-13" src="https://github.com/user-attachments/assets/09e55ab6-3f96-4845-bcbe-ffdddd64c7c2" />

Выставляем ```ServerActive=zabbix.company.local; Hostname=test; Server=zabbix.company.local``` делаем всё как требуется в задании, в скриншот не попала строка server

<img width="1793" height="1009" alt="Screenshot from 2025-11-06 04-49-59" src="https://github.com/user-attachments/assets/bbdec197-b3c4-4b5f-b47f-39401f5295b7" />

<img width="1793" height="1009" alt="Screenshot from 2025-11-06 04-52-01" src="https://github.com/user-attachments/assets/5c52c70b-cbd8-4404-9a53-bf6b02174300" />

Также не забываем добавить 10051 в фильтр командой ```tcp dport 10051```

<img width="1793" height="1009" alt="Screenshot from 2025-11-06 04-45-36" src="https://github.com/user-attachments/assets/95730e27-d2c3-4c27-811a-7b88d66f6841" />

Дальше снова ребутаем командной ```sudo systemctl restart zabbix-agent.service и проверяем статус sudo systemctl status zabbix-agent```

<img width="1793" height="1009" alt="Screenshot from 2025-11-06 04-52-35" src="https://github.com/user-attachments/assets/273e812e-2526-42d1-968e-bbaf5e196333" />

##
8. Настройка cron 

Настройка которую я не смог победить, так и не понял как сделать чтобы появилась задача в списке, но я хотя бы настроил чтобы задача работала в 3:00 и по сути она должна бы была запускаться от рута

<img width="1793" height="1009" alt="Screenshot from 2025-11-06 05-46-00" src="https://github.com/user-attachments/assets/51f7f93a-c1f0-4111-afbf-75b7de198092" />
<img width="1793" height="1009" alt="Screenshot from 2025-11-06 05-15-07" src="https://github.com/user-attachments/assets/8786d20d-0477-46bd-a50e-6aad0176d4e0" />
<img width="1793" height="1009" alt="Screenshot from 2025-11-06 05-07-45" src="https://github.com/user-attachments/assets/53df5273-3048-46ba-9058-6306ee2ac738" />

##
9. Подготовка к использованию как шаблон

Я не имею понятия как данный шаблон можно завернуть в полноценный образ, потому что не делал это самостоятельно, но как мне кажется необходимо сперва сделать бэкап всё системы, после уже снимать готовый образ с системы, грузим его на флешку и разворачиваем на рабочих
машин.

##
10. Документация в формате README.md

a) Данный шаблон используется для проверки знаний потенциального сотрудника, также является хорошим инструментом подготовки перед крупными задачами, ещё этот шаблон можно использовать для автоматизации рабочих процессов по разворачиванию ОС на новых серверах и
компьютерах.
  Используется версия Ubuntu 24.04.3 LTS

  <img width="693" height="474" alt="Screenshot from 2025-11-06 16-06-00" src="https://github.com/user-attachments/assets/06823fff-dff0-4b04-a1de-bbd4030c7872" />

b) Я вел комментирование почти каждой задачи, понимаю что сделал не идеально, с оформлением в таком формате я сталкиваюсь впервые. Были выполнены по мере возможностей и навыков задания поставленные в ТЗ (постарался расписать что делал в каждом задании), выбрал
максимально простой подход, а точнее использовал в основном гайды как настраивать те или иные утилиты, сервисы и службы. Потому что не имею больше опыта в работе с Linux. 









Тестовое задание для собеседования
