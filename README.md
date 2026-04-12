<div align="center">

# Ryazha-clk

### Кастомный sys-clk для Nintendo Switch · русский интерфейс · умный авторазгон

[![Release](https://img.shields.io/github/v/release/Dimasick-git/Sys-clk?label=релиз&style=for-the-badge)](https://github.com/Dimasick-git/Sys-clk/releases)
![License](https://img.shields.io/badge/license-GPL--2.0-blue?style=for-the-badge)

**Ветка 3.x** — сборка на базе **Horizon OC / hoc-clk** с расширенным **Ryazha-Авто**, авто **VRR** и интеграцией **SaltyNX**.

[Скачать релиз](https://github.com/Dimasick-git/Sys-clk/releases) · [Issues](https://github.com/Dimasick-git/Sys-clk/issues)

</div>

---

## Что это

**Ryazha-clk** — сисмодуль и оверлей для управления частотами **CPU / GPU / RAM** и режимом экрана на **Atmosphere**. В этом форке интерфейс и документация ориентированы на русскоязычных пользователей; ядро логики развито в сторону **автоматической подстройки под FPS** и **переменной частоты развёртки (VRR)** в портативе.

---

## Версия 3.0.0 — основное

| Направление | Содержание |
|-------------|------------|
| **Ryazha-Авто** | Автоподбор частот по **реальному FPS** (данные **SaltyNX**). Без валидного FPS авто **не вмешивается**. |
| **Меню** | Скрытое меню авторазгона по кнопке **X** на главном экране оверлея; пункт «О программе» убран; переименованы профили. |
| **GPU / CPU** | По FPS — **цепочки шагов** (нарастающие пачки) вверх и вниз; **±1** к размеру пачки от отклонения FPS от цели. Термо и TDP — по-прежнему **один шаг** за событие. |
| **Полы частот** | Зависят от **целевого FPS**: 30 FPS → **307 / 918** МГц (GPU/CPU); 45 / 60 / 60+ → **460 / 1020** МГц. GPU не ниже **307** МГц. |
| **Пресет 60+** | Цель для логики авто: **64 FPS** на **OLED (Aula)** и **71 FPS** на остальных панелях (согласовано с потолком VRR). |
| **TDP / температуры** | Порог **TDP** (мВт), лимиты **°C** для CPU/GPU (диапазон **30–80°C**), без управления вентилятором из меню авто. |
| **Кэп игры** | Детект принудительного лимита FPS (кат-сцены, меню): по **FPSlocked**, низкой нагрузке GPU, «липкому» FPS — без лишнего разгона. |
| **VRR** | При активном Ryazha-Авто включается **VRR Авто**; в меню есть пояснение. |
| **RAM** | В авто — **максимум** в рамках профиля. |

Подробная пользовательская памятка по кнопкам: файл **`RYAZHA-CLK-USER-GUIDE.md`** в архиве релиза. Техническая сводка: **`RYAZHA-CLK-SVODKA.md`**.

---

## Совместимость

| Компонент | Примечание |
|-----------|------------|
| **Прошивка** | [Atmosphere](https://github.com/Atmosphere-NX/Atmosphere) |
| **Оверлей** | [Ultrahand](https://github.com/ppkantorski/Ultrahand-Overlay) или совместимые менеджеры оверлеев |
| **FPS для авто** | [SaltyNX](https://github.com/masagrator/SaltyNX) как sysmodule — для Ryazha-Авто желателен патченный вариант из экосистемы Horizon OC (общий блок FPS / `renderTickAvg` для лучшего VRR) |
| **KIP** | В дистрибутиве Horizon OC — **`hoc.kip` / `rcu.kip`** по инструкции сборки |

Связка **Ryazhenka** / **Ryazhahand** по желанию: [Ryzhenka](https://github.com/Dimasick-git/Ryzhenka), [Ryazhahand-Overlay](https://github.com/Dimasick-git/Ryazhahand-Overlay).

---

## Установка (кратко)

1. Скачайте архив **`dist`** из [Releases](https://github.com/Dimasick-git/Sys-clk/releases) для версии **3.0.0**.
2. Распакуйте в **корень SD-карты** (структура `atmosphere/`, `config/`, `switch/` и т.д.).
3. Установите зависимости (Atmosphere, SaltyNX при использовании авторазгона).
4. Перезагрузите консоль.

Полная схема путей и KIP — в **`README.md`** внутри архива дистрибутива и в документации [Horizon OC](https://github.com/Horizon-OC/Horizon-OC).

---

## Сборка из исходников

Исходный код **hoc-clk** входит в репозиторий **Horizon OC**. Сборка: **devkitPro (devkitA64)**, скрипты **`build.sh`** / **`pack_dist_only.sh`**, см. **`COMPILING.md`** в том репозитории.

---

## Отказ от ответственности

Разгон и смена частот **ОЗУ** могут повредить **NAND** или **карту памяти**. Делайте резервные копии. Используйте на **свой риск**.

---

## Благодарности

- **Horizon OC** — hoc-clk, губернатор VRR, интеграции.
- **retronx-team / sys-clk** — базовая архитектура.
- **masagrator** — SaltyNX.
- **Atmosphere** — SciresM и участники.
- Сообщество Switch — тесты и обратная связь.

---

## Лицензия

Исходный код **hoc-clk / sys-clk** в цепочке **Horizon OC** распространяется под **GPL-2.0**. Полный текст обычно в файле `LICENSE` в upstream-репозитории.

---

<div align="center">

**[Releases](https://github.com/Dimasick-git/Sys-clk/releases)** · **[Dimasick-git/Sys-clk](https://github.com/Dimasick-git/Sys-clk)**

*Ryazha-clk 3.0.0 — стабильная ветка описания функций авторазгона и VRR.*

</div>
