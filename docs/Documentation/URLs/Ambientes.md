---
title: Exemplo Endpoint ambientes
description: Aqui temos um exemplo do JSON na URL /ambientes 
sidebar_position: 3
---
# METODOS HTTP: GET,POST
### Descrição dos campos:

cod é o código do ambiente

sala é o nome da sala

cap é a capacidade de alunos na disciplina

resp é o nome do responsavel da sala

per é o periodo disponivel do ambiente:

M, que é o periodo da manhã 

T, que é o periodo da tarde 

N, que é o periodo da noite 

I, que é o periodo integral 

### Exemplo de JSON de entrada
```json    
{
    "cod":"codigo do ambiente",
    "sala":"431",
    "cap": 40,
    "resp": "lurdes",
    "per":"M"
}
```   
### Exemplo de JSON de saída
```json    
{
    "id": 1,
    "cod":"codigo do ambiente",
    "sala":"431",
    "cap": 40,
    "resp": "lurdes",
    "per":"M"
}
```    