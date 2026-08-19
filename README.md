<div align="center">

# Ryazha-clk

### Русский оверлей и sysmodule управления частотами Nintendo Switch Mariko

[![Последний релиз](https://img.shields.io/github/v/release/Dimasick-git/Sys-clk?label=%D1%80%D0%B5%D0%BB%D0%B8%D0%B7&style=for-the-badge)](https://github.com/Dimasick-git/Sys-clk/releases/latest)
[![Исходная сборка](https://img.shields.io/github/actions/workflow/status/Ryazhenka-Makers/RCU/build.yml?branch=main&label=%D1%81%D0%B1%D0%BE%D1%80%D0%BA%D0%B0&style=for-the-badge)](https://github.com/Ryazhenka-Makers/RCU/actions/workflows/build.yml)
[![Лицензия](https://img.shields.io/badge/license-GPL--2.0-blue?style=for-the-badge)](https://github.com/Ryazhenka-Makers/RCU/blob/main/LICENSE)

[Скачать последний пакет](https://github.com/Dimasick-git/Sys-clk/releases/latest/download/Ryazha-clk.zip) · [Все релизы](https://github.com/Dimasick-git/Sys-clk/releases) · [Исходный код RCU](https://github.com/Ryazhenka-Makers/RCU)

</div>

---

## О проекте

**Ryazha-clk** — распространяемый SD-ready пакет для управления CPU, GPU, RAM, профилями приложений и совместимыми экранными режимами на Nintendo Switch **Mariko** под Atmosphère. Внутри находятся загрузочный KIP, sysmodule, оверлей, шаблон конфигурации и языковые файлы. Интерфейс ориентирован на русскоязычное использование в Ryazhahand.

Проект собирается только из [Ryazhenka-Makers/RCU](https://github.com/Ryazhenka-Makers/RCU). Этот репозиторий хранит публичные релизы и постоянную пользовательскую документацию; бинарные файлы вручную сюда не загружаются.

> **Предупреждение.** Частоты, напряжения и тайминги памяти могут вызвать зависания и потерю данных. Перед использованием создайте резервные копии NAND, PRODINFO, emuMMC и SD-карты. Любые изменения выполняются на ваш риск.

## Установка

1. Скачайте **[`Ryazha-clk.zip`](https://github.com/Dimasick-git/Sys-clk/releases/latest/download/Ryazha-clk.zip)** из последнего release.
2. Распакуйте архив в **корень SD-карты**, разрешив объединение папок `atmosphere`, `config` и `switch`.
3. Используйте совместимую Atmosphère и Ryazhahand или Tesla-совместимый менеджер оверлеев.
4. Полностью перезагрузите консоль, затем откройте `ryazha-clk.ovl`.

Архив не нужно распаковывать в отдельную вложенную папку. Его структура уже готова для SD-карты.

| Внутри `Ryazha-clk.zip` | Назначение |
|---|---|
| `atmosphere/kips/rcu.kip` | Boot-патчер RCU. |
| `atmosphere/contents/.../exefs.nsp` | Sysmodule Ryazha-clk. |
| `switch/.overlays/ryazha-clk.ovl` | Русскоязычный оверлей. |
| `config/ryazha-clk/` | Шаблон настроек и языковые файлы. |
| `config/ryazhahand/assets/notifications/rcu.rgba` | Ресурс уведомлений Ryazhahand. |

## Возможности

Ryazha-clk содержит профили частот для игр и глобальных режимов, мониторинг, ограничения TDP и температуры, частоты CPU/GPU/RAM и на совместимых конфигурациях — Ryazha-Авто по FPS и настройки экрана/VRR. Для работы автоматического режима нужен валидный FPS от SaltyNX.

Названия, доступность и безопасный диапазон пунктов зависят от прошивки, модели консоли, активного профиля и установленных компонентов CFW. Не применяйте экспериментальные параметры без понимания их назначения.

## Автоматические релизы

Номер версии задаётся в RCU одной строкой `APP_VERSION`. Например, изменение на `APP_VERSION := 3.0.1` и push в `main` автоматически создаёт здесь release **`v3.0.1`** и публикует проверенный `Ryazha-clk.zip`. При неизменной версии существующий release не перезаписывается.

| Событие в RCU | Поведение Sys-clk |
|---|---|
| Новый `APP_VERSION` в `main` | Новый тег и release с тем же номером. |
| Обычный commit без изменения версии | Сборка выполняется, release не меняется. |
| Ручное исправление asset | Допускается только отдельным принудительным запуском workflow. |

Такой порядок сохраняет историю релизов и не смешивает разные сборки под одним тегом.

## Документация

| Документ | Содержание |
|---|---|
| [Памятка по кнопкам и меню](RYAZHA-CLK-USER-GUIDE.md) | Основные экраны, кнопки и режим Ryazha-Авто. |
| [Заметки v3.0.0](RELEASE_NOTES_3.0.0.md) | Исторический список изменений ветки 3.0. |
| [RCU: параметры и сборка](https://github.com/Ryazhenka-Makers/RCU) | Полный технический справочник, версия и CI-процесс. |

## Благодарности и лицензия

Ryazha-clk основан на работах Horizon OC, hoc-clk, sys-clk, Atmosphère, libnx, SaltyNX, Ultrahand/libtesla и сообщества Nintendo Switch. Исходные компоненты распространяются на условиях GPL-2.0; учитывайте лицензии upstream-проектов при повторном использовании.
