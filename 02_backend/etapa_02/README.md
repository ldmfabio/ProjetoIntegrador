# Etapa 02 - Criando a aplicação alunos

Nesta etapa, criaremos uma aplicação chamada `alunos` que será responsável por cadastrar os alunos de uma escola, informando apenas o nome, cidade, data de nascimento, e-mail e telefone. Como temos a cidade, e ela pode ser repetida para vários alunos, criaremos uma tabela chamada `Cidade` para armazenar as cidades e relacioná-las com os alunos. Várias cidades podem pertencer ao mesmo estado, então criaremos uma tabela chamada `Estado` para armazenar os estados e relacioná-los com as cidades.

## Criando a aplicação alunos

No terminal, execute o seguinte comando para criar a aplicação `alunos`:
```bash
pdm run python manage.py startapp alunos
```

Agora já temos uma nova app criada. Você pode perceber que uma nova pasta foi criada, a pasta `alunos`. Dentro dessa pasta estão os arquivos:
- `admin.py`: Arquivo de configuração do Django Admin.
- `models.py`: Arquivo de configuração dos modelos de dados.
- `tests.py`: Arquivo de testes.
- `views.py`: Arquivo de configuração das views.

Como criamos uma nova app, precisamos registrá-la no arquivo `config/settings.py`. Abra o arquivo `settings.py`, que está na pasta `config` e adicione a app `alunos` na lista `INSTALLED_APPS`:
```python
INSTALLED_APPS = [
    ...
    'alunos',
]
```

## Criando os modelos de dados

Vamos criar os modelos de dados para a aplicação `alunos`. Abra o arquivo `models.py`, que está na pasta `alunos`, e adicione o seguinte código:
```python
from django.db import models

class Estado(models.Model):
    nome = models.CharField(max_length=50)
    sigla = models.CharField(max_length=2)

    def __str__(self):
        return self.nome
```

> Neste arquivo temos, na primeira linha, a importação do módulo `models` do Django.
> 
> Em seguida, criamos a classe `Estado` que herda de `models.Model`.
> 
> Esta classe possui dois atributos: `nome` e `sigla`, ambos do tipo `CharField`.
> 
> O método `__str__` retorna o nome do estado, que será exibido no Django Admin.

No terminal, execute o seguinte comando para criar a tabela `Estado` no banco de dados:
```bash
pdm run python manage.py makemigrations
pdm run python manage.py migrate
```

Agora, abra o arquivo `admin.py`, que está na pasta `alunos`, e adicione o seguinte código:
```python
from django.contrib import admin
from .models import Estado

admin.site.register(Estado)
```

Este código registra o modelo `Estado` no Django Admin.

> **Pare, pense e compreenda:** _Veja que inicialmente criamos o projeto Django admin, chamado `config`. Depois, criamos uma aplicação, chamada `alunos`. Para relacionar os dois, fomos no arquivo `settings.py`da pasta `config` para "instalar" a aplicação na administração do Django. Posteriormente foi então criada a model `Estado`, no arquivo `models.py`. Então, no arquivo `admin.py` da aplicação `alunos` registramos esta model criada, para que ela possa ficar acessível na interface administrativa do Django. Cria-se uma ligação entre a administração do django, a app criada e a model da app._

Se você acessar o Django Admin, verá a tabela `Estado` disponível para cadastro. Para acessar o Django Admin, execute o seguinte comando no terminal:
```bash
pdm run python manage.py runserver
```

Acesse o endereço `http://localhost:8000/admin/` no navegador. Você verá a página de login do Django Admin. Faça login com o superusuário criado anteriormente (usuário `admin` e senha `admin`). Após o login, você verá a página inicial do Django Admin. Clique em `Estado` para cadastrar um novo estado.

## Criando a tabela Cidade

Vamos criar a tabela `Cidade` para armazenar as cidades e relacioná-las com os estados. Abra o arquivo `models.py`, que está na pasta `alunos`, e adicione o seguinte código:
> *Deixe uma linha de intervalo em branco entre as classes.*
```python
class Cidade(models.Model):
    nome = models.CharField(max_length=50)
    estado = models.ForeignKey(Estado, on_delete=models.PROTECT)

    def __str__(self):
        return self.nome
```

> Neste código, criamos a classe `Cidade` que herda de `models.Model`.
>
> Esta classe possui dois atributos: `nome` e `estado`.
>
> O atributo `estado` é uma chave estrangeira que relaciona a cidade com o estado.
>
> O método `__str__` retorna o nome da cidade, que será exibido no Django Admin.
>
> A chave estrangeira `estado` é do tipo `ForeignKey` e recebe como parâmetro a classe `Estado` criada anteriormente.
>
> O parâmetro `on_delete=models.PROTECT` indica que, caso um estado seja excluído, as cidades relacionadas a ele não serão excluídas.
>
> **Pare, pense e compreenda:** _Veja que criamos a model `Cidade` e relacionamos com a model `Estado`. A model `Estado` foi criada anteriormente e já está disponível na interface administrativa do Django. Agora, criamos a model `Cidade` e relacionamos com a model `Estado`. A model `Cidade` também será disponibilizada na interface administrativa do Django._

