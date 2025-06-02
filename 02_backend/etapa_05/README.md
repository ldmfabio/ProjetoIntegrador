# Atividade Integradora

## Projeto Integrador II + Banco de Dados

### **Atividade 1: Sistema de Gestão para Clínica Médica**
#### 📌 Contexto:
Você foi contratado para desenvolver o modelo de dados de um sistema de gestão para uma clínica médica. Esse sistema deve organizar informações sobre médicos, pacientes, consultas e prescrições de medicamentos.

#### ✅ Requisitos:
- Crie **no mínimo 7 entidades** relacionadas.
- Todas as entidades devem possuir uma **chave primária (PK)**.
- Onde necessário, crie **chaves estrangeiras (FK)** para representar os relacionamentos.
- Utilize os principais tipos de dados do **MySQL**: `VARCHAR`, `TEXT`, `INT`, `DECIMAL`, `DATE`, `DATETIME`.

#### 🔁 Relacionamentos:
- Cada **médico** pertence a uma **especialidade**.
- Um **paciente** pode realizar várias **consultas** com diferentes **médicos**.
- Cada **consulta** pode gerar uma ou mais **receitas**, que podem conter múltiplos **medicamentos**.

#### 💡 Exemplo de entidades:
- `Paciente`
- `Medico`
- `Especialidade`
- `Consulta`
- `Receita`
- `Medicamento`
- `Receita_Medicamento`

### Equipes que entregarão a atividade:
| **Turma** | **Integrantes** |
|------------|:-----------------|
| **1INFO2** | Luci, Sara, Yasmin |
| **1INFO2** | Emilly, Kelly, Pietra |

### **Atividade 2: Sistema de Pedidos para Indústria de Móveis**

#### 📌 Contexto:
Você foi chamado para projetar o banco de dados de uma **indústria moveleira**. A empresa precisa controlar os pedidos realizados pelos clientes, o estoque de produtos e matérias-primas, e as ordens de produção.

#### ✅ Requisitos:
- Modele **ao menos 7 entidades** com os relacionamentos entre elas.
- Utilize **PK em todas as entidades** e **FK quando houver dependência entre dados**.
- Utilize os tipos: `VARCHAR`, `INT`, `DECIMAL`, `DATE`, entre outros.

#### 🔁 Relacionamentos:
- Um **cliente** pode realizar vários **pedidos**.
- Um **pedido** contém vários **produtos**.
- Os **produtos** são produzidos com **ordens de produção**.
- Os **produtos** utilizam **matérias-primas**.

#### 💡 Exemplo de entidades:
- `Cliente`
- `Pedido`
- `Item_Pedido`
- `Produto`
- `Materia_Prima`
- `Ordem_Producao`
- `Funcionario`

### Equipes que entregarão a atividade:
| **Turma** | **Integrantes** |
|------------|:-----------------|
| **1INFO2** | João, Mateus Oliveira, Ricardo |
| **1INFO2** | André, Johann, Pedro |

### **Atividade 3: Sistema de Gestão de Propriedade Rural (Agronegócio)**
#### 📌 Contexto:
Você está desenvolvendo um sistema para auxiliar a gestão de **propriedades rurais**. O foco é o controle das culturas plantadas, uso de insumos e a colheita.

#### ✅ Requisitos:
- Crie **no mínimo 7 entidades** com relacionamentos reais do cotidiano no campo.
- Todas as entidades devem conter **PK** e utilizar **FK** quando necessário.
- Use os tipos: `VARCHAR`, `DATE`, `DECIMAL`, `INT`.

#### 🔁 Processos:
- Em uma **propriedade**, são realizados **plantios** de diferentes **culturas**.
- Cada **plantio** consome **insumos** e origina uma **colheita**.
- O **histórico de uso de insumos** deve ser registrado.
- Cada **propriedade** pode ter **funcionários** vinculados à execução das tarefas.

#### 💡 Exemplo de entidades:
- `Propriedade`
- `Cultura`
- `Plantio`
- `Colheita`
- `Insumo`
- `Uso_Insumo`
- `Funcionario`

### Equipes que entregarão a atividade:
| **Turma** | **Integrantes** |
|------------|:-----------------|
| **1INFO2** | Davi, Luiz, Vitor |

### **Atividade 4: Sistema de Gestão Escolar**

#### 📌 Contexto:
Você está desenvolvendo um sistema de **controle acadêmico** para uma instituição de ensino. O sistema deve permitir o gerenciamento de alunos, professores, cursos, disciplinas e a frequência nas aulas.

#### ✅ Requisitos:
- Crie **no mínimo 7 entidades** com **PK** e **FK** conforme necessário.
- Utilize os tipos: `VARCHAR`, `DATE`, `INT`, `DECIMAL`.

#### 🔁 Relacionamentos:
- **Alunos** se matriculam em **cursos**.
- **Cursos** possuem **disciplinas**.
- **Disciplinas** são ministradas por **professores**, organizadas em **turmas**.
- **Alunos** têm **frequência** registrada por **turma**.

#### 💡 Exemplo de entidades:
- `Aluno`
- `Curso`
- `Matricula`
- `Disciplina`
- `Professor`
- `Turma`
- `Frequencia`

### Equipes que entregarão a atividade:
| **Turma** | **Integrantes** |
|------------|:-----------------|
| **1INFO2** | Amanda, Heloisa, Roberta |
| **1INFO2** | Breno, Geanluca, José |

### **Atividade 5: Sistema de Hotelaria**

#### 📌 Contexto:
Você foi contratado para construir um sistema para gerenciar **hóspedes**, **reservas**, **pagamentos** e **serviços oferecidos** por um hotel.

#### ✅ Requisitos:
- Modele **no mínimo 7 entidades** com **PK** e **FK**.
- Utilize os tipos de dados: `VARCHAR`, `DATE`, `DECIMAL`, `INT`.

#### 🔁 Relacionamentos:
- Um **hóspede** pode fazer **reservas** em **quartos**.
- Cada **reserva** pode incluir **serviços adicionais**.
- O **pagamento** é vinculado à **reserva**.
- **Funcionários** podem ser registrados para controle de pessoal.

#### 💡 Exemplo de entidades:
- `Hospede`
- `Reserva`
- `Quarto`
- `Pagamento`
- `Servico`
- `Reserva_Servico`
- `Funcionario`

### Equipes que entregarão a atividade:
| **Turma** | **Integrantes** |
|------------|:-----------------|
| **1INFO2** | Afonso, Bianca, Eric |
| **1INFO2** | Arthur, Matheus Lima, Renan |

## **Requisitos:**
- Utilizar Python e Django
- Utilizar Django REST Framework
- Utilizar Git e GitHub
- Enviar o link do repositório do GitHub
- **Data de entrega: 24/06/2025**
- **Observação: A atividade poderá ser, no máximo, em grupos compostos por TRÊS PESSOAS!**
