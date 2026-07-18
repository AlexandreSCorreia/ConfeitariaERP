# Arquitetura

## Objetivo

Descrever a arquitetura da solução, as tecnologias adotadas e as principais decisões técnicas utilizadas durante o desenvolvimento do projeto.

O principal objetivo desta arquitetura é manter o projeto simples, organizado e de fácil manutenção, evitando complexidade desnecessária para um sistema de pequeno e médio porte.

---

# Visão Geral

O sistema é composto por duas aplicações independentes:

- Frontend Web
- Backend API

A comunicação ocorre através de uma API REST utilizando JSON sobre HTTPS.

```text
┌─────────────────────┐
│ Angular 22          │
│ Frontend            │
└──────────┬──────────┘
           │ HTTP / JSON
           ▼
┌─────────────────────┐
│ ASP.NET Core 10 API │
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│ SQL Server          │
└─────────────────────┘
```

---

# Tecnologias

## Frontend

- Angular 22
- Angular Material (Material Design 3)
- Tailwind CSS 4
- SCSS
- Angular Signals
- RxJS

## Backend

- .NET 10 (LTS)
- ASP.NET Core Web API
- Entity Framework Core
- SQL Server
- FluentValidation
- JWT Authentication
- Swagger / OpenAPI

## Ferramentas

- Docker
- Docker Compose
- Git
- GitHub

---

# Arquitetura da Solução

O projeto utiliza os princípios da Clean Architecture com uma abordagem simplificada.

A organização é baseada em funcionalidades (Feature First), reduzindo a quantidade de arquivos necessários para implementar novas funcionalidades.

```text
ConfeitariaERP.sln

src/

├── ConfeitariaERP.Api
├── ConfeitariaERP.Application
├── ConfeitariaERP.Domain
└── ConfeitariaERP.Infrastructure

tests/

├── ConfeitariaERP.Domain.Tests
├── ConfeitariaERP.Application.Tests
└── ConfeitariaERP.Integration.Tests
```

---

# Responsabilidade dos Projetos

## ConfeitariaERP.Api

Responsável por:

- Controllers
- Middlewares
- Configuração da aplicação
- Autenticação
- Injeção de Dependência
- Swagger

---

## ConfeitariaERP.Application

Responsável pelos casos de uso da aplicação.

Cada funcionalidade possui seus próprios arquivos, evitando espalhar código por diversas pastas.

Exemplo:

```text
Customers

CustomerService.cs

CustomerValidator.cs

CustomerMapper.cs

Dtos.cs
```

Essa estrutura reduz a quantidade de arquivos e facilita a manutenção do projeto.

---

## ConfeitariaERP.Domain

Responsável por representar o domínio do negócio.

Contém:

- Entidades
- Value Objects
- Enums
- Interfaces de domínio
- Regras de negócio

O domínio não possui dependência das demais camadas.

---

## ConfeitariaERP.Infrastructure

Responsável pelo acesso à infraestrutura da aplicação.

Contém:

- Entity Framework Core
- DbContext
- Configurações do banco
- Migrations
- Implementação de serviços externos

---

# Organização da Camada Application

A camada Application será organizada por funcionalidades.

```text
Application/

Customers/
    CustomerService.cs
    CustomerValidator.cs
    CustomerMapper.cs
    Dtos.cs

Products/
    ProductService.cs
    ProductValidator.cs
    ProductMapper.cs
    Dtos.cs

Orders/
    OrderService.cs
    OrderValidator.cs
    OrderMapper.cs
    Dtos.cs

Ingredients/
    IngredientService.cs
    IngredientValidator.cs
    IngredientMapper.cs
    Dtos.cs

Recipes/
    RecipeService.cs
    RecipeValidator.cs
    RecipeMapper.cs
    Dtos.cs

Common/
    Result.cs
    PagedResult.cs
```

Cada funcionalidade concentra seus arquivos em um único local, facilitando a localização e manutenção do código.

---

# Organização do Frontend

O Frontend também será organizado por funcionalidades.

```text
app/

core/

shared/

layout/

features/

    customers/

    products/

    ingredients/

    recipes/

    orders/
```

Essa organização mantém o Frontend consistente com a estrutura do Backend.

---

# Comunicação

Todo acesso aos dados ocorre através da API.

```text
Angular

↓

REST API

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

# Padrões Utilizados

## Backend

- Clean Architecture (simplificada)
- Feature First
- Dependency Injection
- FluentValidation
- Extension Methods para mapeamento entre Entidades e DTOs
- Result Pattern

## Frontend

- Standalone Components
- Angular Signals
- RxJS para comunicação assíncrona
- Lazy Loading
- Route Guards
- HTTP Interceptors

---

# Mapeamento entre Objetos

O projeto utiliza mapeamentos manuais através de Extension Methods.

Não serão utilizadas bibliotecas de mapeamento automático, como AutoMapper.

Objetivos:

- Código explícito.
- Facilidade de manutenção.
- Facilidade para depuração.
- Menor quantidade de dependências.

---

# Persistência

- SQL Server como banco principal.
- Entity Framework Core como ORM.
- Code First.
- Migrations para versionamento do banco.

---

# Segurança

- JWT Authentication.
- Authorization por Roles.
- FluentValidation para validação das entradas.
- Middleware global para tratamento de exceções.

---

# Testes

Serão implementados:

- Testes de domínio.
- Testes da camada Application.
- Testes de integração da API.

---

# Objetivos Arquiteturais

Durante o desenvolvimento serão priorizados os seguintes princípios:

- Simplicidade.
- Legibilidade.
- Baixo acoplamento.
- Alta coesão.
- Fácil manutenção.
- Fácil evolução.
- Organização por funcionalidades.
- Código explícito.
- Evitar abstrações prematuras.

Sempre que possível, soluções simples serão preferidas em relação a arquiteturas mais complexas.