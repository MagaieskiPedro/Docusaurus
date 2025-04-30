### Olá visitante
Para replicar o projeto, instale o python, crie uma venv com o comando:
``` bash
python -m venv env
```

 ative a env com :
 ``` bash
./env/Scripts/activate
```
use na raiz do projeto (se clonou):
``` bash
 pip install -r requirements.txt
```
use na raiz do projeto (se cria do zero): 
``` bash
pip install Django django-cors-headers django-filter djangorestframework djangorestframework_simplejwt
``` 
crie e entre em um projeto com:
``` bash
 django-admin startproject <nome-do-projeto>
 cd ./<nome-do-projeto>
```
dentro do projeto, crie um app:
``` bash
python ./manage.py startapp <nome-do-app>
```
dentro do projeto, entre em uma pasta com o mesmo nome do projeto e edite o arquivo settings.py
de acordo com o especificado nessa documentação e o urls.py desse modo:
``` python
from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('api/', include('api.urls'))
]
```

dentro do app, edite os arquivos models,serializer,views de acordo com o especificado nessa documentação, e crie no app um arquivo urls.py com o seguinte código:
``` python
    from django.urls import path
from .views import *

from rest_framework_simplejwt.views import (
    TokenObtainPairView,
    TokenRefreshView,
)

urlpatterns = [
    path('professores', listar_professores),
    path('prof', ProfessoresView.as_view()),
    path('id/<int:pk>', ProfessoresDetailView.as_view()),
    path('token/', TokenObtainPairView.as_view(), name='token_obtain_pair'),
    path('refresh/', TokenRefreshView.as_view(), name='token_refresh'),
    path('buscar/nome/', buscar_nome_professor),
    path('search/', ProfessoresSearchView.as_view()),
    
    path('disciplinas', DisciplinasView.as_view()),
    path('disciplina/<int:pk>', DisciplinaDetailView.as_view()),

    path('ambientes', AmbientesView.as_view()),
    path('ambiente/<int:pk>', AmbienteDetailView.as_view()),

    path('turmas', TurmasView.as_view()),
    path('turma/<int:pk>', TurmaDetailView.as_view()),

    path('cursos', CursosView.as_view()),
    path('curso/<int:pk>', CursoDetailView.as_view()),

]
```
o trecho do código que gerencia autenticação das rotas é:
``` python
from rest_framework_simplejwt.views import (
    TokenObtainPairView,
    TokenRefreshView,
)

path('token/', TokenObtainPairView.as_view(), name='token_obtain_pair'),
path('refresh/', TokenRefreshView.as_view(), name='token_refresh'),
```
usa uma biblioteca que gera automaticamente uma view (classe) que gera tokens de acesso e de refresh(usados para prolongar o tempo autenticado)

para finalizar realize as migrações para o banco de dados local (sqlite) com os comandos abaixo:
``` bash
    python ./manage.py makemigrations
    python ./manage.py migrate
```
e enfim, rode a aplicação com
``` bash
    python ./manage.py runserver
```

