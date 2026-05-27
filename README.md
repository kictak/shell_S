# shell_S

![Запуск терминала](start.gif)
![VS Code терминал](vs_code.png)

Минималистичная тема Oh My Posh и профиль PowerShell с анимированным запуском, градиентом и звуковым эффектом.

---
# Если вы будете редактировать код shell_S.omp.json убедитесь, что кодировка файла — UTF-8 без BOM.

## Возможности

- минималистичный PowerShell-профиль
- тема Oh My Posh:
  - пользователь
  - хост
  - короткий путь
  - Git-статус
  - время справа
- анимированное приветствие при запуске
- плавный heat-gradient
- пропуск анимации клавишей **Space**
- звук запуска (`startup.wav`)
- безопасная остановка звука при закрытии pwsh
- автоматический поиск файлов рядом с `PROFILE`
- кэширование Oh My Posh для быстрого старта
- ленивая загрузка `Terminal-Icons`
- удобные алиасы:
  - `..`
  - `...`
  - `~`
  
---

## Требования

| Компонент | Ссылка |
|---|---|
| PowerShell 7 | https://github.com/PowerShell/PowerShell |
| Oh My Posh | https://ohmyposh.dev/docs/installation/windows |
| Terminal-Icons | https://github.com/devblackops/Terminal-Icons |

---

# Быстрая установка (рекомендуется)

### 1. Клонируйте репозиторий

```powershell
git clone https://github.com/kictak/shell_S.git
```

---

### 2. Перейдите в папку

```powershell
cd shell_S
```

---

### 3. Откройте профиль PowerShell

```powershell
notepad $PROFILE
```

Если файла нет — PowerShell создаст его.

---

### 4. Скопируйте содержимое `PROFILE`

Откройте файл:

```powershell
notepad .\PROFILE
```

Скопируйте всё содержимое и вставьте в `$PROFILE`.

---

### 5. Положите файлы рядом с профилем

Откройте папку профиля:

```powershell
explorer (Split-Path $PROFILE)
```

Скопируйте туда:

```text
PROFILE
shell_S.omp.json
startup.wav
```

Итог:

```text
Documents\PowerShell\
├─ PROFILE
├─ shell_S.omp.json
└─ startup.wav
```

---

### 6. Перезапустите PowerShell

или выполните:

```powershell
. $PROFILE
```

Готово.

---

# Как это работает

Профиль автоматически ищет файлы рядом с собой:

```powershell
$ompConfig = Join-Path $PSScriptRoot "shell_S.omp.json"
$soundPath = Join-Path $PSScriptRoot "startup.wav"
```

Это значит:

- можно открывать терминал из любой папки
- тема всегда найдётся
- звук всегда найдётся

Без ручной правки путей.

---

# Пропуск анимации

Во время запуска нажмите:

```text
Space
```

Оставшаяся часть баннера появится мгновенно.

---

# Звук запуска

По умолчанию используется:

```text
startup.wav
```

рядом с `PROFILE`.

---

## Добавить свой звук

Поддерживается PCM WAV.

Конвертация:

```powershell
ffmpeg -i "my.mp3" -acodec pcm_s16le -ar 44100 "startup.wav"
```

Положите файл рядом с профилем.

---

## Отключить звук

Закомментируйте строку:

```powershell
$soundPath = Join-Path $PSScriptRoot "startup.wav"
```

---

# Дополнительно

## Убрать баннер PowerShell

Windows Terminal → Settings → PowerShell → commandline

```powershell
pwsh.exe -NoLogo
```

---

## Скорость анимации

Найдите:

```powershell
for ($w = 0; $w -lt 6000; $w++) { }
```

Быстрее:

```powershell
3000
```

Медленнее:

```powershell
8000
```

Мгновенно:

удалить строку.

---

## Обновить репозиторий

Если уже установлен:

```powershell
cd shell_S
git pull
```

---

# Файлы

| Файл | Назначение |
|---|---|
| `PROFILE` | PowerShell профиль |
| `shell_S.omp.json` | тема Oh My Posh |
| `startup.wav` | звук запуска |
| `start1.gif` | демонстрация |
| `vs_code.png` | демонстрация vs_code|

---

Сделано для PowerShell + Windows Terminal.
