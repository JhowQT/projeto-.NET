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
