## Клонируем репозиторий, собираем его на сервере srv

* Склонировал тестовое [приложение](https://github.com/vinhlee95/django-pg-docker-tutorial),
* [Поправил](https://github.com/skillfactory-devops/02_deploy/commit/3fb74efcc6ac5a86e9e30ce03d3d6a706aa8cd66) пару мелких ошибок,
* Вынес чувствительные переменные среды приложения в отдельный файл,
* Убедился с помощью `docker-compose up`, что приложение работоспособно.

Теперь время автоматизировать сборку и публикацию образа.

* Зарегистрировал локальный Github Runner для текущей организации и настроил его запуск как службу,
* Написал [workflow](https://github.com/skillfactory-devops/02_deploy/blob/master/.github/workflows/ci-cd.yaml), срабатывающий при появлении новых коммитов в репозитории,
* Отладил в нём сборку и публикацию образа в Github Registy,
* Сделал образ (package) публичным,
* Отладил сборку образа с тегами,
* Дописал в образ способ запуска приложения.


## Описываем приложение в Helm-чарт

* Сделал общее хранение секретов для обоих сервисов,
* Описал сервисы в чарте,
* Экспортировал приложение как NodePort.


## Описываем стадию деплоя в Helm

* Дописал в Github Workflow обновление приложения из Helm-чарта.
