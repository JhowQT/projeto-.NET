# 🏋️‍♂️ FIAP.CP2 – Sistema de Gerenciamento de Calistenia  

> Projeto desenvolvido como parte do **Checkpoint 2 – FIAP**  
> Aplicação **ASP.NET Core MVC + Entity Framework + Oracle Database**

---

## 🚀 Sobre o Projeto

O **FIAP.CP2** é um sistema web desenvolvido em **.NET MVC** com o objetivo de gerenciar **Alunos, Atletas, Exercícios e Treinos** de uma academia de calistenia.

O projeto implementa uma arquitetura completa **em camadas (Model, Data, Business e UI)** e utiliza **Entity Framework Core** para integração com o banco de dados **Oracle** hospedado no ambiente FIAP.

Ele oferece um painel administrativo com interface moderna e CRUD completo para todas as entidades.

---

## 🧩 Estrutura do Projeto


FIAP.CP2
```
├── FIAP.CP2.Data # Camada de acesso a dados (DbContext, Migrations)
│ ├── ApplicationDbContext.cs
│ └── ApplicationDbContextFactory.cs
│
├── FIAP.CP2.Model # Modelos das entidades (Aluno, Atleta, Exercicio, Treino)
│
├── FIAP.CP2.Business # (Camada de regras de negócio - opcional)
│
├── FIAP.CP2.UI # Interface Web MVC
│ ├── Controllers # Controladores com as rotas CRUD
│ ├── Views # Páginas Razor (.cshtml)
│ ├── wwwroot # Estilos, scripts e recursos estáticos
│ ├── appsettings.json # Configurações de conexão Oracle
│ └── Program.cs
```

---

## 🗄️ Banco de Dados Oracle

Conexão configurada com o banco **FIAP Oracle Cloud**:

```csharp
optionsBuilder.UseOracle(
    "User Id=rm560601;Password=040301;Data Source=oracle.fiap.com.br:1521/ORCL;"
);
```
---

## ⚙️ Funcionalidades Implementadas

| Módulo | Descrição | Funcionalidades |
|--------|------------|----------------|
| 🧍‍♂️ **Aluno** | Gerenciamento de alunos matriculados | Criar, editar, listar e excluir alunos |
| 🏃‍♂️ **Atleta** | Cadastro de atletas com nível e idade | CRUD completo + interface visual moderna |
| 💪 **Exercício** | Controle dos exercícios de calistenia | Campos: Nome, Grupo Muscular, Séries, Repetições e Duração |
| 📅 **Treino** | Organização dos treinos por dia da semana | Visualização de dias e duração dos treinos com *badges* coloridas |

---

## 🎨 Interface Visual

As views foram personalizadas com **Bootstrap** e **Bootstrap Icons**, aplicando um design simples, moderno e responsivo.

### 🏠 Página Inicial (Home)
- Exibe atalhos para todos os módulos: **Atletas**, **Exercícios** e **Treinos**
- Ícones de navegação com layout em *cards*

### 🏋️ Lista de Exercícios
- Tabela responsiva com ícones e cores dinâmicas por dificuldade  
- Botões estilizados com ícones: ✏️ **Editar**, 👁️ **Detalhes**, 🗑️ **Excluir**

### 📅 Lista de Treinos
- Exibe os treinos da semana com *badges* coloridas por dia  
- Ícones de calendário, cronômetro e edição  

---

## 🧠 Tecnologias Utilizadas

| Categoria | Ferramenta |
|------------|-------------|
| 💻 **Linguagem** | C# (.NET 9.0) |
| 🌐 **Framework Web** | ASP.NET Core MVC |
| 🧱 **ORM** | Entity Framework Core (Oracle Provider) |
| 🗄️ **Banco de Dados** | Oracle Cloud (FIAP) |
| 🎨 **Front-end** | Razor Pages + Bootstrap 5 + Bootstrap Icons |
| 🧩 **IDE** | Visual Studio 2022 |

---

## 🔧 Como Executar o Projeto

### 1️⃣ Clonar o Repositório
```bash
git clone https://github.com/JhowQT/projeto-.NET
```
---

### 2️⃣ Abrir no Visual Studio

- Vá em **File → Open → Project/Solution**  
- Selecione o arquivo `FIAP.CP2.sln`

---

### 3️⃣ Configurar a Conexão Oracle

Abra o arquivo `appsettings.json` e altere com seu **RM** e **senha**:

```json
"ConnectionStrings": {
  "DefaultConnection": "User Id=rmXXXXXX;Password=XXXXX;Data Source=oracle.fiap.com.br:1521/ORCL;"
}
```

