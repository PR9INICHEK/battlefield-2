Создание и настройка сервера
1. `sudo useradd -m bf2server`
2. `sudo passwd bf2server` далее вводим пароль
3. `sudo -u bf2server -s`
4. `cd /home/bf2server`
    - потому что по умолчанию попадаешь в _bf2server@noname:/root$_
6. `mkdir server-files`
7. `cd server-files`
8. `wget http://dev.insomnia365.com/mirror/bf2/1.41_patch/bf2-linuxded-1.1.2965-797.0-installer.sh`
   - Ссылка нерабочая
9. `chmod +x bf2-linuxded-1.1.2965-797.0-installer.sh`
   - Но не понял, зачем эта команда
10. `./bf2-linuxded-1.1.2965-797.0-installer.sh`
11. 
