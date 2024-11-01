# Создание и настройка сервера
## Подготовка
1. `sudo useradd -m bf2server`
2. `sudo passwd bf2server` далее вводим пароль
3. `sudo adduser bf2server sudo` - даём возможность новому пользователю выполнять команды из под _sudo_
4. `sudo -u bf2server -s`
5. `cd /home/bf2server`
    - потому что по умолчанию попадаешь в _bf2server@noname:/root$_
6. `mkdir server-files`
7. `cd server-files`
## Скачивание
1. `wget http://ftp2.sly.hu/letolt//battlefield2/bf2-linuxded-1.5.3153.0-installer.rar`
    - Тут должны быть запасные urls
10. Если файл с расширением .rar, то устанавлием _unrar_ - `sudo apt-get install unrar`
11. Разархивируем архив -`unrar x -r bf2-linuxded-1.5.3153.0-installer.rar`
12. Для .sh этого не требуется делать
## Установка
1. `sudo chmod +x bf2-linuxded-1.5.3153.0-installer.sh` - без этой команды при выполнении `sudo ./bf2-linuxded-1.5.3153.0-installer.sh` получите ошибку _command not found_
15. `sudo ./bf2-linuxded-1.5.3153.0-installer.sh`
16. Видим сообщение "You will now be shown the EULA for the BF2 dedicated Linux server. Press return to continue."
17. Нажимаем _Enter_
12. Открывается лицензия и показывается процент пройдённого
13. Либо пролистываем по чуть-чуть с помощью нажатия _Enter_
14. Либо переходим к концу с помощью _Page Down_
15. Пишем _accept_
    - не ясно, _decline_ влияет ли на работоспособность сервера
        - > If you decline, you may not use the Tools & Materials.
16. Далее открывается лицензия на использование PunkBuster'a - "You will now be shown the EULA for PunkBuster. Press return to continue."
17. Нажимаем _Enter_
18. Нажимаем _Page Down_
19. Пишем _yes_
    - Не ясно, нужен ли он нам в текущих реалиях и можно ли написать _no_
20. > The target installation directory is where the bf2 directory will be created and must be an existing directory. Enter your target installation directory:
21. Указываем текущую директорию `/home/bf2server/server-files`
22. Дожидаемся сообщений
    - > Installing BF2 to /home/bf2server/server-files/bf2...
    - > Installing PunkBuster...
    - 
    - > Installation complete.



Вот такие файлы и папки у вас должны появиться в созданной папке **bf2**:
1. admin
2. lowercaseDir.py
3. pb_ia-32
4. readmes
5. adminutils
6.  mods
7.  pylib-2.3.4.zip
8. rotate_demo.cfg
9. bin
10. pb_amd-64
11. python
12. start.sh

## Настройка
1. `nano /server/bf2/mods/bf2/settings/serversettings.con`
