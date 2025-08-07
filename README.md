# 🎓 Sistema de Gestão de Cursos - Java + PostgreSQL

## 📌 Descrição do Projeto

O **Sistema de Gestão de Cursos** é uma aplicação desenvolvida em **Java** com interface gráfica **Swing**, persistência de dados em **PostgreSQL** e arquitetura organizada seguindo boas práticas de **MVC (Model-View-Controller)**.

O sistema permite:

* Cadastro e listagem de **Cursos**
* Cadastro e listagem de **Estudantes**
* Cadastro e listagem de **Turmas**
* Exclusão de registros diretamente pela interface
* Uso de **enums** para campos como `Nível` e `Período` integrados ao PostgreSQL
* Captura do **código gerado** para novos estudantes diretamente no momento da inserção

O projeto foi desenvolvido seguindo a **Metodologia Ágil (Scrum)**, com divisão em **20 Sprints** e participação de **três desenvolvedores** com funções definidas:

* **Pedro Paulo** → Líder técnico e responsável pelo back-end e integração com banco de dados
* **Carla Souza** → Desenvolvedora front-end, responsável pelas interfaces gráficas
* **Lucas Andrade** → Analista de banco de dados e responsável pela modelagem e manutenção das tabelas

---

## 🛠 Tecnologias Utilizadas

### **Front-end**

* Java Swing (Interface gráfica)

### **Back-end**

* Java 17+
* JDBC (Java Database Connectivity)

### **Banco de Dados**

* PostgreSQL 15+
* Enums nativos para campos `nivel_enum` e `periodo_enum`

---

## 📅 Planejamento Ágil - Sprints

