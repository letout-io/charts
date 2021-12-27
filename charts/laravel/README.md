# Laravel Helm Chart
This repository contains kubernetes helm charts for deploying Laravel application using git repository or docker image.


[Helm](https://helm.sh/) must be installed to use the charts. Please refer to Helm's [documentation](https://helm.sh/docs/) to get started.

Once Helm is set up properly, add the repo as follows:

```shell
helm repo add letout-io https://letout-io.github.io/charts/
```

Create a values.yaml file for your laravel application.

```shell

image:
  repository: declum/laravel
  prepare:
    git:
      enabled: true
      repo: https://github.com/letout-io/laravel-horizon.git
      refspec: main
env:
  - name: DB_USERNAME
    valueFrom:
      secretKeyRef:
        name: horizon.laravel-db.credentials.postgresql.acid.zalan.do
        key: username
  - name: DB_PASSWORD
    valueFrom:
      secretKeyRef:
        name: horizon.laravel-db.credentials.postgresql.acid.zalan.do
        key: password
envMap:
  APP_KEY: base64:kTA5r2S34nUC6a4kkf6beI3TvkhS4DU6N+UaU8lbues=
  DB_CONNECTION: pgsql
  DB_HOST: laravel-db
  DB_PORT: 5432
  DB_DATABASE: horizon

  BROADCAST_DRIVER: log
  CACHE_DRIVER: redis
  FILESYSTEM_DRIVER: local
  QUEUE_CONNECTION: redis
  SESSION_DRIVER: redis
  SESSION_LIFETIME: 120

  REDIS_HOST: laravel-redis
  REDIS_PASSWORD: 
  REDIS_PORT: 6379
ingress:
  className: nginx
  hosts:
  - horizon.172.16.137.128.sslip.io
```

You can then run `helm upgrade --install application letout-io/laravel -f values.yaml` to install/upgrade the deployments.
