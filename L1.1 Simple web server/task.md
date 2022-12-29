Задача:
Написать сервлет, который будет обрабатывать запросы на /mirror
При получении GET запроса с параметром key=value сервлет должен вернуть в response строку содержащую value.
Например, при GET запросе /mirror?key=hello сервер должен вернуть страницу, на которой есть слово "hello".

Инструкция подготовки к локальной проверке:
Соберите сервер со всеми зависимостями на библиотеки в server.jar
Для этого запустите Maven projects/<Project name>/Plugins/assembly/assembly:single
либо assembly.sh (assembly.bat)

Скопируйте server.jar на уровень src и запустите
java -jar server.jar

В логах консоли вы должны увидеть сообщения о старте сервера.
Проверьте, что сервер отвечает на запросы браузера.

Инструкция подготовки к автоматической проверке:
Добавьте в лог сообщение "Server started". По появлению в логе этого сообщения тестирующая система пойдет, что к вашему серверу можно обращаться.
Соберите server.jar содержащий все библиотеки.

Во время проверки тестовая система запускает ваш сервер, ждет пока "Server started", посылает GET запрос на 
http://localhost:8080/mirror?key=value
и проверяет, что в ответ пришла страница содержащая только 
value

---

# Решение
1. Изменить в файле `sfg/test.prperties` `startWaitPeriod: 1000` -> `startWaitPeriod: 8000`
2. Вставить в Main после `server.start();` -> `java.util.logging.Logger.getGlobal().info("Server started");`
3. Собрать проект `assembly.sh`
4. Запустить проект `java -jar server.jar`
5. http://localhost:8080/mirror?key=value
6. Запустить тест и получаем ключ в терминале `java -jar tester.jar`