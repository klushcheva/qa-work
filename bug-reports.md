## Баг-репорты
### Android

<details>
<summary>[CHART-3013] Android - Таймер свечи в первой сессии не синхронизирован с серверным временем</summary>
<br>

**Project**: Chart | **Components**: Android
  
**Affects Version/s**: 7.14 | **Fix Version/s**: 7.14
  
**Type**: Bug | **Priority**: High
  
**Assignee**: […] | **Reporter**: Kseniia Lushcheva
  
**Resolution**: Done

**Description**:

>Предусловия: 
>- Версия библиотеки графика 3.1.3
>- Баг воспроизводится только для первой сессии пользователя на девайсе. Нужно переустанавливать билд, чтобы воспроизвести повторно
>
>Шаги: 
>1. Запустить билд впервые, авторизоваться
>2. Перейти с зонного графика на свечной
>
>ОР: Корректно отображается свечной график и 15 секундный таймер свечи
>
>ФР: Несколько секунд висит пустая плашка таймера, затем либо: 1) таймер застревает на 15 секундах; либо: 2) таймер начинает тикать, но не синхронно с >серверным временем. Свечи продолжают формироваться корректно

</details>

<details>
<summary>[LVLS-2762] Android - Безрисковые сделки - Количество доступных сделок у юзера не синхронизировано</summary>
<br>
  
**Project**: LVLS | 
**Components**: Android
  
**Affects Version/s**: 8.17 | 
**Fix Version/s**: 8.17

**Type**: Bug | 
**Priority**: Medium
  
**Assignee**: […] | 
**Reporter**: Kseniia Lushcheva

**Resolution**: Done

**Description**:

>Шаги:
>1. Открыть платформу на web и на android
>2. Купить в маркете безрисковую сделку
>3. Использовать сделку в web клиенте
>4. Тапнуть на значок безрисковых сделок в терминале сделки клиента android
>
>ОР: Количество доступных сделок синхронизируется на всех клиентах
>
>ФР: На андроид клиенте не обновляется информация о количестве доступных сделок, если все сделки использованы на web клиенте, андроид продолжает показывать изначальное количество, при попытке использовать сделку сообщение об ошибке "Безрисковая сделка не найдена"
</details>

<details>
<summary>[MWAY-267] Android - Некорректный ресайз графика после перехода зонный-свечи</summary>
<br>

**Project**: Milkyway | **Components**: Library
  
**Affects Version/s**: 3.2.7 | **Fix Version/s**: 3.2.7
  
**Type**: Bug | **Priority**: High
  
**Assignee**: […] | **Reporter**: Kseniia Lushcheva
  
**Resolution**: Done

**Description**:

>Предусловие: 
>- Библиотека 3.2.7
>
>Шаги:
>1. Выбрать зонный график, таймфрейм 12 часов и больше
>2. Переключиться на свечной график
>3. Приблизить-удалить график, промотать к началу истории
>
>ОР: Свечной график корректно отображается после перехода с зонного
>
>ФР: График обрезается с левой стороны, по мере отдаления свечи пропадают

</details>

### Backend

<details>
<summary>[LVLS-2614] Backend - Триалки - В маркет передается неверная дата списания средств</summary>
<br>

**Project**: LVLS | **Components**: Backend
  
**Type**: Bug | **Priority**: Medium
  
**Assignee**: […] | **Reporter**: Kseniia Lushcheva
  
**Resolution**: Done

**Description**:

>Шаги:
>1. Добавить пользователя в А/Б тест триалок
>2. Пойти в маркет
>3. Активировать триалку для какой-нибудь стратегии в маркете
>4. Сравнить дату в пуше и дату на карточке товара
>
>ОР: Дата списания средств - +2 дня к моменту активации триалки
>
>ФР: Дата списания средств в маркете - +1 день к моменту активации триалки

</details>

<details>
<summary>[LVLS-2933] Backend - Маркет - Десинхронизация рейтинга некоторых фич</summary>
<br>

**Project**: LVLS | **Components**: Backend
  
**Type**: Bug | **Priority**: Medium
  
**Assignee**: […] | **Reporter**: Kseniia Lushcheva
  
**Resolution**: Unresolved

**Description**:

>Шаги:
>1. Подключиться к девкбосу по ssh
>2. Отправить запрос /v1/marketplace/features/details с body: {"id: 455"}
>3. Отправить запрос /v1/marketplace/categories
>4. Сравнить поля rating в телах ответов
>
>ОР: Значение рейтинга совпадает в ответах ручек
>
>ФР: Значение рейтинга для некоторых фич не синхронизуется между этими ручками
  
</details>

<details>
<summary>[LVLS-2942] Backend - Торговые сигналы - Не приходит 137 событие после покупки сигналов</summary>
<br>

**Project**: LVLS | **Components**: Backend
  
