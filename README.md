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