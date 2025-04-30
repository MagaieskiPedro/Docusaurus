o código abaixo deve ser inserido no arquivo models.py
## Modelo Ambiente
``` python
class Ambiente(models.Model):
``` 
1. campos do tipo caractere que recebem até 255 caracteres:
``` python
    cod = models.CharField(max_length=255)  
    sala = models.CharField(max_length=255) 
    resp = models.CharField(max_length=255)
```
2. campo do tipo inteiro:    
``` python
    cap = models.IntegerField()  
```           
3. campo do tipo caractere que recebe apenas os tipos informados por letras em PERIODOS de até 10 caracteres com valor padrão M:
``` python
    per = models.CharField(choices=PERIODOS, max_length=10, default="M")
    PERIODOS = [
        ('M', 'Manhã'),
        ('T', 'Tarde'),
        ('N', 'Noite'),
        ('I', 'Integral'),
    ]
```   
## Modelo Cadastro
``` python
class Cadastro(models.Model):
``` 
1. campos do tipo caractere que recebem até 15 e 255 caracteres:
``` python
    ni = models.CharField(max_length=15)   
    nome = models.CharField(max_length=255)  
    cel = models.CharField(max_length=255)
```  
2. campo do tipo email que deve ser formatado no formato de email:
``` python
    email = models.EmailField()
```  
3. campo do tipo decimal:
``` python
    ocup = models.FloatField()
```
## Modelo Cursos
``` python
class Curso(models.Model):
```
1. campos do tipo caractere que recebem até 255 caracteres:
``` python
    cod = models.CharField(max_length=255)
    curso = models.CharField(max_length=255)
    ha =  models.CharField(max_length=255) 
```
2. campo do tipo caractere que recebe valor definido em TIPOS até 20 caracteres com valor padrão CT:
``` python
    tipo = models.CharField(max_length=20, choices=TIPOS, default="CT")
    TIPOS = [
        ('CAI', 'Aprendizagem'),
        ('CT','Técnico'),
        ('CS','Superior'),
        ('FIC','Formação')
    ]
 ```   
## Modelo Disciplinas
``` python
class Disciplinas(models.Model):
```
1. campos do tipo caractere que recebem até 100 caracteres:
``` python
    cod = models.CharField(max_length=100)  
    disc = models.CharField(max_length=100)
``` 
2.  campo do tipo inteiro:
``` python
    ch = models.IntegerField()      
```


## Modelo Turmas
``` python
class Turma(models.Model):
```
1. campos do tipo caractere que recebem até 255 caracteres:
``` python
    cod = models.CharField(max_length=255)   
    turrma = models.CharField(max_length=255)
```
 