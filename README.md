# Интеграция Битрикс24 и собственного мобильного приложения компании Nedvex. Тестирование REST API

## Описание проекта:<br>
В рамках проекта я протестировала API для управления записью на показ недвижимости, которое предоставляет функции просмотра свободных для записи слотов с последующей записью. Тестирование было сосредоточено именно на получении корректных слотов, свободных для записи. Цель тестирования — проверить корректность работы разных запросов, а также исправить ошибки.
#### Алгоритм работы в приложении:<br>
**1.** Агент выбирает в приложении объект недвижимости, типа показа (онлайн или офлайн) и дату<br>
**2.** Жмёт кнопку "записаться на показ"<br>
**3.** Отображается календарь<br>
  1. В календаре отмечены свободные слоты<br>
  2. Свободные слоты содержат в себе все свободные слоты всех менеджеров объекта (У Пети свободно с 9 до 13, у Васи с 13 до 14, у Коли с 16 до 19, отображаем 9-13 свободно, 13-14 свободно, 14-16 занято, 16-19 свободно, т.е объединяем слоты менеджеров )<br>
#### Особенности:<br>
За каждым объектом закреплено разное количество менеджеров<br>
У менеджеров может быть разный рабочий график<br>
У менеджеров могут пересекаться активности<br>
Есть 2 типа показов: онлайн - 1 час, офлайн - 1.5 часа<br>
При запросе слотов день в день не должны быть доступны прошедшие слоты<br>
## Инструменты:<br>
Postman, JSON, Google Sheets
## Результаты:<br>
+ Написано 28 тест-кейсов для проверок корректной обработки POST-запроса при разных условиях
  
![Тест-кейс и проверки API Nedvex 12 12 - Тест-кейсы_page-0002](https://github.com/user-attachments/assets/37a8baa4-cdda-4cd6-9bd8-e9edd5a46bd7)


+ В процессе тестирования было найдено 7 багов
+ В процессе тестирования были доработаны требования к разработке
