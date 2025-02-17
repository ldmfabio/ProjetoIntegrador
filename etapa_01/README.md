# Etapa 01 - Criando o ambiente de desenvolvimento

Criaremos uma nova pasta chamada `projeto_01`. Dentro desta pasta, criaremos outras duas pastas, uma chamada `backend` e outra chamada `frontend`. 

Execute no terminal os seguintes comandos:
```bash
mkdir projeto_01
cd projeto_01
mkdir backend
mkdir frontend
cd backend
code .
```

Agora usaremos o PDM para criar um ambiente virtual e instalar o Django. No terminal, digite o seguinte comando:
```bash
pdm init
```

> Selecione a opção 0 para criar um novo ambiente. O arquivo `pyproject.toml` será criado.

Agora, ainda no terminal, abra a pasta no VSCode, executando o seguinte comando:
```bash
code .
```

Depois de aberto, vá novamente ao terminal e digite o seguinte comando para instalar o Django:
```bash
pdm add django
```

Neste momento será criado o arquivo pdm.lock.

Novamente no terminal, criaremos o projeto Django, que será a administração do nosso backend. Digite o seguinte comando:

> **ATENÇÃO:** O ponto no final do comando é importante para que o projeto seja criado na pasta atual.
```bash
pdm run django-admin startproject config .
```

Neste momento já temos uma pasta nova no projeto. A pasta `config` é a pasta principal do projeto Django. Dentro dessa pasta estão os arquivos:
- `asgi.py`: Arquivo de configuração para o ASGI (Asynchronous Server Gateway Interface).
- `settings.py`: Arquivo de configuração do projeto.
- `urls.py`: Arquivo de configuração das rotas do projeto.
- `wsgi.py`: Arquivo de configuração para o WSGI (Web Server Gateway Interface).

Agora, inclusive, já temos um serviço Django rodando. Para testar, execute o seguinte comando no terminal:
```bash
pdm run python manage.py runserver
```

Acesse o endereço `http://localhost:8000/` no navegador. Você verá a página inicial do Django.

Para parar o servidor, pressione `Ctrl + C` no terminal.

Embora já exista a interface administrativa do projeto, ainda não temos o banco de dados configurado. Para isso, execute o seguinte comando no terminal:
```bash
pdm run python manage.py migrate
```

Ainda no terminal, precisamos criar um usuário que terá acesso à interface administrativa. Este usuário é conhecido como `superusuario`. Execute o seguinte comando:
```bash
pdm run python manage.py createsuperuser
```

> SUGESTÃO: Use o nome `admin` para o superusuário.
> 
> Para o e-mail, neste momento, use também `admin@admincom`
>
> A senha pode ser `admin`. Repita novamente `admin`, obedecendo o solicitado.
>
> **ATENÇÃO:** A senha não será exibida no terminal.
>
> **ATENÇÃO:** O e-mail é fictício e não será utilizado para envio de e-mails.
>
> **ATENÇÃO:** Aparecerá um aviso confirmando se deseja prosseguir com a criação deste usuário e senha, pois a senha é muito comum. Digite `yes` e pressione `Enter`. Não se preocupe, neste momento, com questões de segurança.

Agora, para acessar a interface administrativa, execute o seguinte comando no terminal:
```bash
pdm run python manage.py runserver
```

Algumas alterações que podem ser realizadas no arquivo `settings.py`, que está na pasta `config`:
- Alterar o idioma do sistema:
```python
LANGUAGE_CODE = 'pt-br'
```
- Alterar o fuso horário:
```python
TIME_ZONE = 'America/Sao_Paulo'
```

Acesse o endereço `http://localhost:8000/admin/` no navegador. Faça login com o usuário criado anteriormente.

**Usuário:** admin
**Senha:** admin

# O serviço está rodando? Perfeito, então vamos para a próxima etapa.

## [Clique aqui para ir para a próxima etapa.](../etapa_02/README.md)