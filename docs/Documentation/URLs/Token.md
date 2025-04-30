---
title: Exemplo Endpoint Token
description: Aqui temos um exemplo do JSON na URL /token 
sidebar_position: 13
---
# METODOS HTTP: POST
#### /api/token
### Descrição dos campos:

username é o nome de usuario

password é a senha do usuario

access é o token gerado aleatoriamente que deve ir no header como bearer token em todas as rotas bloqueadas que são todas fora as a seguir:      
[admin/](.admin)  
[api/token](./token)   
[api/refresh](./refresh) 

refresh é o token gerado aleatoriamente que deve ir na rota  [api/refresh](./refresh)  para gerar automaticamente um novo access token
### Exemplo de JSON de entrada
```json
{
  "username":"here the username",
  "password": 9876
}
```
### Exemplo de JSON de saída
```json
{
    "refresh":"Here will be generated the refresh token",
    "access":"Here will be generated the acess token"
}
```
