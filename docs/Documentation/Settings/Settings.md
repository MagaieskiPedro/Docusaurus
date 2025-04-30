o código abaixo deve ser inserido no arquivo settings.py
## Alterações no arquivo settings.py gerado automaticamente
1. adicionadas bibliotecas e aplicativo
``` python
SETTINGS = [
    'rest_framework',
    'api',
    'rest_framework_simplejwt',
    "corsheaders",
    'django_filters'
]
```
2. configurações de autenticação adicionadas
``` python
from datetime import timedelta
    REST_FRAMEWORK = {
        'DEFAULT_AUTHENTICATION_CLASSES': (
            'rest_framework_simplejwt.authentication.JWTAuthentication',
        )
    }

    SIMPLE_JWT = {
        "AUTH_HEADER_TYPES": ("Bearer",),
        "ACCESS_TOKEN_LIFETIME": timedelta(minutes=240),
        "REFRESH_TOKEN_LIFETIME": timedelta(days=1),
    }
```
3. permissões CORS (cross origin resource sharing) permite qualquer host(computador conectado na internet) a consumir a API 
``` python
    CORS_ORIGIN_ALLOW_ALL = True
```