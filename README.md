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

2. Откройте свой профиль PowerShell (если файла нет, он создастся):
   powershell
   notepad $PROFILE
   
3. Добавьте содержимое файла profile.ps1 из этого репозитория в открывшийся блокнот.

## ВНИМАНИЕ ##

4.  Найдите в коде строку $ompConfig = ".\shell_S.omp.json" и замените путь на тот, где лежит ваш файл shell_S.omp.json.


5. Сохраните профиль (Ctrl+S) и закройте блокнот.

6. Перезапустите терминал.

## Дополнительно

- Отключение баннера PowerShell: запускайте pwsh.exe -NoLogo.

- Отключение встроенного замера времени профиля:
  powershell
  Disable-ExperimentalFeature -Name PSProfileLoadTime
  Если нужна анимация приветствия, используйте функцию с Start-Sleep (закомментирована в profile.ps1).

## Файлы

- shell_S.omp.json – тема Oh My Posh.

- profile.ps1 – профиль PowerShell.
