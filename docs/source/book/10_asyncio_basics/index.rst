.. raw:: latex

   \newpage

10. Основы модуля asyncio
=========================

Модуль asyncio можно разделить на две части: высокоуровневый интерфейс для пользователей,
которые пишут программы и низкоуровневый интерфейс для авторов модулей, библиотек
и фреймворков на основе asyncio. В книге рассматривается только первая часть и чаще всего,
вторая не понадобится.

Основная причина использования asyncio - улучшить время работы программы, уменьшив
время ожидания ответа от операций ввода-вывода. В эти моменты будет выполняться 
переключение на другие задачи.


Отличия от многопоточной работы:

* при работе с потоками, планировщик может прервать работу потока в любой момент,
  не всегда это "удобный" момент, поэтому надо явно указывать, что в какие-то моменты
  прерывать поток нельзя.
* при использовании asyncio работа идет в одном потоке
* при работы с сопрограммами, мы явно указываем в каком месте надо сделать переключение
* await приостанавливает работу текущей сопрограммы и вызывает указанный объект.
  То есть, если в текущей сопрограмме написано ``await run_coro``, текущая сопрограмма 
  останавливается и планирует запуск сопрограммы run_coro в цикле событий


.. toctree::
   :maxdepth: 1

   terms
   basics
   run_awaitables
   further_reading
   ../../exercises/10_exercises.rst