| Nº | Sprint                                                         | Desenvolvedores            | O que foi feito                                                          | O que cada um fez                                         | Desenvolvimento | Testes   | Revisão | Deploy  | Data Inicial | Data Final Prevista | Observações                    |
| -- | -------------------------------------------------------------- | -------------------------- | ------------------------------------------------------------------------ | --------------------------------------------------------- | --------------- | -------- | ------- | ------- | ------------ | ------------------- | ------------------------------ |
| 1  | Configuração do ambiente Java e PostgreSQL                     | Pedro Paulo, Lucas Andrade | Configuração IDE, biblioteca JDBC, ambiente PostgreSQL, conexão inicial. | Pedro: Configuração IDE e JDBC.<br>Lucas: Setup do banco. | 1 dia           | 0.5 dia  | 0.5 dia | -       | 01/07/2025   | 02/07/2025          | Setup inicial essencial        |
| 2  | Criação do banco e tabelas                                     | Lucas Andrade              | Script SQL criação tabelas Curso, Estudante, Turma com enums e FK.       | Lucas: Modelagem e criação de tabelas.                    | 1.5 dias        | 0.5 dia  | 0.5 dia | -       | 03/07/2025   | 05/07/2025          | Inclui enums e relacionamentos |
| 3  | Implementação da classe ConexaoPostgres                        | Pedro Paulo                | Classe para conexão genérica reutilizável no DAO.                        | Pedro: Classe de conexão JDBC.                            | 0.5 dia         | 0.5 dia  | 0.5 dia | -       | 06/07/2025   | 07/07/2025          | Base para DAOs reutilizável    |
| 4  | Modelagem das entidades Java (Curso, Estudante, Turma + Enums) | Pedro Paulo                | Criação das classes modelo com encapsulamento e uso correto de enums.    | Pedro: Modelos e construtores.                            | 1.5 dias        | 0.5 dia  | -       | -       | 08/07/2025   | 09/07/2025          | Entidades alinhadas ao BD      |
| 5  | DAO completo de Curso (CRUD + validações)                      | Pedro Paulo                | CRUD para Curso, métodos inserir, listar, atualizar, excluir.            | Pedro: DAO com JDBC + validações básicas.                 | 2 dias          | 1 dia    | 0.5 dia | 0.5 dia | 10/07/2025   | 13/07/2025          | Validação implementada         |
| 6  | DAO completo de Estudante (CRUD + vínculos)                    | Pedro Paulo                | CRUD Estudante com FK Curso e validação de CPF.                          | Pedro: DAO completo + validações.                         | 3 dias          | 1.5 dias | 1 dia   | 0.5 dia | 14/07/2025   | 18/07/2025          | Controle rígido de cadastro    |
| 7  | DAO de Turma (CRUD + enum Período e FK Curso)                  | Pedro Paulo                | Manipulação enum Período e relacionamento Curso.                         | Pedro: DAO completo.                                      | 2 dias          | 1 dia    | 0.5 dia | 0.5 dia | 19/07/2025   | 22/07/2025          | Relacionamento bem definido    |
| 8  | Interface Swing para cadastro de Curso                         | Carla Souza                | Tela com validações básicas.                                             | Carla: Interface e validações.                            | 0.5 dia         | 0.5 dia  | 0.5 dia | 0.5 dia | 23/07/2025   | 23/07/2025          | Layout e validações mínimas    |
| 9  | Interface Swing para Estudantes                                | Carla Souza                | Formulário completo com vínculo de curso.                                | Carla: UI + chamadas controller.                          | 2 dias          | 1 dia    | 0.5 dia | 0.5 dia | 24/07/2025   | 26/07/2025          | Captura de dados validada      |
| 10 | Interface Swing para Turmas                                    | Carla Souza                | Tela com ComboBox de períodos e curso.                                   | Carla: UI + vinculação DAO.                               | 1 dia           | 0.5 dia  | 0.5 dia | 0.5 dia | 27/07/2025   | 28/07/2025          | Combos + validações ativas     |
| 11 | Interface de listagem de Cursos                                | Carla Souza                | Listagem com exclusão e ordenação.                                       | Carla: Interface + métodos.                               | 0.5 dia         | 0.5 dia  | 0.5 dia | 0.5 dia | 29/07/2025   | 29/07/2025          | Interface leve e objetiva      |
| 12 | Interface de listagem de Estudantes                            | Carla Souza                | Tabela com busca e exclusão.                                             | Carla: Tabela + lógica.                                   | 1 dia           | 0.5 dia  | 0.5 dia | 0.5 dia | 30/07/2025   | 31/07/2025          | Inclusão de filtros            |
| 13 | Interface de listagem de Turmas                                | Carla Souza                | Mostra turmas + curso vinculado.                                         | Carla: Listagem e interação.                              | 1 dia           | 0.5 dia  | 0.5 dia | 0.5 dia | 01/08/2025   | 02/08/2025          | Visualização detalhada         |
| 14 | Tratamento de enums com JDBC                                   | Pedro, Lucas               | Conversão correta entre Java e BD.                                       | Ambos: Implementação + testes.                            | 1 dia           | 1 dia    | 0.5 dia | 0.5 dia | 03/08/2025   | 04/08/2025          | Integração de enums estável    |
| 15 | Retorno de ID via RETURNING SQL                                | Pedro Paulo                | Recuperar chave primária automaticamente.                                | Pedro: Otimização DAO.                                    | 1 dia           | 0.5 dia  | 0.5 dia | 0.5 dia | 05/08/2025   | 06/08/2025          | Facilita rastreabilidade       |
| 16 | Exclusão por código (não CPF)                                  | Pedro Paulo                | Melhoria na exclusão por chave primária.                                 | Pedro: Refatoração DAO.                                   | 1 dia           | 0.5 dia  | 0.5 dia | 0.5 dia | 07/08/2025   | 08/08/2025          | Melhora desempenho             |
| 17 | Testes integrados e fluxo completo                             | Pedro, Carla               | Testes ponta a ponta e bugs UI.                                          | Pedro: Back-end.<br>Carla: UI.                            | 3 dias          | 2 dias   | 1 dia   | 1 dia   | 09/08/2025   | 14/08/2025          | Validação geral completa       |
| 18 | Documentação final (README, DER, Manual)                       | Pedro Paulo                | Criação de documentos do projeto.                                        | Pedro: Diagrama e manuais.                                | 2 dias          | 1 dia    | 0.5 dia | 0.5 dia | 15/08/2025   | 17/08/2025          | Documentação completa          |
| 19 | Otimizações finais no código/UI                                | Pedro, Carla               | Refatorações, ajustes estéticos.                                         | Pedro: Código<br>Carla: Layouts.                          | 3 dias          | 1 dia    | 1 dia   | 1 dia   | 18/08/2025   | 22/08/2025          | Melhorias finais               |
| 20 | Apresentação Final (Banca)                                     | Equipe                     | Demonstração, dúvidas e entrega.                                         | Todos: Apresentação.                                      | 1 dia           | -        | -       | -       | 23/08/2025   | 23/08/2025          | Encerramento do projeto        |



---

## 📄 Partes mais complexas do código

### **1. Inserção de Curso com Enum PostgreSQL**

```java
public void inserir(Curso curso) {
    String sql = "INSERT INTO curso (codigo, nome, carga_horaria, nivel) VALUES (?, ?, ?, ?::nivel_enum)";
    try (Connection conn = ConexaoPostgres.getConnection();
         PreparedStatement stmt = conn.prepareStatement(sql)) {
        stmt.setString(1, curso.getCodigo());
        stmt.setString(2, curso.getNome());
        stmt.setInt(3, curso.getCargaHoraria());
        stmt.setString(4, curso.getNivel().name()); // Enum em formato compatível
        stmt.executeUpdate();
    } catch (SQLException e) {
        throw new RuntimeException("Erro ao inserir curso no PostgreSQL: " + e.getMessage(), e);
    }
}
```

💡 **Importância:** Necessário uso de `::nivel_enum` para conversão explícita no PostgreSQL.

---

### **2. Inserção de Turma com Enum PostgreSQL**

