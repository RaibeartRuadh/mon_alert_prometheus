

Настройка мониторинга

Настроить дашборд с 4-мя графиками:

1. память
2. процессор
3. диск
4. сеть

Настроить на одной из систем:

- zabbix (использовать screen (комплексный экран))
- prometheus - grafana

Дополнительное задание:

- использование систем примеры которых не рассматривались на занятии
- список возможных систем был приведен в презентации

Выполнение
----------

Установите зависимости:

```bash
ansible-galaxy install -r requirements.yml
```

Run virtual machine:

```bash
vagrant up
```

После указанной команды запуститися виртуальная машина, на которой
с помощью Ansible настроится `node_exporter`, `prometheus` и `grafana`.

Grafana
-------

http://localhost:3000/

Default user:

- login: admin
- password: admin
