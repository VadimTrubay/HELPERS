Команды для создания файла в разных оболочках:
`echo. > app.py` -- Windows
`touch app.py` -- LINUX

Выполнение кода Python из командной строки с ключом -c:
`C:\Users\Al>python -c "print('Hello, world')"`
`C:\Users\Al>python -c "help(len)"`
`C:\Users\Al>py -3.6 -c "import sys;print(sys.version)"`

Просмотр истории команд:
`doskey/history`
`history`

Определение папок и файлов с использованием универсальных символов:
`C:\Users\Al>dir *.py`
`records201?.txt`

Изменение текущего рабочего каталога командой cd:
`C:\Users\Al>cd Desktop`
`C:\Users\Al>d:`
`C:\Users\Al>cd ..`

Вывод содержимого папки командами dir и ls:
`C:\Users\Al>dir`
`al@ubuntu:~$ ls -a`
`al@ubuntu:~$ ls -l`
`al@ubuntu:~$ ls -al`

Вывод содержимого вложенных папок командами dir /s и find:
`C:\github\ezgmail>dir /s *.py`
`al@ubuntu:~/Desktop$ find . -name "*.py"`


Копирование файлов и папок командами copy и cp:
`C:\Users\Al>copy hello.py someSubFolder`
`al@ubuntu:~/someFolder$ cp hello.py someSubFolder`

Перемещение файлов и папок командами move и mv:
`al@ubuntu:~/someFolder$ mv hello.py someSubFolder`

Переименование файлов и папок командами ren и mv:
`al@ubuntu:~/someFolder$ mv hello.py goodbye.py`

Удаление файлов и папок командами del и rm:
`del /s /q [папка]`
`rd /s/q [исходная папка] `
`rm -r [папка]`
`rm -rf [исходная папка]`

Создание папок командами md и mkdir:
`al@ubuntu:~/Desktop$ mkdir yourScripts`

Поиск программ командами where и which:
`C:\Users\Al>where python`

Очистка терминала командами cls и clear:
`cls`
`clear`

Просмотр переменных среды  set (в Windows) или env (в macOS или Linux):
`C:\Users\Al>set`
`al@al-VirtualBox:~$ echo $HOME`

Переменная среды PATH:
`C:\Users\Al>path`
`al@ubuntu:~$ echo $PATH`

Изменение переменной среды PATH в командной строке:
`C:\Users\Al>path C:\newFolder;%PATH%`
`al@al-VirtualBox:~$ PATH=/newFolder:$PATH`

Постоянное включение папок в PATH в Windows:
`Edit environment variables for your account`

Постоянное включение папок в PATH в macOS и Linux :
`export PATH=/newFolder:$PATH`

Запуск программ Python в Windows
`WIN+R`
`py C:\path\to\yourScript.py`
Проблемы удается решить созданием пакетного сценария
— небольшого текстового
файла с расширением .bat, который может выполнять сразу несколько 
терминальных команд (по аналогии со сценариями командной оболочки в macOS иLinux). 
Для создания этих файлов можно воспользоваться текстовым редактором (например,
Блокнотом). Создайте новый текстовый файл, содержащий следующие две строки:
`@py.exe C:\path\to\yourScript.py %*
@pause`

Запуск программ Python в macOS
В macOS можно создать сценарий командной оболочки для запуска сценариев
Python; для этого следует создать текстовый файл с расширением .command. 
Создайте такой файл в текстовом редакторе (например, TextEdit) и введите следующие
команды:
`#!/usr/bin/env bash
python3 /path\to\yourScript.py`

Запуск программ Python в Ubuntu Linux:
`#!/usr/bin/env python3`
`al@al-VirtualBox:~$ chmod u+x yourScript.py`

Отладочный вывод:
`import logging
logging.basicConfig(filename='log_filename.txt', level=logging.DEBUG,
format='%(asctime)s - %(levelname)s - %(message)s')
logging.debug('This is a log message.')`


































