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

| Sprint | Tarefa                                                         | Responsável(is)            | Desenvolvimento    | Testes            | Revisão          | Deploy           | Observações                                                            |
| ------ | -------------------------------------------------------------- | -------------------------- | ------------------ | ----------------- | ---------------- | ---------------- | ---------------------------------------------------------------------- |
| 1      | Configuração do ambiente Java e PostgreSQL                     | Pedro Paulo, Lucas Andrade | 01/07/2025 (1 dia) | 02/07 (1 dia)     | 03/07 (1 dia)    | 04/07 (1 dia)    | Criação do projeto, estrutura de pacotes, conexão inicial com o banco. |
| 2      | Criação do banco e tabelas (curso, estudante, turma)           | Lucas Andrade              | 05-06/07 (2 dias)  | 07/07 (1 dia)     | 08/07 (1 dia)    | 09/07 (1 dia)    | Estrutura com chaves estrangeiras e enums no PostgreSQL.               |
| 3      | Implementação da classe ConexaoPostgres                        | Pedro Paulo                | 10/07 (1 dia)      | 11/07 (1 dia)     | 11/07 (meio dia) | 12/07 (meio dia) | Classe genérica para reuso em todos os DAOs.                           |
| 4      | Modelagem das entidades (Curso, Estudante, Turma + enums)      | Pedro Paulo                | 13-14/07 (2 dias)  | 15/07 (1 dia)     | 16/07 (1 dia)    | 17/07 (1 dia)    | Uso correto de enums e encapsulamento com boas práticas.               |
| 5      | DAO completo de Curso (CRUD com PostgreSQL)                    | Pedro Paulo                | 18-19/07 (2 dias)  | 20/07 (1 dia)     | 21/07 (1 dia)    | 22/07 (1 dia)    | Inserção e atualização separadas, uso de código como identificador.    |
| 6      | DAO completo de Estudante (CRUD + validações)                  | Pedro Paulo                | 23-25/07 (3 dias)  | 26-27/07 (2 dias) | 28/07 (1 dia)    | 29/07 (1 dia)    | Validação de CPF, ligação com Curso, foreign key.                      |
| 7      | DAO de Turma (CRUD com enum Período e chave estrangeira Curso) | Pedro Paulo                | 30-31/07 (2 dias)  | 01/08 (1 dia)     | 02/08 (1 dia)    | 03/08 (1 dia)    | Uso de enum Periodo, retorno do código de curso.                       |
| 8      | Interface de cadastro de Curso (Swing)                         | Carla Souza                | 04/08 (1 dia)      | 05/08 (1 dia)     | 05/08 (meio dia) | 06/08 (meio dia) | Validações básicas, campos obrigatórios.                               |
| 9      | Interface de cadastro de Estudantes (Swing + validações)       | Carla Souza                | 07-08/08 (2 dias)  | 09-10/08 (2 dias) | 11/08 (1 dia)    | 12/08 (1 dia)    | CPF único, associação com curso, campos obrigatórios.                  |
| 10     | Interface de cadastro de Turma                                 | Carla Souza                | 13/08 (1 dia)      | 14/08 (1 dia)     | 15/08 (1 dia)    | 16/08 (1 dia)    | Uso de ComboBox para seleção de curso e período.                       |
| 11     | Interface de listagem de Cursos                                | Carla Souza                | 17/08 (meio dia)   | 17/08 (meio dia)  | 18/08 (meio dia) | 18/08 (meio dia) | Ordenação por código, simples iteração.                                |
| 12     | Interface de listagem de Estudantes                            | Carla Souza                | 19/08 (1 dia)      | 20/08 (1 dia)     | 21/08 (1 dia)    | 21/08 (meio dia) | Inclusão de botão de exclusão e busca por código.                      |
| 13     | Interface de listagem de Turmas                                | Carla Souza                | 22/08 (1 dia)      | 23/08 (1 dia)     | 24/08 (1 dia)    | 25/08 (1 dia)    | Exibição de curso vinculado à turma.                                   |
| 14     | Tratamento de enums no banco (nivel\_enum, periodo\_enum)      | Pedro Paulo, Lucas Andrade | 26/08 (1 dia)      | 27/08 (1 dia)     | 28/08 (1 dia)    | 28/08 (meio dia) | Uso de `::enum`, `.name()` e integração JDBC.                          |
| 15     | Implementar retorno de ID com RETURNING no SQL                 | Pedro Paulo                | 29/08 (1 dia)      | 30/08 (1 dia)     | 31/08 (1 dia)    | 01/09 (1 dia)    | Necessário para usar o código como PK no app.                          |
| 16     | Ajuste de exclusão usando código no lugar de CPF               | Pedro Paulo                | 02/09 (1 dia)      | 03/09 (1 dia)     | 04/09 (1 dia)    | 04/09 (meio dia) | Correção da lógica de busca e exclusão.                                |
| 17     | Testes integrados e fluxos completos                           | Pedro Paulo, Carla Souza   | 05-07/09 (3 dias)  | 08-09/09 (2 dias) | 10/09 (1 dia)    | 11/09 (1 dia)    | Testes ponta a ponta de CRUDs e interfaces.                            |
| 18     | Documentação final (README, DER, Manual de Uso)                | Pedro Paulo                | 12-13/09 (2 dias)  | 14/09 (1 dia)     | 15/09 (1 dia)    | 15/09 (meio dia) | Instruções de execução, prints, estrutura clara.                       |
| 19     | Otimizações e melhorias finais no código e UI                  | Pedro Paulo, Carla Souza   | 16-18/09 (3 dias)  | 19/09 (1 dia)     | 20/09 (1 dia)    | 21/09 (1 dia)    | Refatoração, melhorias visuais, identação e consistência.              |
| 20     | Apresentação final do projeto                                  | Toda a equipe              | 22/09 (1 dia)      | -                 | -                | -                | Demonstração para banca com explicações técnicas e práticas.           |


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



