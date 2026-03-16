University: \\\[ITMO University](https://itmo.ru/ru/)



Faculty: \[FTMI](https://itmo.ru/ru/viewfaculty/87/fakultet\_tehnologicheskogo\_menedzhmenta\_i\_innovaciy.htm)

Course: \\\[Введение в веб технологии](https://itmo-ict-faculty.github.io/introduction-in-web-tech/)



Year: 2025/2026



Group: U4125



Author: Булгакова Емилия Валерьевна



Lab: Lab1



Date of create: 16.03.2026



Date of finished: 17.03.2026







Лабораторная работа №3: Мониторинг с Prometheus и Grafana



1\. Цель работы: yастроить автоматический сбор метрик (данных о состоянии системы) и визуализировать их на графиках.

2\. Ход работы:

2.1 Настройка конфигурации: Был создан файл prometheus.yml, в котором ,была указана «адресная книга» для Prometheus. Мы прописали ему, что нужно забирать данные с узла node-exporter:9100

2.2 Чтобы не запускать каждый контейнер вручную, был написан файл docker-compose.yml. В нем:



* Была создана общая сеть monitoring, чтобы контейнеры могли общаться.
* Были подключены «тома» (volumes), чтобы настройки и графики не удалились после выключения компьютера.

!\[compose](./screenshots/compose.png)

!\[докер](./screenshots/docker.png)





В Grafana был подключен источник данных (Data Source) — Prometheus. Затем был импортирован профессиональный дашборд под номером 1860, который умеет расшифровывать данные от Node Exporter.

!\[grafana](./screenshots/grafana.png)



Вывод:

В результате работы настроена система мониторинга, позволяющая в реальном времени отслеживать нагрузку на систему (CPU, RAM, Disk, Network). Это позволяет вовремя заметить сбои или нехватку ресурсов.

