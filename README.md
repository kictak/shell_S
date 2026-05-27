# shell_S

![Запуск терминала](start1.gif)

Минималистичная тема Oh My Posh и профиль PowerShell с анимированным запуском и зву ковым эффектом.

---

## Особенности

- Минималистичный профиль для PowerShell
- Oh My Posh тема: пользователь, хост, путь, Git-статус, время
- Анимированное приветствие при запуске
- Плавный градиент от тёмного к светлому
- Пропуск анимации пробелом
- Опциональный звук запуска (`startup.wav`)
- Удобные алиасы: `..`, `...`, `~`
- Настроенный PSReadLine:
  - история команд
  - подсказки
  - отключение системного звука

---

## Требования

| Компонент | Ссылка |
|---|---|
| PowerShell 7 | https://github.com/PowerShell/PowerShell |
| Oh My Posh | https://ohmyposh.dev/docs/installation/windows |
| Terminal-Icons | https://github.com/devblackops/Terminal-Icons |

---

## Установка

### 1. Установите модули

```powershell
Install-Module Oh-My-Posh -Scope CurrentUser
Install-Module Terminal-Icons -Scope CurrentUser
```

---

### 2. Откройте профиль PowerShell

```powershell
notepad $PROFILE
```

Если файла нет — PowerShell создаст его автоматически.

---

### 3. Добавьте `profile.ps1`

Скопируйте содержимое файла `profile.ps1` из репозитория в открывшийся профиль.

---

### 4. Укажите путь к теме

> [!WARNING]
> Найдите строку:

```powershell
$ompConfig = ".\shell_S.omp.json"
```

и замените путь на свой.

Пример:

```powershell
$ompConfig = "C:\Users\Name\Documents\PowerShell\shell_S\shell_S.omp.json"
```

---

### 5. Сохраните и перезапустите терминал

---

## Пропуск анимации

Во время запуска нажмите **Space**.

Оставшаяся часть приветствия отобразится мгновенно.

---

## Звук запуска

По умолчанию профиль ищет:

```powershell
.\startup.wav
```

---

### Добавить свой звук

Поддерживается PCM WAV.

Конвертация через ffmpeg:

```powershell
ffmpeg -i "your-sound.mp3" -acodec pcm_s16le -ar 44100 "startup.wav"
```

После этого положите файл рядом с профилем
или укажите абсолютный путь.

Пример:

```powershell
$soundPath = "C:\Users\Name\Music\startup.wav"
```

---

### Отключить звук

Закомментируйте строку:

```powershell
$soundPath = ".\startup.wav"
```

---

## Дополнительно

### Убрать баннер PowerShell

Запуск без логотипа:

```powershell
pwsh.exe -NoLogo
```

В Windows Terminal:

Settings → PowerShell → commandline

```powershell
pwsh.exe -NoLogo
```

---

### Отключить встроенный замер загрузки профиля

```powershell
Disable-ExperimentalFeature -Name PSProfileLoadTime
```

---

### Изменить скорость анимации

В `profile.ps1` найдите:

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

удалите строку полностью

---

## Файлы

| Файл | Описание |
|---|---|
| `shell_S.omp.json` | тема Oh My Posh |
| `profile.ps1` | профиль PowerShell |
| `start.gif` | демонстрация запуска |
| `startup.wav` | звук запуска (опционально) |

---

Сделано для PowerShell. 
