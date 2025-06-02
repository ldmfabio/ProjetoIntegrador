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

> Para executar o comando mencionado acima, certifique-se de que você está acessando a pasta do seu projeto Django no terminal. O comando `dbshell` permite que você interaja diretamente com o banco de dados, facilitando a execução de consultas SQL, inserções, atualizações e exclusões de dados.

Para fazer isso, você deve executar os seguintes passos:
1. Execute o comando `pdm run python manage.py dbshell` no terminal.
2. Você verá um prompt interativo onde poderá digitar comandos SQL.
3. Por exemplo, você pode digitar `SELECT * FROM nome_da_tabela;` para consultar dados de uma tabela específica.
4. Após digitar os comandos, pressione `Enter` para executá-los.
5. Para sair do shell, digite `exit` ou pressione `Ctrl + D`.
6. Para visualizar as tabelas existentes no banco de dados, você pode usar o comando `.tables` já dentro do shell interativo.
7. Para ver a estrutura de uma tabela específica, você pode usar o comando `.schema nome_da_tabela`.
8. Para sair do shell, digite `exit` ou pressione `Ctrl + D`. No Windows, digite `.quit`.

## Agora, ***let's work***!

## [Clique aqui para ir para a atividade final.](../etapa_05/README.md)