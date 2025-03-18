## Клонируем репозиторий, собираем его на сервере srv

* Склонировал тестовое [приложение](https://github.com/vinhlee95/django-pg-docker-tutorial),
* [Поправил](https://github.com/skillfactory-devops/02_deploy/commit/3fb74efcc6ac5a86e9e30ce03d3d6a706aa8cd66) пару мелких ошибок,
* Вынес чувствительные переменные среды приложения в отдельный файл,
* Убедился с помощью `docker-compose up`, что приложение работоспособно.

Теперь время автоматизировать сборку и публикацию образа.

* [Создал](https://github.com/settings/tokens) Persoanal access token для дальнейшей работы с Github Container Registry,
* Убедился, что с ним можно залогиниться в реестре `echo $TOKEN | docker login ghcr.io -u USERNAME --password-stdin`,
* Прописал его в секреты организации,
* Зарегистрировал локальный Github Runner для текущей организации и настроил его запуск как службу,
* Написал workflow, срабатывающий при появлении новых коммитов в организации.

