---
title: Exemplo Endpoint Professores
description: Aqui temos um exemplo do JSON na URL /professores 
sidebar_position: 11
---
# METODOS HTTP: GET,POST
#### /api/professores
### Descrição dos campos:

ni é o numero de identificação do professor

nome é o nome do professor

email é o email do professor

cel é o celular do professor

ocup são as horas de ocupação do professor
### Exemplo de JSON de entrada
```json    
    {
		"ni": "1021328",
		"nome": "Lindomar José",
		"email": "lin@lin.com",
		"cel": "23132132123",
		"ocup": 50
	}
```   
### Exemplo de JSON de saída
```json    
    {
		"id": 1,
		"ni": "1021328",
		"nome": "Lindomar José",
		"email": "lin@lin.com",
		"cel": "23132132123",
		"ocup": 50
	}
```    