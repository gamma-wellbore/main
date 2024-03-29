
# Подготовка. Обновление Python на Astra Linux

По умолчанию на Astra Linux установлен старый Python версии 3.6. Это не дает возможности пользоваться современными библиотеками, которые используются в ПО и могут быть использованы пользователями при написании своих скриптов.

В связи с этим необходимо произвести обновление Python. Ниже представлены все необходимые команды для того, чтобы скачать исходные коды Python, скомпиллировать их на рабочей станции и установить. К сожалению, в общем доступе нет установочной версии Python для для простой установки, поэтому необходимо их собрать самому из исходников.


+ Установить зависимости:
`sudo apt install build-essential zlib1g-dev libncurses5-dev libgdbm-dev liblzma-dev libnss3-dev  libssl-dev libsqlite3-dev libreadline-dev libffi-dev curl libbz2-dev `

+ Скачать текущую версию исходников с оффициального сайта [Python download page](https://www.python.org/downloads/source/) при помощи операции [`wget`](https://linuxize.com/post/wget-command-examples/)
Пример для текущей версии Python на время написания инструкции (Python 3.9.1):
```
wget https://www.python.org/ftp/python/3.9.1/Python-3.9.1.tgz
```

+ Когда загрузка завершена, [разархивировать архив с по помощью команды tar](https://linuxize.com/post/how-to-extract-unzip-tar-gz-file/) :
```
tar -xf Python-3.9.1.tgz
```

+ [Перейти](https://linuxize.com/post/linux-cd-command/) в папку где находятся разархивированные файлы и запустить скрипт `configure` :
```
cd Python-3.X.X
./configure --enable-optimizations
```

Опция `--enable-optimizations` оптимизирует процесс, запуском нескольких тестов, это может немногог замедлить процедуру.

Далее скрипт запускает несколько проверок, чтобы быть уверенным, что все необходимые зависимости присутствуют в системе:

+ Start the Python 3.9 build process:
```
make -j 2
```

Чтобы ускорить процесс сборки поставьте после `-j` количество процессоров, которые у вас есть в рабочей станции. Это можно узнать командой `nproc`.

+ Когда процесс сборки завершится можно запустить установку Питона следующей командой: 
    ```
    sudo make altinstall
    ```

   Рекомендуется использовать команду `altinstall` вместо `install` чтобы произошла замена имеющихся в системе библиотек python3.
   
Готово. Python 3.9 инсталлирован в системе. Версию можно проверить следующей командой:

```
python3.9 --version
```

Результат покажет текущую версию Python:

```output
Python 3.9.1
```

