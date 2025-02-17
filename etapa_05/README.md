# "Trabalhinho" - Projeto Integrador II

Para finalizar o ano letivo da disciplina de Projeto Integrador II, a dupla (máximo 2 integrantes - inegociável) deverão criar a API REST para uma das seguintes modelagens abaixo:

**1. Sistema de Controle de Pedidos**
   - Clientes (id, nome, email, telefone)
   - Pedidos (id, id_cliente, data_pedido, valor_total)
   - ItensPedido (id, id_pedido, produto, quantidade, preco_unitario)

`📝 Explicação: Cada cliente pode ter vários pedidos, e cada pedido pode ter vários itens.`

**2. Sistema de Biblioteca**
    - Livros (id, titulo, autor, ano_publicacao)
    - Alunos (id, nome, matricula, curso)
    - Emprestimos (id, id_aluno, id_livro, data_emprestimo, data_devolucao)

`📝 Explicação: Cada empréstimo está vinculado a um único aluno e a um único livro.`

**3. Sistema de Controle de Consultas Médicas**
    - Pacientes (id, nome, data_nascimento, telefone)
    - Medicos (id, nome, especialidade, crm)
    - Consultas (id, id_paciente, id_medico, data_consulta, descricao)

`📝 Explicação: Cada consulta é associada a um único paciente e a um único médico.`

**4. Sistema de Gerenciamento de Turmas**
    - Professores (id, nome, disciplina, email)
    - Turmas (id, nome, id_professor, horario)
    - Alunos (id, nome, matricula, curso, id_turma)

`📝 Explicação: Cada turma tem um único professor e vários alunos, mas cada aluno pertence a apenas uma turma.`


Ou, se preferir, use um dos modelos trabalhados na disciplina de Banco de Dados durante o ano letivo que está chegando ao fim.



**Requisitos:**
- Utilizar Python e Django
- Utilizar Django REST Framework
- Utilizar Git e GitHub
- Enviar o link do repositório do GitHub
- **Data de entrega: 20/02/2025**
- **Observação: A atividade poderá ser em dupla.**


> Vá até ao [Google Classroom](https://classroom.google.com) da disciplina de **PRIN2 2024** para entregar o link do repositório do GitHub na atividade correspondente a esta tarefa.