No terminal, execute o seguinte comando para criar a tabela `Cidade` no banco de dados:
```bash
pdm run python manage.py makemigrations
pdm run python manage.py migrate
```

Agora, abra o arquivo `admin.py`, que está na pasta `alunos`, e adicione o seguinte código:
```python
from .models import Cidade

admin.site.register(Cidade)
```

Este código registra o modelo `Cidade` no Django Admin e o torna disponível para cadastro.

Uma possibilidade é, ao invés de ter duas linhas para importar de .models, importar tudo de uma vez:
```python
from .models import Estado, Cidade
```

Se você acessar o Django Admin, verá a tabela `Cidade` disponível para cadastro. Para acessar o Django Admin, execute o seguinte comando no terminal:
```bash
pdm run python manage.py runserver
```

Acesse o endereço `http://localhost:8000/admin/` no navegador. Você verá a página de login do Django Admin. Faça login com o superusuário criado anteriormente (usuário `admin` e senha `admin`). Após o login, você verá a página inicial do Django Admin. Clique em `Cidade` para cadastrar uma nova cidade.

**SUGESTÃO**

Altere a definição do método `__str__` da classe `Estado` para exibir o nome e a sigla do estado:
```python
def __str__(self):
    return f'{self.nome} - {self.sigla}'
```

Altere a definição do método `__str__` da classe `Cidade` para exibir o nome da cidade e a sigla do estado ao qual ela pertence:
```python
def __str__(self):
    return f'{self.nome} - {self.estado.sigla}'
```

## Criando a tabela Aluno

Vamos criar a tabela `Aluno` para armazenar os alunos. Abra o arquivo `models.py`, que está na pasta `alunos`, e adicione o seguinte código:

```python
class Aluno(models.Model):
    nome = models.CharField(max_length=100)
    data_nascimento = models.DateField()
    email = models.EmailField()
    telefone = models.CharField(max_length=15)
    cidade = models.ForeignKey(Cidade, on_delete=models.PROTECT)

    def __str__(self):
        return self.nome
```

> Neste código, criamos a classe `Aluno` que herda de `models.Model`.
>
> Esta classe possui cinco atributos: `nome`, `data_nascimento`, `email`, `telefone` e `cidade`.
>
> O atributo `cidade` é uma chave estrangeira que relaciona o aluno com a cidade.
>
> O método `__str__` retorna o nome do aluno, que será exibido no Django Admin.
>
> A chave estrangeira `cidade` é do tipo `ForeignKey` e recebe como parâmetro a classe `Cidade` criada anteriormente.
>
> O parâmetro `on_delete=models.PROTECT` indica que, caso uma cidade seja excluída, os alunos relacionados a ela não serão excluídos.

No terminal, execute o seguinte comando para criar a tabela `Aluno` no banco de dados:
```bash
pdm run python manage.py makemigrations
pdm run python manage.py migrate
```

Agora, abra o arquivo `admin.py`, que está na pasta `alunos`, e adicione o seguinte código:
```python
from .models import Aluno

admin.site.register(Aluno)
```

Este código registra o modelo `Aluno` no Django Admin e o torna disponível para cadastro.

Ao invés de ter duas linhas para importar de .models, você pode importar tudo de uma vez, numa linha só:
```python
from .models import Estado, Cidade, Aluno
```

Se você acessar o Django Admin, verá a tabela `Aluno` disponível para cadastro. Para acessar o Django Admin, execute o seguinte comando no terminal:
```bash
pdm run python manage.py runserver
```

Acesse o endereço `http://localhost:8000/admin/` no navegador. Você verá a página de login do Django Admin. Faça login com o superusuário criado anteriormente (usuário `admin` e senha `admin`). Após o login, você verá a página inicial do Django Admin. Clique em `Aluno` para cadastrar um novo aluno.

**SUGESTÃO**

Altere a definição do método `__str__` da classe `Aluno` para exibir o nome do aluno e a cidade e estado ao qual ele pertence:
```python
def __str__(self):
    return f'{self.nome} - {self.cidade.nome} ({self.cidade.estado.sigla})'
```

# Estados, Cidades e Alunos cadastrados? Então vamos para a próxima etapa!

Agora que criamos as tabelas `Estado`, `Cidade` e `Aluno`, cadastramos alguns estados, cidades e alunos, vamos para a próxima etapa. Nesta etapa, vamos criar uma API REST para listar, cadastrar, atualizar e excluir os alunos cadastrados.

## [Clique aqui para ir para a próxima etapa.](../etapa_03/README.md)