**Type**: Bug | **Priority**: Medium
  
**Assignee**: […] | **Reporter**: Kseniia Lushcheva
  
**Resolution**: Done

**Description**:
  
>Предусловие: открыть консоль с вебсокетом otp, отфильтровать по тексту "e":137
>
>Шаги:
>1. Зайти в маркет, вкладка торговые сигналы
>2. Купить любые торговые сигналы
>3. Открыть меню торговых сигналов
>
>Ожидаемый результат: в сокет приходит 137 событие (/137/trading_signals:timeframes:v3)
>
>Фактический результат: в сокет не приходит 137 событие  
  
</details>

### iOS

<details>
<summary>[LVLS-2609] iOS - Торговые стратегии - Не работает предупреждение при переключении на механику, не соответствующую механике активной стратегии</summary>
<br>

**Project**: LVLS | **Components**: iOS
  
**Affects Version/s**: 9.1 | **Fix Version/s**: 9.1
  
**Type**: Bug | **Priority**: Medium
  
**Assignee**: […] | **Reporter**: Kseniia Lushcheva
  
**Resolution**: Done

**Description**:

>Предусловие: у пользователя включена FX или FTT стратегия (но не FTT&FX)
>
>Шаги:
>1. Перейти на экран ассетов
>2. Сменить механику на противоположную (FTT -> FX / FX -> FTT)
>
>ОР: Появляется поп-ап предупреждение о том, что если сменить механику, стратегия будет выключена. Если подтвердить действие - произойдет смена механики и стратегия отключится
>
>ФР: Предупреждение не появляется. Происходит смена механики, при этом стратегия остается активной 

</details>

<details>
<summary>[LVLS-2976] iOS - Торговые сигналы - При смене ориентации экрана съезжают таймфреймы в bottom sheet</summary>
<br>

**Project**: LVLS | **Components**: iOS
  
**Affects Version/s**: 9.5 | **Fix Version/s**: 9.5
  
**Type**: Bug | **Priority**: Medium
  
**Assignee**: […] | **Reporter**: Kseniia Lushcheva
  
**Resolution**: Done

**Description**:

>Шаги:
>1. Открыть торговые сигналы 
>2. Открыть выбор таймфреймов 
>3. Смени ориентацию экрана на горизонтальную 
>4. Вернуть ориентацию экрана в вертикальное положение
>
>ОР: <img src="https://github.com/klushcheva/qa-work/blob/main/assets/2976_%D0%B1%D1%8B%D0%BB%D0%BE.png" alt="ER" width="200"/> ФР: <img src="https://github.com/klushcheva/qa-work/blob/main/assets/2976_%D1%81%D1%82%D0%B0%D0%BB%D0%BE.png" alt="AR" width="200"/>
</details>

### Web

<details>
<summary>[LVLS-2797] Web - Маркет - Нет кнопки депозита если у пользователя недостаточно средств и выбран демо счет</summary>
<br>

**Project**: LVLS | **Components**: Web
  
**Type**: Bug | **Priority**: Medium
  
**Assignee**: […] | **Reporter**: Kseniia Lushcheva
  
**Resolution**: Done

**Description**:

>Предусловия:
>- Выбран демо счет
>- На реальном счете нет денег
>
>Шаги: 
>1. Открыть маркет, любую категорию (например, торговые сигналы)
>2. Выбрать товар (например, Minor swing)
>3. Попытаться купить
>
>Ожидаемый результат: Появляется текст о том, что недостаточно средств + кнопка депозита под реальным счётом на вкладке маркета
>
>Фактический результат: Нет текста и кнопки; [см. видео](https://github.com/klushcheva/qa-work/blob/main/assets/2797.mov)
</details>

<details>
<summary>[LVLS-2965] Web - Торговые стратегии - Стратегии не всегда обновляются</summary>
<br>

>Сейчас после перезагрузки страницы при открытии инструментов торгового анализа один раз запрашивается https://api.olymptrade.com/v1/strategy-presets/list, при дальнейших переходах в стратегии мы не получаем актуальную информацию, так как больше не совершается запрос до перезагрузки страницы 
>
>Предусловие: инструменты торгового анализа открывались ранее
>
>Шаги:
>1. Купить стратегию/бандл стратегий в маркете/выдать через back office/получить со статусом
>2. Перейти на экран стратегий
>
>Ожидаемый результат: новые полученные стратегии отображаются доступными на клиенте
>
>Фактический результат: информация о стратегиях на клиенте не обновилась
</details>

<details>
<summary>[TD-2122] Web - Профиль - Иконка профиля выглядит не по дизайну</summary>
<br>

**Project**: LVLS | **Components**: Web
  
**Type**: Bug | **Priority**: Medium
  
**Assignee**: […] | **Reporter**: Kseniia Lushcheva
  
**Resolution**: Done

**Description**:

>Предусловие: авторизоваться на платформе
>
>Шаги:
>1. Посмотреть на иконки профиля и уровня сервиса в правом верхнем углу
>
>Ожидаемый результат: 1) иконки профиля и уровня сервиса "склеены" вместе 2) цвет фона уровня сервиса 1B1D21 <img src="https://github.com/klushcheva/qa-work/blob/main/assets/2122_%D0%B1%D1%8B%D0%BB%D0%BE.png" alt="ER" width="200"/>
>
>Фактический результат: 1) иконки профиля и уровня сервиса разъехались 2) цвет фона уровня сервиса 0E0F13 <img src="https://github.com/klushcheva/qa-work/blob/main/assets/2122_%D1%81%D1%82%D0%B0%D0%BB%D0%BE.png" alt="ER" width="200"/>

