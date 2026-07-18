# Confeitaria ERP

Sistema de gerenciamento para pequenos produtores alimentícios que trabalham sob encomenda.

O objetivo do projeto é auxiliar confeiteiras e salgadeiras autônomas no controle de clientes, pedidos, produção e ingredientes, substituindo controles manuais realizados através de cadernos e conversas espalhadas em aplicativos de mensagem.

> Projeto desenvolvido com foco em estudo de Arquitetura de Software, DDD, Clean Architecture, desenvolvimento Full Stack e boas práticas de engenharia de software.

---

# Objetivo

Desenvolver uma solução simples e eficiente para controlar o fluxo operacional de um negócio de produção sob encomenda:

- Cadastro de clientes.
- Gerenciamento de produtos e combos.
- Controle de pedidos.
- Planejamento da produção.
- Controle de ingredientes.
- Cálculo de necessidades de matéria-prima.
- Acompanhamento de entregas e pagamentos.

---

# Contexto do Problema

Pequenos produtores que trabalham sob encomenda normalmente controlam seus pedidos através de:

- Cadernos.
- Conversas no WhatsApp.
- Planilhas simples.
- Memória.

Isso pode gerar problemas como:

- Erros na quantidade produzida.
- Esquecimento de pedidos.
- Falta de ingredientes.
- Compras de última hora.
- Dificuldade para acompanhar pagamentos.

O sistema busca centralizar essas informações em um único lugar.

---

# Documentação

A documentação do projeto está disponível na pasta `/docs`.

Documentos:

| Documento | Descrição |
|---|---|
| [Product Vision](docs/00-vision.md) | Visão do produto, objetivo e problema que será resolvido |
| [Persona](docs/01-persona.md) | Perfil do usuário principal do sistema |
| [Business Rules](docs/02-business-rules.md) | Regras de negócio do domínio |
| [Domain Model](docs/03-domain-model.md) | Modelo das entidades e relacionamentos principais |
| [MVP](docs/04-mvp.md) | Escopo inicial e funcionalidades prioritárias |
| [Arquitetura](docs/05-architecture.md) | Decisões arquiteturais e organização da solução |
| [Backlog](docs/backlog) | Organização das funcionalidades e tarefas de desenvolvimento |

---

# Funcionalidades do MVP

O MVP contempla:

## Clientes

- Cadastro de clientes.
- Histórico de pedidos.
- Controle de informações de contato.

## Produtos

- Cadastro de produtos.
- Variações de sabores.
- Controle de preços.

## Pedidos

- Criação de pedidos sob encomenda.
- Controle de status.
- Associação com clientes.

## Ingredientes

- Cadastro de matérias-primas.
- Controle de estoque.
- Planejamento de necessidade de compra.

## Produção

- Organização dos pedidos por data de entrega.
- Visualização da produção necessária.

---

# Arquitetura

O projeto utiliza uma arquitetura baseada em:

- Clean Architecture simplificada.
- Organização por funcionalidades (Feature First).
- Separação entre domínio, aplicação, infraestrutura e apresentação.
- Código orientado a manutenção e evolução.

Fluxo principal:

```
Angular

↓

ASP.NET Core Web API

↓

Application

↓

Domain

↓

Infrastructure

↓

SQL Server
```

---

# Tecnologias

## Backend

- .NET 10 (LTS)
- ASP.NET Core Web API
- Entity Framework Core
- SQL Server
- FluentValidation
- Swagger / OpenAPI

## Frontend

- Angular 22
- Angular Material
- Tailwind CSS
- SCSS
- Angular Signals
- RxJS

## Ferramentas

- Git
- GitHub
- Docker

---

# Estrutura do Projeto

```
src/

├── ConfeitariaERP.Api
├── ConfeitariaERP.Application
├── ConfeitariaERP.Domain
└── ConfeitariaERP.Infrastructure

tests/

├── Domain.Tests
├── Application.Tests
└── Integration.Tests
```

---

# Princípios do Projeto

Durante o desenvolvimento serão priorizados:

- Código simples e legível.
- Baixo acoplamento.
- Alta coesão.
- Separação de responsabilidades.
- Evitar complexidade desnecessária.
- Evolução da arquitetura conforme a necessidade real do sistema.

---

# Status

🚧 Em desenvolvimento.