# CI/CD

---

# CI/cd

---

# CI

---

# CI в КТБС

* Что было?

---

# CI в КТБС

* Что было?
* Что сейчас?

---

# CI в КТБС

* Что было?
* Что сейчас?
* Зачем то, что сейчас?! Я просто хочу программировать!

![crying-frog](images/crying-frog.png)

---

# CI в КТБС

* Что было?
* Что сейчас?
* Зачем то, что сейчас?! Я просто хочу программировать!
* Планы на будущее

---

# CI в КТБС (декабрь 2016)

* CI: buildbot (python 2.7)
* Targets: astra 1.5, windows(?)
* Internal tools: packaging, cprorab (c++/cmake), aptlier
* External tools: fpm, docker
* Storage: reprepro

---

# CI в КТБС (декабрь 2018)

* CI: buildbot (python 3)
* Targets: astra 1.5, ubuntu 16.04, docker, windows
* Internal tools: packaging, cprorab (c++/cmake), aptlier,
    package-description, testing, dockier
* External tools: fpm, docker
* Storage: aptly, docker registry, windows smb server

---

# CI в КТБС (февраль 2019)

* CI: buildbot (python 3), **gitlab-ci**
* Targets: astra 1.5, ubuntu 16.04, docker, windows
* Internal tools: packaging, cprorab (c++/cmake), aptlier,
    package-description, testing, dockier
* External tools: fpm, docker
* Storage: aptly, docker registry, windows smb server, **gitlab-pages**

---

# Buildbot vs Gitlab-CI

* Features

---

# Buildbot

## Pros:
* python
* гибкий
## Cons:
* не интегрирован в системы контроля версий
* нельзя исполнять команды в docker контейнере и использовать docker сервисы (из коробки)
* императивный
* много багов в страшном веб-интерфейсе
* медленно разрабатывается
* туманная документация
* позициионируется как сервер сборки одного (!) проекта
* сложно развернуть worker

---

# Зачем нам gitlab-ci?

![question](images/question.jpg)

---

# Потому что у нас gitlab

![smart](images/smart.jpeg)

---

# Gitlab-CI

## Pros:
* интегрирован в gitlab
* декларативный
* отличная документация
* можно исполнять команды в docker контейнере и использовать docker сервисы
* активно разрабатывается
* легко развернуть worker
## Cons:
* не такой гибкий

---

# Gitlab-CI

## Интегрирован в gitlab:
* pipeline начинается сразу после коммита

---

# Gitlab-CI

## Интегрирован в gitlab:
* pipeline начинается сразу после коммита
* не надо волноваться что к gitlab нет доступа (ssh ключи)

---

# Gitlab-CI

## Интегрирован в gitlab:
* pipeline начинается сразу после коммита
* не надо волноваться что к gitlab нет доступа (ssh ключи)
* описание pipeline-а всегда (!) рядом с проектом

---

# Gitlab-CI

## Интегрирован в gitlab:
* pipeline начинается сразу после коммита
* не надо волноваться что к gitlab нет доступа (ssh ключи)
* описание pipeline-а всегда (!) рядом с проектом
* можно запретить merge в случае фейла

---

# Buildbot vs Gitlab-CI

* Features
* Pipeline

---

# Buildbot

![pipeline](images/buildbot-pipeline.png)

---

# Gitlab-CI

![pipeline](images/gitlab-pipeline.png)

---

# Buildbot vs Gitlab-CI

* Features
* Pipeline
* ????????

---

# Buildbot vs Gitlab-CI

* Features
* Pipeline
* ????????
* **Gitlab-CI**

![yep](images/yep.jpg)

---

# Планы

* Перевести всё что можно на gitlab-ci
* Максимально отказаться от централизированных хранилищ описания сборки (package-description)
* Всегда использовать паттерн (gitflow-like):
    * new branch
    * commit «add feature X»
    * pipeline failed
    * wip
    * pipeline succeed
    * squash commit
    * remove branch

---

# Master allowed

![commits-chaotic](images/commits-chaotic.png)

---

# Master disabled

![commits-regular](images/commits-regular.png)

---

# Вопросы
