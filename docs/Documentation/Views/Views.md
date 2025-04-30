o código abaixo deve ser inserido no arquivo views.py
## Views de Ambiente 
 ``` python
class AmbientesView(ListCreateAPIView):
    queryset = Ambiente.objects.all()
    serializer_class = AmbienteSerializer
    permission_classes = [IsAuthenticated]

class AmbienteDetailView(RetrieveUpdateDestroyAPIView):
    queryset = Ambiente.objects.all()
    serializer_class = AmbienteSerializer
    permission_classes = [IsAuthenticated]
```
[ListCreateAPIView] é um parametro que a classe recebe que informa que ela pode receber os metodos HTTP GET e POST, GET que permite
que sejam consultados todos os itens do modelo informado, POST que permite que seja criado um novo item seguindo o modelo informado

[RetrieveUpdateDestroyAPIView] é um parametro que a classe recebe que informa que ela pode receber os metodos HTTP GET(por id), PUT e DELETE
GET que permite que seja consultado um item especifico pelo numero id, PUT permite que seja alterado o item do id informado, DELETE que apaga o item do id informado

[queryset] recebe todos os objetos contidos em um modelo referido (nesse caso Ambiente), e aplica sobre  os metodos http daquela classe

[serializer_class] recebe a classe que irá serializar os dados do modelo em queryset (nesse caso AmbienteSerializer)

[permission_classes] informa se para acessar aquela classe é preciso estar ou não autenticado(IsAuthenticade significa que nesse caso sim)
e em casos mais avançados, quais permissões serão necessarias


## Views de Cadastro
1. Cadastro basico
``` python
@api_view(['GET', 'POST'])
@permission_classes([IsAuthenticated])
def listar_professores(request):
    if request.method == 'GET':
        queryset = Cadastro.objects.all()
        serializer = CadastroSerializer(queryset, many=True)
        return Response(serializer.data)
    elif request.method == 'POST':
        serializer = CadastroSerializer(data=request.data)
        if serializer.is_valid():
            serializer.save()
            return Response(serializer.data, status=status.HTTP_201_CREATED)
        else:
            return Response(serializer.errors, status=status.HTTP_400_BAD_REQUEST)
```
### Explicação do código acima

* Cabeçalho / Annotations / Generics :
``` python
@api_view(['GET', 'POST'])
``` 
informa que aceita metodos de GET e POST, criar e ler dados no modelo cadastro
``` python
@permission_classes([IsAuthenticated])
``` 
informa que só aceita usuarios autenticados

* Corpo
``` python
    if request.method == 'GET':
        queryset = Cadastro.objects.all()
        serializer = CadastroSerializer(queryset, many=True)
        return Response(serializer.data)
 ```
 se a requisição foi feita como GET, recebe todos os registros do modelo cadastro, passa eles pelo serializer do cadastro, e por fim retorna os dados desse serializer
 ``` python
    elif request.method == 'POST':
        serializer = CadastroSerializer(data=request.data)
        if serializer.is_valid():
            serializer.save()
            return Response(serializer.data, status=status.HTTP_201_CREATED)
        else:
            return Response(serializer.errors, status=status.HTTP_400_BAD_REQUEST)
```
se a requisição foi feita como POST, serializa essa requisição, checa se é valida, se for ela é salva e retornada com o status 201, se não for é retornado um status 400

2. Filtrar por nome do cadastro especifico
``` python
@api_view(['GET', 'POST'])
@permission_classes([IsAuthenticated])
def buscar_nome_professor(request):
    termo = request.get('nome', '')
    if termo:
        professores = Cadastro.objects.filter(nome_incontains = termo)
    else:
        professores = Cadastro.objects.all()
    
    serializer = CadastroSerializer(professores, many=True)
    return Response(serializer.data, status=status.HTTP_200_OK)
```
### Explicação do código acima
``` python
if termo:
    professores = Cadastro.objects.filter(nome_incontains = termo)
else:
    professores = Cadastro.objects.all()
```
se houver um nome de professor(termo) pesquisado na url, o objeto que será chamado vai ser apenas o professor especificado
se não houver um nome de professor(termo) pesquisado na url, retorna todos os professores  

3. cadastro usando classes com view
``` python
class ProfessoresView(ListCreateAPIView):
    queryset = Cadastro.objects.all()
    serializer_class = CadastroSerializer
    permission_classes = [IsAuthenticated]

class ProfessoresDetailView(RetrieveUpdateDestroyAPIView):
    queryset = Cadastro.objects.all()
    serializer_class = CadastroSerializer
    permission_classes = [IsAuthenticated]

class ProfessoresSearchView(ListAPIView):
    queryset = Cadastro.objects.all()
    serializer_class = CadastroSerializer
    permission_classes = [IsAuthenticated]
    filter_backends = [DjangoFilterBackend, SearchFilter]
    search_fields = ['nome']
```
### Explicação do código acima
``` python
    filter_backends = [DjangoFilterBackend, SearchFilter]
    search_fields = ['nome']
```
filter_backends cria um filtro de busca, SearchField realiza uma busca por um campo e DjangoFilterBackend filtra a consulta com o campo informado para pesquisa
search_fields informa o campo do modelo que será usado para pesquisa (nesse caso nome)

## Views de Curso
``` python
class CursosView(ListCreateAPIView):
    queryset = Curso.objects.all()
    serializer_class = CursoSerializer
    permission_classes = [IsAuthenticated]

class CursoDetailView(RetrieveUpdateDestroyAPIView):
    queryset = Curso.objects.all()
    serializer_class = CursoSerializer
    permission_classes = [IsAuthenticated]
```

## Views de Disciplina
``` python
class DisciplinasView(ListCreateAPIView):
    queryset = Disciplinas.objects.all()
    serializer_class = DisciplinaSerializer
    permission_classes = [IsAuthenticated]

class DisciplinaDetailView(RetrieveUpdateDestroyAPIView):
    queryset = Disciplinas.objects.all()
    serializer_class = DisciplinaSerializer
    permission_classes = [IsAuthenticated]
```

## Views de Turma
``` python
class TurmasView(ListCreateAPIView):
    queryset = Turma.objects.all()
    serializer_class = TurmaSerializer
    permission_classes = [IsAuthenticated]

class TurmaDetailView(RetrieveUpdateDestroyAPIView):
    queryset = Turma.objects.all()
    serializer_class = TurmaSerializer
    permission_classes = [IsAuthenticated]
```