```java
public void inserir(Turma turma) {
    String sql = "INSERT INTO turma (codigo, data_inicio, data_fim, periodo, curso_codigo) VALUES (?, ?, ?, ?::periodo_enum, ?)";
    try (Connection conn = ConexaoPostgres.getConnection();
         PreparedStatement stmt = conn.prepareStatement(sql)) {
        stmt.setString(1, turma.getCodigo());
        stmt.setDate(2, Date.valueOf(turma.getDataInicio()));
        stmt.setDate(3, Date.valueOf(turma.getDataFim()));
        stmt.setString(4, turma.getPeriodo().name());
        stmt.setString(5, turma.getCurso().getCodigo());
        stmt.executeUpdate();
    } catch (SQLException e) {
        throw new RuntimeException("Erro ao inserir turma: " + e.getMessage(), e);
    }
}

```

💡 **Importância:** Assim como no curso, exige `::periodo_enum` para compatibilidade.

---

### **3. Inserção de Estudante com Captura de Código Automático**

```java
public void inserir(Estudante estudante) {
    String sql = "INSERT INTO estudante (nome, cpf, email, telefone, endereco, curso_codigo) VALUES (?, ?, ?, ?, ?, ?) RETURNING codigo";
    try (Connection conn = ConexaoPostgres.getConnection();
         PreparedStatement stmt = conn.prepareStatement(sql)) {
        stmt.setString(1, estudante.getNome());
        stmt.setString(2, estudante.getCpf());
        stmt.setString(3, estudante.getEmail());
        stmt.setString(4, estudante.getTelefone());
        stmt.setString(5, estudante.getEndereco());
        stmt.setString(6, estudante.getCurso().getCodigo());
        try (ResultSet rs = stmt.executeQuery()) {
            if (rs.next()) {
                estudante.setCodigo(rs.getInt("codigo"));
            } else {
                throw new SQLException("Falha ao obter o código do estudante inserido.");
            }
        }
    } catch (SQLException e) {
        throw new RuntimeException("Erro ao inserir estudante: " + e.getMessage(), e);
    }
}
```

📌 Desafios Técnicos e Soluções
Durante o desenvolvimento do Sistema de Gestão de Cursos com Java + PostgreSQL, surgiram dois desafios principais que precisaram ser solucionados para garantir a integração correta entre o sistema e o banco de dados.

1. Problema com Enums no PostgreSQL
O PostgreSQL utiliza tipos ENUM nativos (nivel_enum e periodo_enum), mas ao tentar salvar diretamente com PreparedStatement.setString(), ocorria erro de conversão, pois o banco exige um tipo específico.

✅ Solução adotada:

Ajustar as queries para utilizar conversão explícita (?::nivel_enum e ?::periodo_enum).

Utilizar enum.name() no Java para garantir que o valor enviado corresponda exatamente ao formato salvo no banco (sem acentos e no padrão maiúsculo).

💡 Isso garantiu que valores como "Básico" fossem convertidos corretamente para BASICO no momento da inserção.

2. Problema na Captura do ID do Estudante
Ao inserir um novo estudante, era necessário capturar automaticamente o ID (código) gerado pelo banco, pois ele é usado como chave primária em outras tabelas.
Sem isso, não seria possível manter o vínculo correto com outros registros, como matrículas e turmas.

✅ Solução adotada:

Alterar o SQL de inserção para incluir RETURNING codigo.

Ler o valor retornado imediatamente após a execução com ResultSet e definir no objeto Java.

💡 Isso garantiu que o ID recém-gerado estivesse disponível assim que o estudante fosse cadastrado.

📎 Resumo:
Essas adaptações foram cruciais para que o sistema conseguisse persistir corretamente os dados, respeitar os tipos ENUM do PostgreSQL e capturar IDs automaticamente, garantindo total consistência entre a interface gráfica, os métodos DAO e o banco de dados.


🖼 Capturas de Tela da Interface

📌 1. Cadastro de Curso com Enum 


![Cadastro Curso](docs/Interfa-cadastro-curso-enum.png)

📌 2. Cadastro de Turma com Enum  


![Cadastro Turma](docs/Interfa-cadastro-turma-enum.png)

📌 3. Lista de Estudantes com Curso Vinculado  


![Lista Estudantes](docs/Interfa-lista-estudante-curso.png)


📊 Vantagens e Dificuldades da Metodologia Ágil

✅ **Vantagens**
- Entregas rápidas e incrementais
- Feedback constante e adaptação às mudanças
- Melhor comunicação entre membros da equipe
- Mais fácil de identificar e corrigir erros cedo

⚠️ **Dificuldades**
- Exige disciplina e comprometimento com prazos
- Necessário bom entendimento das tarefas para evitar retrabalho
- Para equipes pequenas, algumas cerimônias podem ser sobrecarregantes
- Integração contínua requer atenção constante a testes


👤 Autor  
**Pedro Paulo Damasceno Muniz**  
Estudante de Análise e Desenvolvimento de Sistemas – Uniasselvi – Blumenau  
Participante do treinamento intensivo +Devs2Blu – Blumenau  
📌 GitHub: [https://github.com/Damasceno11](https://github.com/Damasceno11)  
📌 LinkedIn: [https://www.linkedin.com/in/pedro-paulo-damasceno-muniz](https://www.linkedin.com/in/pedro-damasceno-23b330150/)







