# Домашнее задание
Настройка мониторинга
Настроить дашборд с 4-мя графиками
1) память
2) процессор
3) диск
4) сеть

настроить на одной из систем
- zabbix (использовать screen (комплексный экран))
- prometheus - grafana

* использование систем примеры которых не рассматривались на занятии
- список возможных систем был приведен в презентации

в качестве результата прислать скриншот экрана - дашборд должен содержать в названии имя приславшего
Критерии оценки: 5 - основное задание
6 - задание со зведочкой

Был выбран вариант с Прометиусом и Графаной
Дополнительно использовался Node Exporter для экспорта метрик. 
Для удобства развертывания, пригодились навыки создания ролей. Это тот же playbook, только на конкретный пакет/сервис в структуре galaxy.ansible
Установка:
Выполнить импорт ролей для Grafana, Prometheus, Node Export for Prometheus

*ansible-galaxy install -r requirements.yml*

В результате мы должны получитьлог:

- downloading role 'node_exporter', owned by RaibeartRuadh
- downloading role from https://github.com/RaibeartRuadh/ansible-role-node-exporter/archive/main.tar.gz
- extracting RaibeartRuadh.node_exporter to /home/roy/.ansible/roles/RaibeartRuadh.node_exporter
- RaibeartRuadh.node_exporter (main) was installed successfully
- downloading role 'prometheus', owned by RaibeartRuadh
- downloading role from https://github.com/RaibeartRuadh/ansible-role-prometheus/archive/main.tar.gz
- extracting RaibeartRuadh.prometheus to /home/roy/.ansible/roles/RaibeartRuadh.prometheus
- RaibeartRuadh.prometheus (main) was installed successfully
- downloading role 'grafana', owned by RaibeartRuadh
- downloading role from https://github.com/RaibeartRuadh/ansible-role-grafana/archive/main.tar.gz
- extracting RaibeartRuadh.grafana to /home/roy/.ansible/roles/RaibeartRuadh.grafana
- RaibeartRuadh.grafana (main) was installed successfully

Далее. Выполнить запуск сервера Vagrant

vagrant up

После запуска сервера. выполнить вход по IP:port 
Данные задаются в файле Vagrantfile и могут быть изменены под требования:
SERVER_IP = "192.168.10.10"
GRAFANA_PORT_GUEST = 3000

http://192.168.10.10:3000

При первом входе потребуется ввода логина/пароля admin/admin и ввод нового пароля.

В результате должен быть загружен сайт Grafana
с экспортированными метриками на:
- Load Average
- Disk Size 
- Memory
- Disk read/write
- Network

Скрин 1 и Скрин 2

Откуда можно получить данные для Node Exporter
Лучший вариант - установить Prometheus + Grafana. Создать свой Dashboard и скопировать получившуюся JSON модель dashboard.
Скрин 3








