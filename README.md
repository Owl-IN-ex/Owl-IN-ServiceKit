<p align="center">
  <img src="docs/images/readme-cover.png" alt="Owl-IN ServiceKit" width="100%">
</p>

<p align="center">
  <a href="https://github.com/Owl-IN-ex/Owl-IN-ServiceKit/releases/latest"><strong>Скачать последнюю версию</strong></a>
  ·
  <a href="CHANGELOG.md">История версий</a>
  ·
  <a href="ROADMAP.md">План работ</a>
</p>

# Owl-IN ServiceKit

**Owl-IN ServiceKit** — портативная утилита для диагностики и аккуратного восстановления Windows 10/11. Установка не требуется: релизная сборка распространяется одним EXE.

**Обнаружить → Объяснить → Сохранить состояние → Исправить → Проверить → Откатить**

## Что уже умеет

- быстрый **Quick Scan** компьютера;
- режим **Easy Mode** с понятными сценариями «У меня проблема»;
- режим **Expert Mode** с расширенной технической диагностикой;
- диспетчер процессов с CPU, RAM, GPU и VRAM, поиском и подробностями программы;
- проверка сети, DNS, прокси, VPN/TUN, hosts и компонентов, влияющих на соединение;
- диагностика накопителей, RAM/BSOD, Windows Update, служб, автозапуска и событий Windows;
- анализ подозрительной фоновой активности с учётом процессов, путей, подписи и механизмов автозапуска;
- анализ подозрительных объектов и связанных механизмов автозапуска;
- восстановление подключения после некорректных proxy/PAC-настроек, оставшихся после VPN;
- отчёты, история запусков и раздел восстановления;
- запуск из одного EXE без отдельной установки.

## Easy Mode и Expert Mode

**Easy Mode** нужен, когда не хочется разбираться в Event ID, службах, драйверах и реестре. Выбираешь симптом — **Owl-IN ServiceKit** собирает данные, объясняет результат обычным языком и предлагает доступный следующий шаг.

**Expert Mode** показывает технические доказательства и состояние системы подробнее: конфигурацию, сеть, накопители, RAM/BSOD, Windows Update, службы и автозапуск, события, безопасность и RAW-данные.

## Скриншоты

### Easy Mode — «У меня проблема»

<p align="center">
  <img src="docs/images/easy-mode.png" alt="Owl-IN ServiceKit — Easy Mode — У меня проблема" width="100%">
</p>

Пользователь выбирает симптом, после чего Owl-IN ServiceKit запускает соответствующую проверку и показывает результат без необходимости вручную разбирать технические данные.

### Expert Mode — «Сеть»

<p align="center">
  <img src="docs/images/expert-mode.png" alt="Owl-IN ServiceKit — Expert Mode — Сеть" width="100%">
</p>

Технический режим показывает состояние сети, прокси, hosts, VPN/TUN-интерфейсов, сетевых драйверов и других компонентов, которые могут влиять на подключение.

## Текущая версия

**1.3.0** — актуальный стабильный выпуск Owl-IN ServiceKit.

**[Скачать Owl-IN ServiceKit 1.3.0](https://github.com/Owl-IN-ex/Owl-IN-ServiceKit/releases/tag/v1.3.0)**

Проверенный релизный файл: `Owl-IN-ServiceKit-1.3.0.exe`.

```text
SHA-256: b9c006919795ec12c12ff51547be03f12f04c7b2e818461a1e57aabcefd7c290
```

Закрытие окна крестиком сворачивает приложение в область уведомлений. Для полного завершения выберите **«Выйти»** в меню значка. Перед запуском новой версии завершите предыдущую.

Готовые EXE не хранятся среди исходников репозитория. Релизные сборки публикуются отдельно через **GitHub Releases**.

## Сборка

Проект использует **.NET 8**, WPF и WebView2. Для локальной сборки под Windows используется `BUILD-EXE.cmd`.

Публичный файл формируется в виде:

```text
Owl-IN-ServiceKit-x.y.z.exe
```

## Документация

- [`CHANGELOG.md`](CHANGELOG.md) — история версий;
- [`ROADMAP.md`](ROADMAP.md) — рабочий список задач, который может меняться по ходу разработки;
- [`SECURITY.md`](SECURITY.md) — подход к безопасности;
- [`docs/architecture.md`](docs/architecture.md) — текущая архитектура;
- [`docs/easy-mode.md`](docs/easy-mode.md) — Easy Mode;
- [`docs/expert-mode.md`](docs/expert-mode.md) — Expert Mode;
- [`docs/release-process.md`](docs/release-process.md) — выпуск релизов;
- [`docs/releases/1.0.4.md`](docs/releases/1.0.4.md) — примечания к выпуску 1.0.4;
- [`docs/releases/1.1.0.md`](docs/releases/1.1.0.md) — примечания к выпуску 1.1.0;
- [`docs/RELEASE-NOTES-1.3.0.md`](docs/RELEASE-NOTES-1.3.0.md) — примечания к текущему выпуску;

- [`docs/website.md`](docs/website.md) — отдельный сайт Owl-IN и его связь с Owl-IN ServiceKit.

Подробнее о диспетчере процессов и собственном сборе данных: [документация](docs/PROCESS-MONITOR.md).