</details>

## Задачи
<details>
<summary>[AQA-4657] Web - Адаптировать тесты в маркете</summary>
<br>

**Project**: Auto QA | **Components**: Web
  
**Type**: Task | **Priority**: Medium
  
**Assignee**: […] | **Reporter**: Kseniia Lushcheva
  
**Resolution**: Done

**Description**:
  
> В задаче LVLS-2620 поменялся UI маркета. Теперь главная страница маркета - список категорий фичей.
>Добавляем дополнительные шаги в тесты с помощью новых локаторов в задаче LVLS-2663
>1. com.olymptrade.qa.platform.tests.deeplink.LevelsDeeplinkTest.checkDeeplinkMarketplace и com.olymptrade.qa.platform.tests.menu.SidebarMenuTest.checkSidebarNavigation - нужно проверять, что открылся маркет (cor-w-panel-marketPlaceCategories)
>2. 4 теста в com.olymptrade.qa.platform.tests.market.DeeplinksMarketTest, 5 тестов в com.olymptrade.qa.platform.tests.market.MarketAndStatusesTest, 6 тестов в com.olymptrade.qa.platform.tests.market.ViewPurchasedFeatureTest, 5 тестов в com.olymptrade.qa.platform.tests.market.MarketAndStatusesTest (без downgradeStatusToStarter и downgradeStatusToAdvanced):
>нужно 1) открывать маркет (cor-w-panel-marketPlaceCategories) 2) открывать инвентарь (mp-inventory-button)
>в downgradeStatusToStarter и downgradeStatusToAdvanced нужно заходить в маркет, выбирать категорию, и покупать фичу
>3. 3 теста в com.olymptrade.qa.platform.tests.market.MultiAccountMarketTest, 12 тестов в com.olymptrade.qa.platform.tests.market.BuyFeatureMarketTest, 18 тестов в com.olymptrade.qa.platform.tests.market.ViewFeatureMarketTest:
>нужно 1) открывать маркет (cor-w-panel-marketPlaceCategories) 2) открывать нужную категорию (mp-category-card) 3) в категории выбирать нужную фичу
>4. com.olymptrade.qa.platform.tests.menu.SidebarMenuTest.checkSidebarNavigation - нужно в шаге "проверка открытия маркета" поменять локатор на cor-w-panel-marketPlaceCategories
</details>

<details>
<summary>[LVLS-2080] iOS - Обрабатывать рестрикшен на покупки в маркетплейс на клиенте</summary>
<br>

**Project**: LVLS | **Components**: iOS
  
**Type**: Task | **Priority**: Medium
  
**Assignee**: […] | **Reporter**: Kseniia Lushcheva
  
**Resolution**: Done

**Description**:

>В задаче LVLS-2040 добавлен рестрикшен на покупку фичей в маркете, при выставленном рестрикшене marketplace_purchase на попытку покупки приходит ошибка:
>  {type: "Error", code: "purchase_restricted", msg: "purchase_restricted", internal_code: "zdcCtZl0UI"}
> Нужно обрабатывать эту ошибку на клиенте:
>- Анимация покупки не должна проигрываться
>- Сверху экрана должно появляться сообщение об ошибке

</details>

<details>
<summary>[LVLS-2579] Web - Торговые cигналы - Проверять, принял ли конкретный пользователь соглашение </summary>
<br>

**Project**: LVLS | **Components**: Web
  
**Type**: Task | **Priority**: Medium
  
**Assignee**: […] | **Reporter**: Kseniia Lushcheva
  
**Resolution**: Done

**Description**:
  
> В local storage в ключе tradingSignals хранится информация о том, принимал ли какой-либо пользователь в браузере пользовательское соглашение (user agreement) о использовании торговых сигналов, формат:
>  {"userAgreement":{"v":true,"ea":null}}
>
>Давайте проверять, принял ли конкретный пользователь соглашение, т.к. одним браузером могут пользоваться несколько людей, а легальную информацию об использовании сигналов стоит показывать каждому пользователю.
</details>