---

### 4️⃣ Aplicar as Migrations (caso necessário)

No **Package Manager Console**, execute o comando:

```bash
Update-Database
```

---

### 5️⃣ Executar a Aplicação

Pressione **Ctrl + F5** ou clique em ▶️ **Run**  
O sistema abrirá automaticamente em:

```
https://localhost:7183/
```

---

## 📸 Exemplos de Telas

| Tela | Descrição |
|------|-----------|
| 🏠 **Home** | Página inicial com acesso aos módulos |
| 🏃 **Atletas** | CRUD completo com lista e botões de ação |
| 💪 **Exercícios** | Tabela responsiva com design moderno e ícones |
| 📅 **Treinos** | Visualização com cores e *badges* por dia da semana |

---

## 👨‍💻 Autor

**Jhonatan Quispe Torrez**  
🎓 *FIAP – Análise e Desenvolvimento de Sistemas*  
💼 *Projeto desenvolvido para a disciplina de Desenvolvimento Web com .NET*  
📧 **Contato:** [LinkedIn](https://www.linkedin.com) / [GitHub](https://github.com)

---

## 🔗 Endpoints da Aplicação

| Método | Endpoint | Descrição | Controller |
|---------|-----------|------------|-------------|
| **GET** | `/Atletas` | Lista todos os atletas cadastrados | `AtletasController` |
| **GET** | `/Atletas/Details/{id}` | Exibe detalhes de um atleta específico | `AtletasController` |
| **GET** | `/Atletas/Create` | Exibe o formulário de criação de atleta | `AtletasController` |
| **POST** | `/Atletas/Create` | Cadastra um novo atleta no banco | `AtletasController` |
| **GET** | `/Atletas/Edit/{id}` | Exibe o formulário de edição de um atleta | `AtletasController` |
| **POST** | `/Atletas/Edit/{id}` | Atualiza os dados de um atleta existente | `AtletasController` |
| **GET** | `/Atletas/Delete/{id}` | Exibe a confirmação de exclusão de atleta | `AtletasController` |
| **POST** | `/Atletas/Delete/{id}` | Exclui um atleta definitivamente | `AtletasController` |

| Método | Endpoint | Descrição | Controller |
|---------|-----------|------------|-------------|
| **GET** | `/Exercicios` | Lista todos os exercícios cadastrados | `ExerciciosController` |
| **GET** | `/Exercicios/Details/{id}` | Exibe detalhes de um exercício específico | `ExerciciosController` |
| **GET** | `/Exercicios/Create` | Exibe o formulário de criação de exercício | `ExerciciosController` |
| **POST** | `/Exercicios/Create` | Cadastra um novo exercício no banco | `ExerciciosController` |
| **GET** | `/Exercicios/Edit/{id}` | Exibe o formulário de edição de exercício | `ExerciciosController` |
| **POST** | `/Exercicios/Edit/{id}` | Atualiza os dados de um exercício existente | `ExerciciosController` |
| **GET** | `/Exercicios/Delete/{id}` | Exibe a confirmação de exclusão de exercício | `ExerciciosController` |
| **POST** | `/Exercicios/Delete/{id}` | Exclui um exercício definitivamente | `ExerciciosController` |

| Método | Endpoint | Descrição | Controller |
|---------|-----------|------------|-------------|
| **GET** | `/Treinos` | Lista todos os treinos cadastrados | `TreinosController` |
| **GET** | `/Treinos/Details/{id}` | Exibe detalhes de um treino específico | `TreinosController` |
| **GET** | `/Treinos/Create` | Exibe o formulário de criação de treino | `TreinosController` |
| **POST** | `/Treinos/Create` | Cadastra um novo treino no banco | `TreinosController` |
| **GET** | `/Treinos/Edit/{id}` | Exibe o formulário de edição de treino | `TreinosController` |
| **POST** | `/Treinos/Edit/{id}` | Atualiza os dados de um treino existente | `TreinosController` |
| **GET** | `/Treinos/Delete/{id}` | Exibe a confirmação de exclusão de treino | `TreinosController` |
| **POST** | `/Treinos/Delete/{id}` | Exclui um treino definitivamente | `TreinosController` |

---

🧩 **Observações:**
- Todos os endpoints seguem o padrão MVC e usam *views Razor* para renderizar as telas.  
- As ações **GET** exibem as páginas e as ações **POST** enviam os dados para o banco Oracle.  
- O Entity Framework Core faz o mapeamento automático das tabelas.  


