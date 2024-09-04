# Диаграмма Развертывания: Система Отчетности на Kubernetes

## Внешние Системы

- **Dealers' Devices**: Устройства дилеров, используемые для доступа к порталу через веб-браузер.
- **1C Server**: Внешний сервер с системой 1С, который управляет данными о продуктах и дилерах.

## Kubernetes Cluster

### Namespace: production

#### Pods

- **Pod: Web Server**
  - **Web Server Container**: Веб-приложение, обрабатывающее веб-запросы и обслуживающее портал.

- **Pod: Backend Service 1**
  - **Backend Service Container 1**: Бекенд-сервис, обрабатывающий API-запросы и бизнес-логику.

- **Pod: Backend Service 2**
  - **Backend Service Container 2**: Бекенд-сервис, обрабатывающий API-запросы и бизнес-логику.

- **Pod: Database Server**
  - **Database Container**: База данных для хранения транзакционных данных.

- **Pod: Analytics Database**
  - **ClickHouse Container**: База данных для аналитики, используемая для хранения данных для отчетов.

- **Pod: Kafka Broker**
  - **Kafka Broker Container**: Мессенджер для обработки сообщений и потоков данных.

- **Pod: ETL Service**
  - **ETL Container**: Сервис для обработки, трансформации и загрузки данных.

- **Pod: Report Service**
  - **Report Service Container**: Сервис для генерации и предоставления отчетов.

- **Pod: Keycloak SSO**
  - **Keycloak Container**: Контейнер для управления аутентификацией пользователей через SSO (Single Sign-On).

- **Pod: Ingress Controller**
  - **Ingress Controller Container**: Контейнер для управления входящим трафиком к сервисам.

### Kubernetes Services

- **Web Server Service**: Сервис для балансировки нагрузки веб-сервера.
- **Backend Service 1 Service**: Сервис для балансировки нагрузки первого бекенд-сервиса.
- **Backend Service 2 Service**: Сервис для балансировки нагрузки второго бекенд-сервиса.
- **Database Service**: Сервис для балансировки нагрузки базы данных.
- **Kafka Broker Service**: Сервис для балансировки нагрузки брокера Kafka.
- **ETL Service**: Сервис для балансировки нагрузки ETL.
- **Keycloak Service**: Сервис для балансировки нагрузки Keycloak SSO.
