# Домашнее задание к занятию "GitLab" - `Сенотов АС`


### Задание 1

##### Что нужно сделать:

1. Разверните GitLab локально, используя `Vagrantfile` и инструкцию, описанные в этом репозитории.
2. Создайте новый проект и пустой репозиторий в нём.
3. Зарегистрируйте gitlab-runner для этого проекта и запустите его в режиме Docker. Раннер можно регистрировать и запускать на той же виртуальной машине, на которой запущен GitLab.

##### В качестве ответа в репозиторий шаблона с решением добавьте скриншоты с настройками раннера в проекте.

GitLab развернут на отдельной виртуальной машине с помощью deb установки

![img1](img/img1.png)

Runner запущен на отдельной машине и зарегистрирован

![img1](img/img2.png)

Пустой проект

![img1](img/img3.png)


---

### Задание 2

##### Что нужно сделать:

1. Запушьте репозиторий на GitLab, изменив origin. Это изучалось на занятии по Git.
2. Создайте `.gitlab-ci.yml`, описав в нём все необходимые, на ваш взгляд, этапы.

##### В качестве ответа в шаблон с решением добавьте:
* файл gitlab-ci.yml для своего проекта или вставьте код в соответствующее поле в шаблоне;
* скриншоты с успешно собранными сборками.

Репозиторий с GitHub на сервере GitLab

![img1](img/img4.png)

```YAML
Содержимое .gitlab-ci.yml
stages:
  - test
  - build

test:
  stage: test
  image: golang:1.17
  script: 
   - go test .

build:
  stage: build
  image: docker:latest
  script:
   - docker build .

```
Скриншот сборки

![img1](img/img5.png)
![img1](img/img6.png)

---


