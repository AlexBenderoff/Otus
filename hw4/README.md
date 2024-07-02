# OTUS Homework

## ДЗ-4. Работа с Helm-ом

### Подготовка окружения для запуска.
Запустить minikube
```shell
minikube start
```
    
Подключить аддон ingress.
```shell
minikube addons enable ingress
```
#### Установка
1. Склонировать репозиторий в текущую директорию
    ```shell
    git clone https://github.com/AlexBenderoff/Otus.git
    ```
2. Перейти в папку hw4/manifest/
   ```shell
   cd hw4/manifest/
   ```
3. Добавить репозиторий heml
   ```shell
   helm repo add bitnami https://charts.bitnami.com/bitnami
   ```
   запустить posgtres с параметрами в отдельном yaml файле
   ```shell
   helm install my-postgres bitnami/postgresql -f values-postgresql.yaml
   ```
4. Запустить манифесты
   ```shell
   kubectl apply -f configMap.yaml
   kubectl apply -f secret.yaml
   kubectl apply -f deployment.yaml
   kubectl apply -f service.yaml
   kubectl apply -f ingress.yaml
   ```
5. Для работы на локальной машине, необходимо, чтобы в /etc/hosts был прописан "127.0.0.1 arch.homework", также
   выполнить команду
   ```shell
   minikube tunnel
   ```
6. Перейти в браузер и выполнить запрос(http://arch.homework/user)
7. Запустить коллекцию Postman  из папки /hm4/postman
8. Для удаления приложения выполнить команду из папки (manifest).
   ```shell
    kubectl delete -f .
    helm uninstall my-postgres
   ```
