# Git commands

Команды для создания файла в разных оболочках:
CMD (командная строка Windows):
echo. > app.py # создаст file app

LINUX:
За допомогою команди touch:
touch app.py

PowerShell:
New-Item -Path . -Name "app.py" -ItemType "file"

Команда mkdir создаёт каталоги, например:
mkdir my_folder # создаст папку my_folder

Команды для создания файла в разных оболочках:
CMD (командная строка Windows):

bash
Копіювати код
echo. > app.py
PowerShell:

bash
Копіювати код
New-Item -Path . -Name "app.py" -ItemType "file"
Команда mkdir создаёт каталоги, например:

bash
Копіювати код
mkdir my_folder # создаст папку my_folder

Если вы работаете в Linux или macOS через терминал PyCharm, вместо этого используйте:

bash
Копіювати код
touch app.py

В терминале PyCharm на Windows, если команда echo. вызывает ошибку, это может быть связано с тем, что PyCharm использует PowerShell по умолчанию, а не стандартную командную строку.

В PowerShell используйте команду New-Item для создания файла. Вот как это сделать:

В PowerShell:
bash
Копіювати код
New-Item -Path . -Name "app.py" -ItemType "file"
Альтернативный способ:
Также можно использовать команду Out-File для создания пустого файла:

bash
Копіювати код
"" | Out-File -FilePath app.py
В CMD:
Если вы хотите использовать команду echo в стандартной командной строке (CMD), убедитесь, что вы используете CMD, а не PowerShell:

В PyCharm перейдите на вкладку Terminal.
Измените оболочку на CMD, если это возможно. Для этого вы можете изменить настройки терминала в PyCharm:
Откройте настройки PyCharm: File > Settings (или PyCharm > Preferences на macOS).
Перейдите в раздел Tools > Terminal.
В поле Shell Path укажите путь к cmd.exe (например, C:\Windows\System32\cmd.exe).
Сохраните изменения и перезапустите терминал.
В CMD команда для создания файла будет работать так:

bash
Копіювати код
echo. > app.py
Эти методы помогут вам создать файл app.py в терминале PyCharm независимо от используемой оболочки.


