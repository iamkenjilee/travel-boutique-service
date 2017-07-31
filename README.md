Aviasales Travel iOS SDK
=================
[![CocoaPods](https://img.shields.io/cocoapods/v/AviasalesSDK.svg)](https://cocoapods.org/pods/AviasalesSDK)
[![CocoaPods](https://img.shields.io/cocoapods/p/AviasalesSDK.svg)](https://cocoapods.org/pods/AviasalesSDK)
[![Travis](https://img.shields.io/travis/KosyanMedia/Aviasales-iOS-SDK/master.svg)](https://travis-ci.org/KosyanMedia/Aviasales-iOS-SDK)

#### README in [English](https://github.com/KosyanMedia/Aviasales-iOS-SDK/blob/master/README_EN.md)  

## Описание

[Aviasales](https://www.aviasales.ru) Travel iOS SDK — набор библиотек, позволяющий добавить поиск авиабилетов и отелей в ваше приложение. Когда пользователь покупает билет или бронирует отель, вы получаете вознаграждение. SDK используется при разработке официальных приложений Aviasales и Hotellook.

SDK включает в себя:

* две библиотеки для интеграции с поисковой системой поиска авиабилетов и отелей;
* шаблонный проект с пользовательским интерфейсом.

Вы можете использовать шаблонный проект для создания своего собственного поискового приложения. Чтобы отслеживать выплаты, посетите нашу партнерскую сеть — [Travelpayouts.com](https://www.travelpayouts.com/).

Узнайте подробнее о доходах в [Travelpayouts FAQ](https://support.travelpayouts.com/hc/ru/articles/203955613-Комиссия-и-выплаты).

## <a name="usage"></a>Использование шаблонного проекта
### 📲 Установка
1. Скачайте себе последний release (не beta) шаблонного проекта отсюда: [https://github.com/KosyanMedia/Aviasales-iOS-SDK/releases](https://github.com/KosyanMedia/Aviasales-iOS-SDK/releases).
2. Скачайте зависимости, выполнив команду ```pod install --repo-update``` в каталоге с шаблонным проектом.  
**После этого для работы с проектом используйте файл ```AviasalesSDKTemplate.xcworkspace```**.
3. Подставьте правильные значения партнерского токена и маркера в файле ```Config.h``` в константы ```kJRAPIToken``` и ```kJRPartnerMarker```.
4. Если у вас еще нет партнерского маркера и токена, получите их в [Travelpayouts](https://travelpayouts.com/).

### 📱 Поддержка версий iOS
Поддерживаются версии, начиная с iOS 9.0

### 🖼 Иконка приложения
**Не забудьте заменить иконку приложения** (по умолчанию, в шаблоне используются иконки, залитые белым цветом). Для этого в папке ```AviasalesSDKTemplate/Resources/App.xcassets/AppIcon.appiconset``` достаточно заменить картинки (20.png, 29.png, 40.png и т.д.) на свои с аналогичными именами.

### ✈️🏨 Выбор вкладок
Если вы хотите убрать вкладку поиска билетов или поиска отелей, поменяйте значения TICKETS_ENABLED или HOTELS_ENABLED на 0 в разделе "Build Settings" в настройках проекта. Вкладку настроек убрать таким способом нельзя.

### 🇺🇸🇷🇺 Локализация
Локализации для текстов можно настроить через установку NSLSKey в разделе "Attributes Inspector" в xib-файлах.

### 🔧🌻 Настройка цветов
Выбрать цветовую схему можно в файле ColorSchemeConfigurator.swift. Достаточно прописать в переменной currentColorScheme одно из значений BlackColorScheme() / BlueColorScheme() / PurpleColorScheme(). Или установить значение CustomColorScheme() и настроить схему по своему усмотрению в файле CustomColorScheme.swift.
Внешний вид и цвета элементов тоже можно настроить в xib-файлах. Смотрите доступные для изменения поля в разделе "Attributes Inspector". В качестве ключей для цветов можно использовать любые значения из JRColorScheme.h.

Вот список основных полей с пояснениями:

|Название|Описание|
|--------|--------|
tintColor | Цвет всех кнопок и иконок в приложении
searchFormTintColor | Цвет иконок и кнопок на формах поиска
navigationBarBackgroundColor | Цвет панели навигации
navigationBarItemColor | Цвет элементов в панели навигации
searchFormBackgroundColor | Цвет фона в формах поиска
searchFormTextColor | Цвет текстов в формах поиска
searchFormSeparatorColor | Цвет разделительных полосок в формах поиска
mainButtonBackgroundColor | Фоновый цвет кнопок "Найти" в формах поиска
mainButtonTitleColor | Цвет текста на кнопках "Найти" в формах поиска

Если вам нужно больше настроек, например, цвета индикатора загрузки фотографий отелей или цвета элементов в фильтрах, воспользуйтесь настройками в файле JRColorScheme.m.

### 🤑 Настройка рекламы Appodeal
Для того чтобы вы могли получать дополнительную прибыль с рекламы, мы интегрировали в приложение рекламный SDK [Appodeal](https://www.appodeal.com/). Для его настройки задайте параметр **kAppodealApiKey** в файле **Config.h** (получите ключ API, зарегистрировавшись в [Appodeal](https://www.appodeal.com/)).

По умолчанию, реклама будет отображаться на экранах ожидания поиска билетов и отелей.

Для тестирования рекламы включите тестовый режим **kAppodealTestingMode** в файле **Config.h**. Тестовый режим будет работать только в **Debug** конфигурации.

Если вы не хотите, чтобы ваши пользователи видели рекламу, выставите **NO** для **kShowAppodealAds**, а **kAppodealApiKey** просто оставьте пустым.

### ⭐️ Обратная связь и оценка приложения
Задайте значения параметрам **kContactUsEmail** и **kAppStoreRateLink** в файле **Config.h** чтобы активировать пункты меню "Написать нам письмо" и "Оценить приложение".

## 🏭 Использование Fabric/Crashlytics
В шаблонное приложение встроена библиотека **Fabric/Crashlytics**, которая позволяет отслеживать крэши в приложении, а также рассылать тестовые сборки. Чтобы активировать эти функции, вам необходимо зарегистрироваться и получить **API Key** и **Build Secret** на сайте https://fabric.io. Далее необходимо:
1) Прописать соответствующие значения в файле **fabric.sh** в корневой папке
2) Прописать **Fabric > APIKey** в файле **AviasalesSDKTemplate-Info.plist**
