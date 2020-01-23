## Телеграм бот для отслеживания котировок со скользящим окном
[@TIPortfolioBot](https://t.me/TIPortfolioBot)

## Список возможностей

#### Отслеживание котировок

| Команда | Описание | Пример использования
| ------ | ------ | ------
| **/w <тикер> <порог>** | Добавить инструмент в список отслеживания | **/w AAPL 1%** Будет присылать уведомление каждый раз, когда цена на акцию Apple изменится на 1%<br>**/w TWTR =30** Пришлет уведомление, когда цена на акцию Twitter достигнет или пересечет $30
| **/wl** | Список отслеживаемых инструментов | 
| **/wd <тикер>** | Удалить инструмент из отслеживания | **/wd AAPL** Удалит все отслеживания за ценой на акции Apple

#### Глобальное отслеживание

| Команда | Описание | Пример использования
| ------ | ------ | ------
| **/watchglobal <порог%>** | Отслеживать все акции, уведомлять о росте и падении любой акции в пределах торговой сессии |
| **/gainers [число результатов\|порог%]** | Вывести список выросших акций за текущий день. По умолчанию выводит топ 15. | **/g 20** Выведет топ 20 выросших акций<br>**/g 5%** Выведет все акции, выросшие как минимум на 5%
| **/losers [число результатов\|порог%]** | Вывести список упавших акций за текущий день. По умолчанию выводит топ 15. | **/l 20** Выведет топ 20 выросших акций<br>**/l 5%** Выведет все акции, упавшие как минимум на 5%

#### Информация об инструменте

| Команда | Описание | Пример использования
| ------ | ------ | ------
| **/info <тикер\|figi\|название> [период]** | Вывести базовую информацию об инструменте и график изменения цены за указанный период | **/i AAPL** Выведет базовую информацию об акциях Apple<br>**/i macy 90d** Найдет инструмент M по подстроке из названия(Macy's) и выведет базовую информацию с графиком за 90 дней<br><br>**Правила задания периода:**<ul><li>1h - 1 час</li><li>2d - 1 дня</li><li>3w - 3 недели</li><li>1mb, 2mb, 3mb, 5mb, 10mb, 15mb, 30mb - размерность бара в 1, 2, 3, ... минут соответственно</li><li>1hb - размерность бара в 1 час</li><li>1db - размерность бара в 1 день</li><li>1wb - размерность бара в 1 неделю</li><li>1mob - размерность бара в 1 месяц</li></ul>

#### Информация о портфеле на брокере Тинькофф Инвестиции

`На данный момент Тинькофф не предоставляет возможности разграничивать права доступа для ключей, а также поддерживается работа только с основным счетом, без ИИС.
Используйте на свой страх и риск (ключ позволяет создавать заявки на покупку/продажу, теоретически можно напакостить, если ключ попадет в плохие руки)`

| Команда | Описание | Пример использования
| ------ | ------ | ------
| **/apikey** |Задать API ключ (см. как получить в [официальной документации](https://tinkoffcreditsystems.github.io/invest-openapi/auth/#_2)) |
| **/summary** | Сводка по прибыли в портфеле | Пример вывода:<br><br>RUB полученная прибыль:<br>+₽12345.67 (див 1234.56, ком 123.45, налог 432.1)<br>RUB потенциальная прибыль: +₽8765.4<br><br>USD полученная прибыль: +$3456.78 (див 45.67, ком 5.67, налог 7.89)<br>USD потенциальная прибыль: -$123.45<br><br>EUR полученная прибыль: €987.65 (див 0.00, ком 12.34, налог 0.00)<br>EUR потенциальная прибыль: +€567.89
| **/fullreport** | Детальные данные прибыли по открытым и закрытым позициям | Пример вывода:<br><br>...<br>VEON (BBG000QCW561)<br><br>Получено: -$0.18 (ком -$0.18)<br>В портфеле: $179.90<br>Потенциал: +$8.60 (+4.78%)<br><br>WB (BBG0065XPGX9)<br>2019/10/25 +$1.74 (+0.59%)<br>2020/01/08 +$8.52 (+6.17%)<br><br>Получено: +$9.80 (ком -$0.46)<br>В портфеле: $132.81<br>Потенциал: -$3.72 (-2.80%)<br>...