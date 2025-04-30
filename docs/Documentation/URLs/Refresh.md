---
title: Exemplo Endpoint Refresh
description: Aqui temos um exemplo do JSON na URL /refresh 
sidebar_position: 12
---
# METODOS HTTP: POST
#### /api/refresh
### Descrição dos campos:
refresh é o campo que recebe o token refresh gerado na rota [api/token](./token)
access é um novo access token gerado para manter o usuario logado 
### Exemplo de JSON de entrada
```json
{
    "refresh":"Here the refresh token "
}
```
### Exemplo de JSON de saída
```json
{"access":"Here will be generated the new access token"}
```