C4.11 Практика VUE.js

В домашнем задании вы будете улучшать проект.

Фронтенд:

Сейчас алерт нельзя убрать. Надо добавить к нему крестик закрытия. Для этого можно повесить атрибут dismissible, но, возможно, этого может оказаться недостаточно. Вероятно, логику скрытия и показывания надо спрятать внутрь этого компонента.
Сейчас у нас слишком много форм. Можно было бы обойтись только одной на весь проект, что сделало бы код менее лапшеобразным.
В нашем коде никак не обрабатываются ошибки в запросах (методы error и finally в библиотеке axios). Это не очень хорошо, поэтому стоит что-нибудь с этим сделать.
Про компоненты и как с ними работать, когда их много, почитайте документацию.

Документация по Vue есть и на русском, но некоторые блоки могут быть ещё не переведены. В них могут отсутствовать некоторые важные детали. Старайтесь использовать англоязычную документацию.

Бэкенд

Самое очевидно: в нашем проекте сейчас нет никакого механизма сохранения задач.
Мы также недостаточно параноидально проверяем приходящие данные, например, в DELETE, а следовало бы.
Весь код описан в одном блоке, тогда как работу с "базой" стоило бы вынести в отдельный модуль.
Для хранилища в этом проекте вы можете использовать sqlalchemy, но мы рекомендуем закрепить использование localStorage и просто сохранять данные внутри компонент. Напоминаем, что в devtools есть раздел Application, позволяющий просматривать содержимое localStorage. Так как в этом блоке мы фокусируемся на фронтенд-технологиях, попробуйте решить задачу сохранения данных именно этим способом.

Код и результат работы вы можете или выложить на github как проект, или же опубликовать в github pages результат работы npm run build. Задача публикации результата на github pages после сборки проекта нетривиальна, поэтому рассматривайте эту часть как задание со звёздочкой. Ваша задача сделать работающий код и загрузить его в github.

Итого, вам требуется сделать следующее:

Добавить возможность сохранять задачи и их состояния (общее число; выполнена или нет; описания) между открытиями страницы (или в коде py, или через localStorage; лучше через localStorage)
Добавить счётчики выполненных и невыполненных задач в заголовок страницы до таблицы.
Добавить обработку входящих данных в приложение. Как минимум надо ограничить возможность делать запросы с невалидным ID. Даже когда мы используем только localStorage без бэкенда, на уровне кода фронтенда вам тоже надо проверять передаваемые id задач при вызове соответствующих действий из интерфейса.
(если вы используете backend на Python) Разнести код работы с базой и сам сервер по разным модулям и использовать sqlalchemy.
Добавить возможность закрыть любой используемый алерта во фронтенде.
