---
title: Exemplo Endpoint id
description: Aqui temos um exemplo do JSON na URL /id/$id 
---
# METODOS HTTP: GET
### Descrição dos campos
id é o identificador unico do professor, utilizado no final da url para procurar especificamente pelos dados relativos aquele professor

ni é o numero de identificação do professor

nome é o nome do professor

email é o email do professor

cel é o celular do professor

ocup são as horas de ocupação do professor
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