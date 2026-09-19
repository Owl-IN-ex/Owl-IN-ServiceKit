# Архитектура Owl-IN ServiceKit

## Общая схема

Текущая архитектура:

```text
WPF host (.NET 8)
    ↓
WebView2 UI
    ↓
C# host actions / PowerShell backend
    ↓
Windows APIs / CIM / Event Log / network tools
```

Portable-сборка распространяется как один EXE-контейнер. При запуске внутренний runtime распаковывается в локальный versioned cache.

## Слои

### UI

`ui/`

- `index.html`
- `app.css`
- `app.js`
- графические assets

UI отвечает за навигацию, визуализацию результатов и пользовательские сценарии. Системные действия выполняются через host/backend.

### WPF / C# host

Главный desktop-контейнер и мост между WebView2 и системной частью.

### PowerShell backend

`backend/ServiceKit.Backend.ps1`

Используется для системной диагностики и существующих repair-actions. PowerShell-файлы проекта хранятся в UTF-8 с BOM для корректной работы Windows PowerShell 5.1 на русской Windows.

### Launcher

`Launcher/`

Создаёт распространяемый EXE и управляет versioned runtime-кэшем в `%LOCALAPPDATA%\Owl-IN\ServiceKit\runtime\...`.

## Принцип системных действий

Для операций, которые изменяют состояние Windows, используется схема:

**Detect → Explain → Backup → Fix → Verify → Rollback**

## Easy и Expert

Easy и Expert используют общие данные и часть общих низкоуровневых операций, но отличаются уровнем детализации и пользовательским сценарием.

## Offline-first

Основная диагностика Owl-IN ServiceKit рассчитана на работу без постоянного подключения к интернету. Сеть используется там, где она действительно нужна: например, для сетевых тестов или проверки релизов.
