# Authentication with Flask, React, and Docker
# Deploying a Flask and React Microservice to AWS ECS
[![pipeline status](https://gitlab.com/testdriven/flask-react-auth/badges/master/pipeline.svg)](https://gitlab.com/testdriven/flask-react-auth/commits/master)

https://testdriven.io/courses/auth-flask-react/

# curl
## GET(all)
```shell
curl -X GET http://localhost:5004/users
```

## GET(id)
```shell
curl -X GET http://localhost:5004/users/{:id}
```

## POST(register)
```shell
curl -X POST http://localhost:5004/auth/register -H 'accept: application/json' -H 'Content-Type: application/json' -d '{"username":"{USER_NAME}","email":"{USER_EMAIL}","password":"{USER_PASSWORD}"}'
```

## POST(login)
```shell
curl -X POST http://localhost:5004/auth/login -H 'accept: application/json' -H 'Content-Type: application/json' -d '{"username":"{USER_NAME}","email":"{USER_EMAIL}","password":"{USER_PASSWORD}"}'
```

[response]
```shell
{
    "refresh_token": "{REFRESH_TOKEN}",
    "access_token": "{ACCESS_TOKEN}",
}
```

## POST(status)
```shell
curl -X GET 'http://localhost:5004/auth/status' -H "Authorization: Bearer {ACCESS_TOKEN}"
```

## POST (refresh)
```shell
curl -X POST http://localhost:5004/auth/refresh -H 'accept: application/json' -H 'Content-Type: application/json' -d '{"refresh_token":"{REFRESH_TOKEN}"}'
```

## PUT
```shell
curl -X PUT http://localhost:5004/users/4 -H 'accept: application/json' -H 'Content-Type: application/json' -d '{"username":"{NEW_USENAME}","email":"{NEW_EMAIL_ADDRESS}","password":"{NEW_PASSWORD}"}'
```

## DELETE
```shell
curl -X DELETE http://localhost:5004/users/{:id}
```


## ecs memo
### APP_SETTINGS
```shell
APP_SETTINGS = src.config.ProductionConfig
```
### DATABASE_URL
```shell
DATABASE_URL = RDS_URI

#RDS_URI base_example
postgresql://{MASTER_USENAME}:{MASTER_PASSWORD}@{RDS_END_POINT}:{PORT}/{INITIAL_DB_NAME}

#RDS_URI examples
postgresql://hoge:password@hogehoge.ap-northeast-1.rds.amazonaws.com:5432/hoge_db
```
### DATABASE_TEST_URL
```
DATABASE_TEST_URL = postgres://postgres:postgres@api-db:5432/api_test
```
### FLASK_ENV
```shell
FLASK_ENV = production
```
### SECRET_KEY
```shell
SECRET_KEY = "A string of 50 characters or more"
```