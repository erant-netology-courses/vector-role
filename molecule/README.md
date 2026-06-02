# Molecule: vector

Тестирование роли vector при помощи Molecule

## Создание симлинков
Без создания симлинков не получится

```sh
mkdir -p molecule/resources/roles molecule/ubuntu/roles molecule/oraclelinux/roles
ln -s "$(pwd)" molecule/resources/roles/vector
ln -s "$(pwd)" molecule/ubuntu/roles/vector
ln -s "$(pwd)" molecule/oraclelinux/roles/vector
```

## Запуск

```sh
molecule test -s ubuntu
molecule test -s oraclelinux
```
