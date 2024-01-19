# Автоматический запуск Podman и Gamma при старте ОС

Сделать это можно следующими способами:  
– c помощью systemd в Linux и launchd в macOS: посредством запуска скрипта start_gamma.sh  
– через запуск скрипта start_gamma.ps1 планировщиком Windows, добавив в него задачу скриптом start_with_windows.ps1  
Если вы инсталлировали Podman впервые и не настраивали ранее автоматический старт виртуальной машины Podman, то сделать это можно на всех ОС такими способами:  
– раскомментировав строку “podman machine start” в скрипте start_gamma  
– опцией “Engine autostart” в настройках Podman Desktop

