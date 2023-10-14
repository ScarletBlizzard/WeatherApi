## WeatherApi
API прогноза погоды, располагающийся в кластере Kubernetes и обращающийся к отказоустойчивому кластеру Postgres через балансировщик HAProxy.

![Схема](images/WeatherApi.png)

Домен для доступа к api:  ```weather-api-94``` (указать заголовок ```Host: weather-api-94``` при запросе).

### Развёртывание
```
git clone https://github.com/ScarletBlizzard/WeatherApi && cd WeatherApi
git submodule update --init
helm install weather-api weather-api/  # Установка Helm чарта (деплой api в Kubernetes)
ansible-playbook postgresql_cluster/deploy_pgcluster.yml  # Деплой кластера Postgres
```

### Эндпоинты и данные
![Эндпоинты](images/Endpoints.png)

![Данные](images/Data.png)
