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
12. Для _.sh_ этого не требуется делать
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
6. mods
7. pylib-2.3.4.zip
8. rotate_demo.cfg
9. bin
10. pb_amd-64
11. python
12. start.sh

## Настройка
1. `sudo nano bf2/mods/bf2/settings/serversettings.con`
    - через `sudo`, в ином случае увидите - "[ File 'serversettings.con' is unwritable ]"
2. TODO Тут нужна ссылка на то как настраивать _serversettings.con_, что за что отвечает и для _maplist.con_
    - `cd readmes`
    - `nano readme-linux.txt`
        - Тут инфа по параметрам для _serversettings.con_
    - `nano readmeserver.txt`
        - Тут ещё доп инфа, в том числе и про _maplist.con_
     
Какие-то из команд ниже помогли с проблемой

4. sudo apt-get install ia32-libs
        Reading package lists... Done
        Building dependency tree... Done
        Reading state information... Done
        Package ia32-libs is not available, but is referred to by another package.
        This may mean that the package is missing, has been obsoleted, or
        is only available from another source
        However the following packages replace it:
          lib32z1
        
        E: Package 'ia32-libs' has no installation candidate

`find /usr/lib/ -name *ncurses*`

/usr/lib/x86_64-linux-gnu/libncursesw.so.6
/usr/lib/x86_64-linux-gnu/libncurses.so.6
/usr/lib/x86_64-linux-gnu/libncursesw.so.6.4
/usr/lib/x86_64-linux-gnu/libncurses.so.6.4


https://stackoverflow.com/questions/17005654/error-while-loading-shared-libraries-libncurses-so-5

`sudo ln -s /usr/lib/x86_64-linux-gnu/libncursesw.so.6.0 /usr/lib/libncurses.so.5`
`sudo ln -s /usr/lib/x86_64-linux-gnu/libncursesw.so.6.0 libncursesw.so.5`


find /usr/lib/ -name *libtinfo*
/usr/lib/x86_64-linux-gnu/libtinfo.so.6.4
/usr/lib/x86_64-linux-gnu/libtinfo.so.6

`sudo ln -s /usr/lib/x86_64-linux-gnu/libncursesw.so.6.0 /usr/lib/libtinfo.so.5`


https://stackoverflow.com/a/79141988

`sudo nano /etc/apt/sources.list.d/ubuntu.sources`
    Types: deb
    URIs: http://security.ubuntu.com/ubuntu/
    Suites: focal-security
    Components: main universe
    Signed-By: /usr/share/keyrings/ubuntu-archive-keyring.gpg


`sudo apt update`
`sudo apt-get install libncurses5:i386`

https://stackoverflow.com/a/78649883

`sudo add-apt-repository universe`
`sudo apt-get install libncurses5 libncurses5:i386`
https://askubuntu.com/questions/1252062/how-to-install-libncurses-so-5-in-ubuntu-20-04


`cd /home/bf2server/server-files/bf2`


## Запуск
1. `sudo ./start.sh +help` - Для проверки, что всё хорошо
    - Если без `sudo`, то будет ошибка "./start.sh: 24: ulimit: error setting limit (Operation not permitted)". Хотя информация о параметрах выведется
2. 

# Полезные ссылки
1. https://habr.com/ru/articles/149947/
2. Инфа про PunkBuster - https://habr.com/ru/articles/149947/#comment_5076552
