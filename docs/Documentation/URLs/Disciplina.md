---
title: Exemplo Endpoint disciplina
description: Aqui temos um exemplo do JSON na URL /disciplina/$id
sidebar_position: 7
---
# METODOS HTTP: GET,PUT,DELETE
#### /api/disciplina/$id
### Descrição dos campos:

cod é o código da disciplina

disc é o nome da disciplina

ch é a carga horaria da disciplina
### Exemplo de JSON de entrada
```json    
{
    "cod":"123",
    "disc":"matematica",
    "ch": 40
}
```   
### Exemplo de JSON de saída
```json    
{
    "id": 1,
    "cod":"123",
    "disc":"matematica",
    "ch": 40
}
```    