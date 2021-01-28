# Шаблон для телеграм ботов
сделал [@Forden](https://github.com/Forden/aiogram-bot-template), модифицировал [@Latand](https://github.com/latand/aiogram-bot-template/), модифицировал модификацию [@w0rng](https://github.com/w0rng/template-telegram-bot).  

## Описание настроек  
`TG_TOKEN` - токен от бота в телеге  
`ADMINS` - список id админов через запятую (если 1, то запятую не надо)  
`DEBUG` - true или false, выводить или нет отладочную информацию в консоль. По умолчанию **_false_**   
`DATABASE` - url для подключения к БД, потом SQLAlchemy прикручу. По умолчанию **_memory_**.  
`DOMAIN` - домен для вебхуков. Если не задан, то используются логпул запросы. По умолчанию **_none_**  
`WEBAPP_PORT` - порт для вебхуков. Пол умолчанию **_5000_**  

## Отличие от оригинала
Самым главным нововведением и причиной создания форка является автоматическая загрузка модулей.  
В оригинальном шаблоне для создания новых хендлеров требовалось написать несколько новых импортов в `__init__` файлах. В данной версии шаблона не требуется писать ничего.
Аналогичная ситуация и с middleware слоем. Для добавление новой мидлвари не нужно писать `__init__` файлы, не нужно руками добавлять ее в Dispatcher.

## Как добавить новый хендлер?
Просто поместить файл `.py` в папку `handlers`. Он автоматически загрузится.

## Как добавить новый middleware?
Поместить модуль мидлвари в папку `middlewares` и добавить путь к классу в массив `INSTALLED_MIDDLEWARES`, находящийся в файле `config/installed_modules`

## Автоперезагрузка скрипта
Для удобной разработки был добавлен скрипт `auto-restart.sh`, который автоматически перезапускает бота при сохранении.