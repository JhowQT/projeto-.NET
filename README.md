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
