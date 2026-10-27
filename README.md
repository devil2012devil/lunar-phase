
<a name="readme-top"></a>

[![HASSFEST](https://github.com/ngocjohn/lunar-phase/actions/workflows/hassfest.yaml/badge.svg)](https://github.com/ngocjohn/lunar-phase/actions/workflows/hassfest.yaml) ![Загрузки GitHub (все версии)](https://img.shields.io/github/downloads/ngocjohn/lunar-phase/total?style=flat&logo=homeassistantcommunitystore&logoSize=auto&label=Загрузки&color=%2318BCF2) ![Загрузки GitHub (последний выпуск)](https://img.shields.io/github/downloads/ngocjohn/lunar-phase/latest/total?style=flat&logo=homeassistantcommunitystore&logoSize=auto)

# 🌘 Интеграция лунных фаз для Home Assistant

<img src="https://raw.githubusercontent.com/ngocjohn/lunar-phase/main/assets/lunar-header.gif" style="border-radius: 8px" />

##

<p style="text-align: justify;">Интеграция Lunar Phase — это пользовательский компонент для Home Assistant, который предоставляет подробную информацию о текущей фазе Луны. Она использует точные астрономические расчёты для получения достоверных данных о Луне. Интеграция будет полезна любителям астрономии, астрологии и всем, кто хочет отслеживать смену лунных фаз.</p>

## Возможности

- **Текущая фаза Луны**: отображает текущую фазу Луны.
- **Возраст Луны**: показывает возраст Луны в днях.
- **Расстояние до Луны**: показывает расстояние до Луны в километрах.
- **Освещённая доля Луны**: показывает долю освещённого диска Луны.
- **Освещённость от Луны**: расчётная освещённость от лунного света в люксах по модели Крисциунаса — Шефера (Krisciunas–Schaefer).
- **Восход и заход Луны**: отображает время восхода и захода Луны.
- **Следующие основные фазы**: показывает дату и время ближайшего новолуния, полнолуния, первой и последней четверти.
- **Положение Луны**: показывает высоту над горизонтом, азимут и параллактический угол Луны.
- **Следующее верхнее кульминирование Луны**: показывает время, когда Луна в следующий раз достигнет наивысшего положения над горизонтом.

<img src="https://raw.githubusercontent.com/ngocjohn/lunar-phase/main/assets/lunar-entities.png" alt="Сущности интеграции Lunar Phase">
<img src="https://raw.githubusercontent.com/ngocjohn/lunar-phase/main/assets/lunar-phase.png" alt="Атрибуты датчика лунной фазы">

## Дополните панель Home Assistant красивым отображением лунных фаз

> [!TIP]
> Если вы хотите добавить на панель Home Assistant наглядный и информативный индикатор лунных фаз, обратите внимание на мою пользовательскую карточку Lunar Phase Card. Она отображает подробную информацию о фазах Луны и легко интегрируется в существующую конфигурацию Home Assistant. Карточка подойдёт любителям астрономии и всем, кто хочет удобно и красиво отслеживать смену лунных фаз. Найти и установить Lunar Phase Card можно [здесь](https://github.com/ngocjohn/lunar-phase-card/).

<div style="display: flex; justify-content: space-around;">
  <img src="https://raw.githubusercontent.com/ngocjohn/lunar-phase/main/assets/lunar-default.png" alt="Карточки лунных фаз" width="48%" height="100%">
  <img src="https://raw.githubusercontent.com/ngocjohn/lunar-phase/main/assets/lunar-compact.png" alt="Календарь лунных фаз" width="48%" height="100%">
</div>

## Содержание

<details>
    <summary>Содержание</summary>

- [Возможности](#возможности)
- [Установка](#установка)
  - [Установка через HACS](#установка-через-hacs)
  - [Ручная установка](#ручная-установка)
- [Настройка](#настройка)
  - [Настройка через интерфейс Home Assistant](#настройка-через-интерфейс-home-assistant)
- [Описание датчиков](#описание-датчиков)
- [Участие в разработке](#участие-в-разработке)

</details>

## Установка

### Установка через HACS

1. Откройте настройки HACS и добавьте этот репозиторий в качестве пользовательского репозитория.
2. Найдите в HACS интеграцию `Lunar Phase` и установите её.
3. Перезапустите Home Assistant.

[![Открыть Home Assistant и перейти к репозиторию в HACS](https://my.home-assistant.io/badges/hacs_repository.svg)](https://my.home-assistant.io/redirect/hacs_repository/?owner=ngocjohn&repository=lunar-phase&category=Integration)

### Ручная установка

1. Скачайте папку `lunar_phase` из этого репозитория.
2. Скопируйте папку `lunar_phase` в каталог `custom_components` вашей установки Home Assistant. Каталог `custom_components` должен находиться на одном уровне с файлом `configuration.yaml`.
3. Перезапустите Home Assistant.

## Настройка

### Настройка через интерфейс Home Assistant

Чтобы настроить интеграцию Lunar Phase, выполните следующие действия:

1. Откройте панель Home Assistant.
2. Перейдите в раздел `Настройки` → `Устройства и службы` → `Добавить интеграцию`.
3. Найдите `Lunar Phase` и выберите её.
4. Откроется форма с предварительно заполненными данными о местоположении вашего дома в Home Assistant. При необходимости измените значения и отправьте форму:
   - **Название местоположения (Location Name)** — по умолчанию используется значение `location_name` из настроек Home Assistant. Это произвольное текстовое название.
   - **Широта (Latitude)** — предварительно заполнена координатами дома из настроек Home Assistant; значение можно изменить.
   - **Долгота (Longitude)** — предварительно заполнена координатами дома из настроек Home Assistant; значение можно изменить.

Регион и часовой пояс определяются автоматически на основании настроек Home Assistant и отдельно в форме не отображаются.

После настройки интеграция создаст датчик лунной фазы и дополнительные диагностические датчики, предоставляющие подробную информацию о Луне.

## Описание датчиков

| **Название** | **Описание** |
| --- | --- |
| `Moon Phase` | Отображает текущую фазу Луны, например новолуние, растущую Луну, первую четверть и другие фазы. |
| `Moon Age` | Показывает возраст Луны в днях. |
| `Moon Distance` | Показывает расстояние до Луны в километрах. |
| `Moon Illumination Fraction` | Показывает долю освещённого диска Луны. |
| `Moon Illuminance` | Показывает расчётную освещённость от лунного света в люксах. Если Луна находится ниже горизонта, значение равно `0.0`. |
| `Moon Rise` | Показывает время следующего восхода Луны. |
| `Moon Set` | Показывает время следующего захода Луны. |
| `Moon High` | Показывает время следующего верхнего кульминирования Луны. |
| `Next Full Moon` | Показывает дату следующего полнолуния. |
| `Next New Moon` | Показывает дату следующего новолуния. |
| `Next Third Quarter` | Показывает дату следующей последней четверти Луны. |
| `Next First Quarter` | Показывает дату следующей первой четверти Луны. |
| `Moon Altitude` | Показывает высоту Луны над горизонтом в градусах. |
| `Moon Azimuth` | Показывает азимут Луны в градусах. |
| `Moon Parallactic Angle` | Показывает параллактический угол Луны в градусах. |
| `Next Moon Phase` | Показывает следующую фазу Луны и дату её наступления. |

## Участие в разработке

Мы приветствуем вклад сообщества! Если у вас есть предложения, вы обнаружили проблему или хотите предложить новую функцию, [создайте обращение](https://github.com/ngocjohn/lunar-phase/issues) или отправьте запрос на внесение изменений (pull request).

### Участники

- [@ngocjohn](https://github.com/ngocjohn) — автор оригинальной интеграции.
- [@italo-lombardi](https://github.com/italo-lombardi) — улучшения в версии v0.3.0.

##

Наслаждайтесь отслеживанием лунных фаз с интеграцией Lunar Phase для Home Assistant!

&copy; 2024–2026 Viet Ngoc

[https://github.com/ngocjohn/](https://github.com/ngocjohn/)

<p align="right">(<a href="#readme-top">Вернуться к началу</a>)</p>
