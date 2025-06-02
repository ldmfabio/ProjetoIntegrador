# Etapa 4 - GitHub

Inclusive, não precisa esperar finalizar para publicar, pode ir publicando conforme for fazendo as tarefas. 😉

Porém, se preferir, pode publicar tudo de uma vez só. 🚀

Vai aqui uma dica:

Acesse a URL [gitignore.io](https://www.gitignore.io/) e gere um arquivo `.gitignore` para projetos Python. Este arquivo irá ignorar os arquivos e pastas que não precisam ser versionados.

Neste site, digite `Python` e também `Django` e clique em `Create`. Copie o conteúdo gerado e cole no arquivo `.gitignore` do seu projeto. O arquivo `.gitignore` deve ficar na pasta raiz do projeto.

Depois, siga os passos abaixo para publicar o código no GitHub:

1. No terminal, vá até a pasta do projeto.
2. Execute o comando `git init` para iniciar o repositório Git.
3. Execute o comando `git add .` para adicionar todos os arquivos ao repositório.
4. Execute o comando `git commit -m "Introdução API REST"` para fazer o commit identificando-o pela mensagem adequada.
5. No Visual Studio Code, vá na opção `Source Control` e clique nos três pontinhos `...` e selecione a opção `Push`, ou então `Publish to GitHub`.
6. Indique o nome do repositório.
7. Selecione se deseja que o repositório seja público ou privado.
8. Clique em `Create Repository`.
9. Pronto! Seu código estará publicado no GitHub.

Caso deseja abrir o projeto no repositório, o Visual Studio Code mostrará uma notificação no canto inferior direito. Clique em `Open in GitHub` ou então `Abrir no GitHub`.

Se tiver alguma dúvida, não hesite em me chamar. Estou à disposição para ajudar. 🤗

Claro, esses passos para publicar no GitHub demandam de alguns pré-requisitos. Já é necessário ter seu usuário logado no Visual Studio Code e é preciso ter seu `git config` também configurado.

## Você sabia?

Também é possível executar instruções SQL diretamente no Django, utilizando o comando `pdm run python manage.py dbshell`. Este comando abrirá um shell interativo onde você poderá executar comandos SQL diretamente no banco de dados configurado no seu projeto Django.

Para fazer isso, você deve executar os seguintes passos:
1. Certifique-se de que o banco de dados está configurado corretamente no arquivo `settings.py` do seu projeto Django.
2. Execute o comando `pdm run python manage.py dbshell` no terminal.
3. Você verá um prompt interativo onde poderá digitar comandos SQL.
4. Por exemplo, você pode digitar `SELECT * FROM nome_da_tabela;` para consultar dados de uma tabela específica.
5. 
4. Após digitar os comandos, pressione `Enter` para executá-los.
5. Para sair do shell, digite `exit` ou pressione `Ctrl + D`.
6. 


### Está concluído? ***Então, _let's work_!*** 🚀

## [Clique aqui para ir para a atividade final.](../etapa_05/README.md)