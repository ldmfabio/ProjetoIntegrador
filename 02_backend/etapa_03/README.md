# Etapa 03 - Criando a API REST

Nesta etapa, vamos criar uma API REST para listar, cadastrar, atualizar e excluir os alunos cadastrados.

## Django REST Framework

O Django REST Framework é uma biblioteca que facilita a criação de APIs REST em projetos Django. Para instalar o Django REST Framework, execute o seguinte comando no terminal:
```bash
pdm add djangorestframework
```

Agora, adicione o Django REST Framework ao arquivo `INSTALLED_APPS` do arquivo `settings.py`:
```python
INSTALLED_APPS = [
    ...
    'rest_framework',
]
```

> **Adicione a linha `rest_framework` antes da linha referente a aplicação `cadastro`.**
>
> **ATENÇÃO:** O arquivo `settings.py` está na pasta `config`.

## Criando o arquivo de serialização

Vamos criar um arquivo de serialização para a aplicação `alunos`. Clique com o botão direito do mouse na pasta `alunos` e selecione a opção `New File`. Nomeie o arquivo como `serializers.py`.

Adicione o seguinte código ao arquivo `serializers.py`:
```python
from rest_framework.serializers import ModelSerializer
from .models import Estado

class EstadoSerializer(ModelSerializer):
    class Meta:
        model = Estado
        fields = '__all__'
```

Este código cria um serializador para a classe `Estado`. O serializador é responsável por converter os objetos em JSON.

## Criando as views

Vamos criar as views para a aplicação `alunos`. Abra o arquivo `views.py`, que está na pasta `alunos`, e adicione o seguinte código:
```python
from rest_framework.viewsets import ModelViewSet
from .models import Estado
from .serializers import EstadoSerializer

class EstadoViewSet(ModelViewSet):
    queryset = Estado.objects.all()
    serializer_class = EstadoSerializer
```

Este código cria uma view para a classe `Estado`. A view é responsável por listar, cadastrar, atualizar e excluir os objetos.

> _Apenas uma observação importante: O ponto que vai antes das palavras models e serializers é para indicar que os arquivos estão na mesma pasta que o arquivo views.py. Portanto, se os arquivos estiverem em pastas diferentes, é necessário indicar o caminho correto, mas, neste caso, o ponto é suficiente._

## Configurando as rotas

Vamos configurar as rotas para a aplicação `alunos`. Abra o arquivo `urls.py`, que está na pasta `config`, e adicione o seguinte código:
```python
from django.contrib import admin
from django.urls import include, path
from rest_framework.routers import DefaultRouter
from alunos.views import EstadoViewSet

router = DefaultRouter()
router.register(r'estados', EstadoViewSet)

urlpatterns = [
    path('', include(router.urls)),
    path('admin/', admin.site.urls),
]
```

Este código cria as rotas para a aplicação `alunos`. As rotas são responsáveis por direcionar as requisições para as views corretas.

Nas linhas 6 e 7, criamos um roteador padrão e registramos a view `EstadoViewSet` com o nome `estados`.

Na linha 9, incluímos as rotas do roteador no arquivo de rotas.

A linha 10 mantém a rota para a interface administrativa do Django. Ela é que possibilita que você acesse a URL `http://localhost:8000/admin/`. O admin após a porta corresponde à URL registrada na linha 10. **Não é mágica!**

Agora já é possível acessar a API REST. Execute o seguinte comando no terminal:
```bash
pdm run python manage.py runserver
```

Acesse a URL `http://localhost:8000/estados/` no navegador. Você verá a lista de estados cadastrados.

Também, se você acessar a URL `http://localhost:8000/estado/1/`, verá o estado com o ID 1.

Se você acessar a URL `http://localhost:8000/`, verá então todas as URLs que foram registradas no arquivo `urls.py`. Neste caso, a URL `http://localhost:8000/estados/` é a única que foi registrada e, por isso, é a única que aparece.

Para parar o servidor, pressione `Ctrl + C` no terminal.

# TAREFA

- [ ] Criar a API REST para a aplicação `cidade`.
- [ ] Criar a API REST para a aplicação `aluno`.


## Quando finalizar, não esqueça de publicar o código no GitHub. Avance para a próxima etapa para seguir as orientações 😉

## [Clique aqui para ir para a próxima etapa.](../etapa_04/README.md)