# Leads
1. Main - основной wrorkflow, catch - обработчик ошибок. Для подключения обработчика в Main переходим wrorkflow - settings - Error Workflow выбираем catch.
2. Создаем переменную(variables) key: tgChatId value: id tg чата для уведомлений.
3. Добавить Credentials можно 2-мя путями: через node в Main, связанный с приложением к которому требуется доступ, либо через Creat Credentials в проекте:
	- google sheets: Google Sheets OAuth2 API - connection - sign in with Google вводим УЗ.
	- telegram: Telegram API - connection - Access Token(Вводим бот токен)
	- openai: OpenAi - connection - API Key(Вводим OpenAi API Key)
4. Webhook URL расположен в Main - Webhook - Production URL(Test URL для разового запуска на тестирование)
5. Примеры curl для тестирования:
	Корректный:
	 curl -X POST <Webhook_URL> \
	  -H "Content-Type: application/json" \
	  -d '{"name":"Анна","email":"anna@mail.ru","message":"Интересует Rolex Submariner"}'
	Неккоректный email:
	 curl -X POST <Webhook_URL> \
	  -H "Content-Type: application/json" \
	  -d '{"name":"Анна","email":"123","message":"Интересует Rolex Submariner"}'
	Отсутствует message: 
	 curl -X POST <Webhook_URL> \
	  -H "Content-Type: application/json" \
	  -d '{"name":"Анна","email":"anna@mail.ru","message":""}'
	Brand = none:
	 curl -X POST <Webhook_URL> \
	  -H "Content-Type: application/json" \
	  -d '{"name":"Анна","email":"anna@mail.ru","message":"Интересуют новые часы"}'