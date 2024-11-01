Создание и настройка сервера
1. `sudo useradd -m bf2server`
2. `sudo passwd bf2server` далее вводим пароль
3. `sudo adduser bf2server sudo` - даём возможность новому пользователю выполнять команды из под _sudo_
4. `sudo -u bf2server -s`
5. `cd /home/bf2server`
    - потому что по умолчанию попадаешь в _bf2server@noname:/root$_
6. `mkdir server-files`
7. `cd server-files`
8. `wget http://ftp2.sly.hu/letolt//battlefield2/bf2-linuxded-1.5.3153.0-installer.rar`
    - Тут должны быть запасные urls
10. `chmod +x bf2-linuxded-1.1.2965-797.0-installer.sh`
    - Но не понял, зачем эта команда
11. `./bf2-linuxded-1.1.2965-797.0-installer.sh`
12. 
