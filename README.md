# OTUS Homework

## ДЗ-2. Docker Контейнер 

Репозиторий содержит Докерфайл для создания образа приложения (Dockerfile/Dockerfile).

## ДЗ-3. Приложение в kubernetes

### Подготовка окружения для запуска.

#### Установка
1. Склонировать репозиторий в текущую директорию
    ```shell
    git clone https://github.com/AlexBenderoff/Otus.git
    ```
2. Установить [minikube](https://kubernetes.io/ru/docs/tasks/tools/install-minikube/).

3. Запустить minikube
    ```shell
    minikube start
    ```
4. Перейти в папку manifest.
   ```shell
   cd manifest/
   ```
5. Подключить аддон ingress.
   ```shell
   minikube addons enable ingress
   ```
6. Запустить манифесты
   ```shell
   kubectl apply -f deploy.yaml
   kubectl apply -f service.yaml
   kubectl apply -f ingress.yaml
   ```
7. Для работы на локальной машине, необходимо, чтобы в /etc/hosts был прописан "127.0.0.1 arch.homework", также
   выполнить команду
   ```shell
   minikube tunnel
   ```
8. Перейти в браузер и выполнить запрос [health](http://arch.homework/health/)
9. Для удаления приложения выполнить команду из папки (manifest).
   ```shell
    kubectl delete -f .
   ```
