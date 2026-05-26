# shell_S

![Запуск терминала](start.gif)

Минималистичная тема Oh My Posh и профиль PowerShell с градиентным приветствием при старте.

## Особенности

- Компактная тема Oh My Posh: имя пользователя, хост, текущий путь, Git-статус, время.
- Градиентное приветствие при запуске (от чёрного к белому).
- Набор полезных алиасов: `..`, `...`, `~`.
- Оптимизированные настройки PSReadLine (история, предсказания, отключение звука).

## Требования

- [PowerShell 7](https://github.com/PowerShell/PowerShell)
- [Oh My Posh](https://ohmyposh.dev/docs/installation/windows)
- [Terminal-Icons](https://github.com/devblackops/Terminal-Icons) 

## Установка

1. Установите модули:
   ```powershell
   Install-Module Oh-My-Posh -Scope CurrentUser
   Install-Module Terminal-Icons -Scope CurrentUser

2. Добавьте содержимое файла `profile.ps1` из этого репозитория в ваш профиль PowerShell.  

   > **Важно**  
   > Найдите в скопированном коде строку  
   > `$ompConfig = ".\atomicBit.omp.json"`  
   > и убедитесь, что путь указывает на реальное расположение файла `shell_S.omp.json` на вашем компьютере.  
   > Если вы сохранили тему в другую папку, **обязательно исправьте эту переменную** – иначе тема не загрузится.
