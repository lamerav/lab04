## Laboratory work IV

## Homework

Вы продолжаете проходить стажировку в "Formatter Inc." (см [подробности](https://github.com/tp-labs/lab03#Homework)).

В прошлый раз ваше задание заключалось в настройке автоматизированной системы **CMake**.

Сейчас вам требуется настроить систему непрерывной интеграции для библиотек и приложений, с которыми вы работали в [прошлый раз](https://github.com/tp-labs/lab03#Homework). Настройте сборочные процедуры на различных платформах:
* используйте [TravisCI](https://travis-ci.com/) для сборки на операционной системе **Linux** с использованием компиляторов **gcc** и **clang**;
* используйте [AppVeyor](https://www.appveyor.com/) для сборки на операционной системе **Windows**.

**Travis**
```sh
$ edit .travis.yml

language: cpp # Указываем язык для которого необходимо выполнить конфигурацию системы
dist: bionic  # Указываем необходимую версию linux (Ubuntu 18.04 Bionic Beaver)

os:
- linux # Требуемая ОС

compiler:
- clang # ЯП для которых будет проводиться компиляция
- gcc

script: # Так как наша цель - проверить, собирается ли проект на чистом окружении, выполняем команды сборки из прошлого ДЗ
- cmake -Hformatter_lib/ -Bformatter_lib/_build
- cmake -Hformatter_ex_lib/ -Bformatter_ex_lib/_build
- cmake -Hhello_world_application -Bhello_world_application/_build
- cmake -Hsolver_lib -Bsolver_lib/_build
- cmake -Hsolver_application -Bsolver_application/_build
```
**AppVeyor**
```sh
os: Visual Studio 2015 # Требуемая система

build_script: # Инструкции для сборки
  - cmd: cmake -Hformatter_lib/ -Bformatter_lib/_build
  - cmd: cmake -Hformatter_ex_lib/ -Bformatter_ex_lib/_build
  - cmd: cmake -Hhello_world_application/ -Bhello_world_application/_build
  - cmd: cmake -Hsolver_lib/ -Bsolver_lib/_build
  - cmd: cmake -Hsolver_application/ -Bsolver_application/_build

```
## Links

- [Travis Client](https://github.com/travis-ci/travis.rb)
- [AppVeyour](https://www.appveyor.com/)
- [GitLab CI](https://about.gitlab.com/gitlab-ci/)

```
Copyright (c) 2015-2020 The ISC Authors
```
