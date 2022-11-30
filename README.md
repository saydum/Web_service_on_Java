```
		APP
	 	 |
		 V
 	Архитектурно независимый byte code
  	  |			|
  	  V			V
	Linux	  Windows
```

Байт-код - это код после компиляции Java компилятором

Ключевые идеи
- Написанный код работает на всех устройства где установлена JVM
- Встроенный сборщик мусора
- Безопасность исполнения

Платформа Java
- Java Runtime Environment (JRE)
	- Java Virtual Machine (JVM)
	. Interpreter
	. Just-In-Time (JIT) compile
	. Byte code verifire
	. Garbage collector (GC)
		* Поиск ненужных объектов
		* Освобождение памяти
		! Анализ идет по ссылкам, если объект доходит до stack это значить что объект живой
		! Если не доходит(heap), то его удалит сборщик мусора
		(Сборщик мусора это часть JVM которая удаляет объекты, по ссылкам на которые, нельзя дойти до стека) 

	- Class Libreres

- Java Development Kit (JDK)
	- JRE
	- Java compile (Javac)
	. Превращает *.java в *.class
	. *.class можно собрать в *.jar (zip архив)

- Java editions
	- Java SE
	. Стандартная редакция
	. JVM + библиотека классов

	- Java EE
	. Java SE
	. Спецификация
	. API + runtime environment services

	- Java ME
	. Мобильные телефоны, бытовая техника

- Maven это система зависимостей и сборка проектов
	. pom.xml - содержит зависимости

- Jetty
	. connector	Принимает http запросы (request)
	. handler(s)	Возвращает (response)
	. ThreadPool 	pool потоков для обработки запросов

- Java Servlet
	- Servlet
	. Класс расширяющий возможности сервера 
	. как applet, только на web сервере 
	. java решение для создания динамических страниц
	. объект, который обрабатывает http запросы(request) и возвращает ответ (response) - html страницу
	
	- ServletContainer
	. часть web сервера, содержащая сервлеты связывает URL с сервлетом

- Шаблонизатор <freemarket>
```html
<body>
	<p> Имя пользователя: ${ userName } </p>
</body>
```
