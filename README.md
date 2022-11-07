# customer-support-chatbot

Реализация чат-ботов поддержки клиентов с использованием сервиса Dialogflow на Google Cloud Platform.

Dialogflow — это сервис, позволяющий создавать чат-ботов для разных платформ и языков на разных устройствах. Принимая запрос в виде текста на естественном языке или некого события, Dialogflow согласовывает запрос с наиболее подходящим шаблоном. При этом он основывается на информации, содержащейся в шаблоне (примеры, сущности, контекст, параметры) и машинном обучении. Dialogflow  формирует ответный запрос и возвращает данные в виде объекта ответа JSON.


## Создание агента в DialogFlow

"Агент" — это что-то вроде "бота" в Telegram, только в DialogFlow.  

Для начала нужно создать аккаунт в Google Cloud Platform: [https://console.cloud.google.com/].  

После создания аккаунта в Google Cloud Platform создаем проект.

После создания проекта в создаем проект в сервисе DialogFlow: https://cloud.google.com/dialogflow/docs/quick/setup.

Далее нужно создать агента через консоль DialogFlow: [https://cloud.google.com/dialogflow/docs/quick/build-agent]. 
При создании агента выбираем язык, на котором будем общаться с пользователями. Так же при создании агента понадобится идентификатор проекта Google Cloud Platform.  


## "Обучение" бота

Для обучения бота создайте новый __Intent__ и добавьте несколько тренировочных фраз в секции __Training phrases__. Чтобы бот что-то ответил, ему нужно добавить текст ответа в секции __Response__. Затем можно попробовать пообщаться с ботом в меню слева-сверху.

Чтобы бот хорошо натренировался, фразы должны быть разными. 

Так же можно "обучить" бота с помощью скрипта ```create_dialogflow_intent.py```. Для этого нужно указать путь до файла с тренировочными фразами и ответами. Пример запуска:
```bash
$ python create_dialogflow_intent.py intents/questions.json  
```

## Запуск бота на сервере

Для размещения бота можно использовать платформу [Heroku](https://www.heroku.com/).

