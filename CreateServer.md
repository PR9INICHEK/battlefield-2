# Создание и настройка сервера
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
9. Если файл с расширением .rar, то устанавлием _unrar_ - `sudo apt-get install unrar`
10. Разархивируем архив -`unrar x -r bf2-linuxded-1.5.3153.0-installer.rar`
11. Для .sh этого не требуется делать
12. `sudo chmod +x bf2-linuxded-1.5.3153.0-installer.sh` - без этой команды при выполнении `sudo ./bf2-linuxded-1.5.3153.0-installer.sh` получите ошибку _command not found_
13. `sudo ./bf2-linuxded-1.5.3153.0-installer.sh`
14. Видим сообщение "You will now be shown the EULA for the BF2 dedicated Linux server. Press return to continue."
15. Нажимаем _Enter_
12. Открывается лицензия и показывается процент пройдённого
13. Либо пролистываем по чуть-чуть с помощью нажатия _Enter_
14. Либо переходим к концу с помощью _Page Down_
15. Пишем _accept_
    - не ясно, _decline_ влияет ли на работоспособность сервера
        - > If you decline, you may not use the Tools & Materials.
16. 
