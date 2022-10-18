Установка Kibana
=========

Роль установки Kibana из локального архива дистрибутива. Роль копирует архив с дистрибутивом на указанные машины, распаковывает его и устанавливает в `/etc/profile.d/` файл `kib.sh`, содержащий скрипт для установки переменной `KIB_HOME` на каталог установки Kibana и добавления `$KIB_HOME/bin` к `PATH`.

Переменные
--------------

- kibana_version: версия Kibana, по умолчанию 8.4.3
- kibana_home: каталог, Kibana, по умолчанию `/opt/kibana/8.4.3`
- kibana_archive: имя архива с дистрибутивом Kibana, по умолчанию `kibana-8.4.3-linux-x86_64.tar.gz`

Тестирование
----------------

В каталоге `molecule` имеются скрипты для тестирования роли с помощью Docker на трех платформах:

- docker.io/pycontribs/ubuntu:latest
- docker.io/pycontribs/centos:8
- docker.io/pycontribs/centos:7

Пример Playbook
----------------
```yaml
- hosts: kibana
  roles:
    - martynov-andrey.kibana-role