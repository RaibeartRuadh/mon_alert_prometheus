
Запуск сценарий установки Prometheus+Grafana+node_exporter
Настройка мониторинга c дашборд на 4 графика:

1. память
2. процессор
3. диск
4. сеть

Выполнение
----------
1. Для запуска стенда вам потребуется: Git, Ansible 2.9.6, Vagrant 2.2.16, VirtualBox 6.1
2. Установите зависимости:

```bash
ansible-galaxy install -r requirements.yml
```

3.Запуск проекта:

```bash
vagrant up
```
4. Проверка.
    `Перейти по адресу http://localhost:3000/`
    `Default user:`
    `Ввести:
    - login: admin
    - password: admin

5. Выберите Dashboard - Dashboards - Manage - RaibeartRuadh Dashboard. 

