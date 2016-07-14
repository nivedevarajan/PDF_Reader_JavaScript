# pdf-reader-js

Наш текущий функционал:
- режим чтения
- режим конспектирования (возможно выделение)
- создание цитаты (она формируется на сервере по специальным правилам)
  читалка должна передать номер страницы, ид книги и выделенный текст
- масштабирование (с запоминанием масштаба при пролистывании)
- автоматическое масштабирование по высоте/ширине
- индикация и управление закладками
- переход на произвольную страницу книги
- отображение сообщений от сервера

В данный момент алгоритм работы такой:
1. читалка формирует запрос на сервер: ид книги + номер страницы + желаемая версия (для чтения или для цитирования)
   сервер отвечает в формате json или xml
   в ответе указывается доступность страницы в выбранном формате, если страница не доступна - то код сообщения для отображения пользователю
   + некоторые другие параметры (положена ли страница в закладки например)
2. в случае положительно результата в п.1 читалка загружает файл страницы и показывает его.
3. для перехода в режим цитирования пункты 1, 2 повторяются
