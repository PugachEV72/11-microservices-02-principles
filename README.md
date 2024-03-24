# Домашнее задание к занятию `«Микросервисы: принципы»` - Пугач Евгений.


---

## `Задание 1`

## API Gateway

Предложите решение для обеспечения реализации API Gateway. Составьте сравнительную таблицу  
возможностей различных программных решений. На основе таблицы сделайте выбор решения.

Решение должно соответствовать следующим требованиям:

- маршрутизация запросов к нужному сервису на основе конфигурации,
- возможность проверки аутентификационной информации в запросах,
- обеспечение терминации HTTPS.  

Обоснуйте свой выбор.

### Ответ:

| Решение            | Маршрутизация | Аутентификация | Терминация HTTPS | Бесплатно/Открыто?                |
|--------------------|---------------|----------------|------------------|-----------------------------------|
| Kong Gateway       | +             | +              | +                | Бесплатно, Apache 2.0             |
| Tyk.io             | +             | +              | +                | Бесплатно, MPL                    |
| HAProxy            | +             | +              | +                | Бесплатно                         |
| Yandex API Gateway | +             | +              | +                | Платно                            |
| Azure API Gateway  | +             | +              | +                | Платно                            |
| NGINX              | +             | +              | +                | Бесплатно                         |
| Gravitee           | +             | +              | +                | Бесплатно, немного порезана       |
| Google Apigee      | +             | +              | +                | Бесплатно                         |
| WSO2 API Manager   | +             | +              | +                | Бесплатно                         |

По функционалу подходят все варианты. Все указанные продукты удовлетворяют требованиям задачи и имеют свои преимущества.  

Например: хорошая производительность, как у Gravitee или Apigee, большое сообщество, как у Kong или NGINX. При этом есть  
риски ограничения поддержки в России, как у Apigee от Google. Для небольшого проекта целесообразно использовать облачные  
API Gateway, например от Яндекса (есть бесплатный объём).  

Наиболее оптимальным будет NGINX - популярное бесплатное решение, продукт с большим сообществом (можно найти достаточно  
различных схем реализации API Gateway). При этом есть возможность платной поддержки.  

Также можно рассмотреть HAProxy, как более быструю и универсальную альтернативу.


---

## `Задание 2`

## Брокер сообщений

Составьте таблицу возможностей различных брокеров сообщений. На основе таблицы сделайте обоснованный выбор решения.

Решение должно соответствовать следующим требованиям:

- поддержка кластеризации для обеспечения надёжности,
- хранение сообщений на диске в процессе доставки,
- высокая скорость работы,
- поддержка различных форматов сообщений,
- разделение прав доступа к различным потокам сообщений,
- простота эксплуатации.

Обоснуйте свой выбор.

### Ответ:

| Брокер сообщений | Поддержка кластеризации | Хранение сообщений на диске | Высокая скорость работы | Поддержка различных форматов сообщений | Разделение прав доступа | Простота эксплуатации |
| --- | --- | --- | --- | --- | --- | --- |
| Apache Kafka | + | + | + | + | + | +- |
| RabbitMQ | + | + | + | STOMP, AMQP, MQTT | + | + |
| Redis | + | +- | + | + | + | + |
| ActiveMQ | + | + | + | OpenWire, STOMP, AMQP, MQTT, JMS | + | + |

**Выводы**:

Мне кажется, лучшими вариантами являются Kafka или RabbitMQ. Итоговое решение будет зависеть от того, что является  
приоритетом, на какие параметры нужно обратить внимание, а какие параметры можно считать второстепенными. Для максимальной  
производительности нужно рассматривать Kafka. При этом RabbitMQ позволяет упорядочивать произвольные группы событий.  

`Apache Kafka` - является наиболее популярным продуктом с большим сообществом и высокой призводительностью, это  
распределенная очередь с высокой пропускной способностью, созданная для длительного хранения больших объемов данных.  

`Redis` - имеет наибольшую популярность, как база данных для хранения "горячих" данных. Это давно известный, популярный брокер  
со множеством функций и возможностей, поддерживающих сложную маршрутизацию. Он способен обеспечивать маршрутизацию сообщений  
при  незначительном трафике.

`RabbitMQ` - простой в использовании, но имеет меньшую гибкость, чем Kafka.

---

### Дополнительные задания (со звездочкой*)


