após criar um app no django, crie um arquivo serializer.py
então coloque código abaixo no arquivo serializer.py
## Serializer de Ambiente
* classe definida como serializer recebe o modelo Ambiente e converte todos os campos para JSON
``` python
class AmbienteSerializer(serializers.ModelSerializer):
    class Meta:
        model = Ambiente
        fields = '__all__'
```
## Serializer de Cadastro
* classe definida como serializer recebe o modelo Cadastro e converte todos os campos para JSON
``` python
 class CadastroSerializer(serializers.ModelSerializer):  
     class Meta:  
            model = Cadastro  
            fields = '__all__'
```
## Serializer de Curso
* classe definida como serializer recebe o modelo Curso e converte todos os campos para JSON
``` python
class CursoSerializer(serializers.ModelSerializer):
    class Meta:
        model = Curso
        fields = '__all__'
```
## Serializer de Disciplina
* classe definida como serializer recebe o modelo Disciplina e converte todos os campos para JSON
``` python
class DisciplinaSerializer(serializers.ModelSerializer):
    class Meta:
        model = Disciplinas
        fields = '__all__'
```
## Serializer de Turma
* classe definida como serializer recebe o modelo Turma e converte todos os campos para JSON
``` python
class TurmaSerializer(serializers.ModelSerializer):
    class Meta:
        model = Turma
        fields = '__all__'
```