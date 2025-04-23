---
title: Exemplo Endpoint cursos
description: Aqui temos um exemplo do JSON na URL /cursos 
sidebar_position: 6
---
# METODOS HTTP: GET,POST
### Descrição dos campos:

cod é o código do curso

nome é o nome do curso

ha é horas de aulas do curso

tipo é referente ao tipo de curso:

CAI é curso de aprendizagem industrial

CT é curso técnico

CS é cuso superior

FIC é formação inicial e continuada

### Exemplo de JSON de entrada
```json    
{
    "cod":"TEC",
    "curso":"Tecnico em desenvolvimento de sistemas",
    "tipo": "CT",
    "ha": "45"
}
```   
### Exemplo de JSON de saída
```json    
{
	"id": 1,
	"cod": "TEC",
	"curso": "Tecnico em desenvolvimento de sistemas",
	"tipo": "CT",
	"ha": "45"
}
```    