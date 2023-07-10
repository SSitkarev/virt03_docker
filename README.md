# Домашнее задание к занятию 3. «Введение. Экосистема. Архитектура. Жизненный цикл Docker-контейнера» - Ситкарёв Сергей

## Задача 1
Сценарий выполнения задачи:

создайте свой репозиторий на https://hub.docker.com;
выберите любой образ, который содержит веб-сервер Nginx;
создайте свой fork образа;
реализуйте функциональность: запуск веб-сервера в фоне с индекс-страницей, содержащей HTML-код ниже:
<html>
<head>
Hey, Netology
</head>
<body>
<h1>I’m DevOps Engineer!</h1>
</body>
</html>
Опубликуйте созданный fork в своём репозитории и предоставьте ответ в виде ссылки на https://hub.docker.com/username_repo.

[Ответ](https://hub.docker.com/r/ssitkarev/netology_nginx)

## Задача 2
Посмотрите на сценарий ниже и ответьте на вопрос: «Подходит ли в этом сценарии использование Docker-контейнеров или лучше подойдёт виртуальная машина, физическая машина? Может быть, возможны разные варианты?»

Детально опишите и обоснуйте свой выбор.

Сценарий:

высоконагруженное монолитное Java веб-приложение; - *Т.к. приложение монолитное, то лучше его установить на виртуальную или физическую машину.*
Nodejs веб-приложение; - *Для автоматизации лучше развернуть в докер контейнере, т.к. в случае с nodejs приложением требуется настраивать програмные зависимости, переменные среды, файлы конфигурации.*
мобильное приложение c версиями для Android и iOS; - *Судя по всему кейс с разработкой мобильного приложения. Поэтому, чтобы не пересобирать образы, лучше использовать виртуальную машину.*
шина данных на базе Apache Kafka; - *Для простоты, надёжности и доступности, можно собрать несколько докер контейнеров и объединить в кластер*
Elasticsearch-кластер для реализации логирования продуктивного веб-приложения — три ноды elasticsearch, два logstash и две ноды kibana; - *Так же для простоты, надёжности и доступности, можно собрать по несколько докер контейнеров для каждого приложения и объединить в кластеры
мониторинг-стек на базе Prometheus и Grafana; *И снова докер контейнеры*
MongoDB как основное хранилище данных для Java-приложения; - *Виртуальная или физическая машина, т.к. в данном случае ключевым фактором является надёжность. (На свойм опыте насобирал шишек с MongoDB в контейнерах)*
Gitlab-сервер для реализации CI/CD-процессов и приватный (закрытый) Docker Registry. - *Для простоты, надёжности и доступности больше подойдёт докер*

## Задача 3
Запустите первый контейнер из образа centos c любым тегом в фоновом режиме, подключив папку /data из текущей рабочей директории на хостовой машине в /data контейнера.
Запустите второй контейнер из образа debian в фоновом режиме, подключив папку /data из текущей рабочей директории на хостовой машине в /data контейнера.
Подключитесь к первому контейнеру с помощью docker exec и создайте текстовый файл любого содержания в /data.
Добавьте ещё один файл в папку /data на хостовой машине.
Подключитесь во второй контейнер и отобразите листинг и содержание файлов в /data контейнера.

![Задание3](https://github.com/SSitkarev/SSitkarev-9-01/blob/main/img/cpu_utilization.jpg)