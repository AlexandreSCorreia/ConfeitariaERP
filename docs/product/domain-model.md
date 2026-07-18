# Modelo de Domínio

## Objetivo

Este documento descreve as principais entidades do domínio e seus relacionamentos.

Seu objetivo é representar o negócio de forma independente da implementação.

---

# Visão Geral

```text
Cliente
    │
    └── Pedido
            │
            ├── ItemPedido
            │       │
            │       └── Produto
            │               │
            │               ├── Receita
            │               │       │
            │               │       └── ReceitaIngrediente
            │               │               │
            │               │               └── Ingrediente
            │               │
            │               └── Categoria
            │
            ├── Pagamento
            │
            └── Entrega

Ingrediente
        │
        └── MovimentaçãoEstoque
```

---

# Entidades

## Cliente

Representa uma pessoa que realiza pedidos.

### Responsabilidades

- Manter dados cadastrais.
- Possuir histórico de pedidos.

### Relacionamentos

- 1 Cliente possui vários Pedidos.

---

## Pedido

Representa uma encomenda realizada por um cliente.

### Responsabilidades

- Controlar status.
- Agrupar itens.
- Definir data de entrega.
- Controlar pagamento.

### Relacionamentos

- Pertence a um Cliente.
- Possui vários Itens.
- Possui um ou mais Pagamentos.

---

## ItemPedido

Representa um produto dentro de um pedido.

### Responsabilidades

- Definir quantidade.
- Definir preço no momento da venda.

### Relacionamentos

- Pertence a um Pedido.
- Referencia um Produto.

---

## Produto

Representa um item vendido.

Exemplos

- Coxinha
- Brigadeiro
- Bolo

### Responsabilidades

- Definir preço.
- Definir receita.

### Relacionamentos

- Possui uma Receita.
- Pertence a uma Categoria.

---

## Receita

Define como um produto é produzido.

### Responsabilidades

- Relacionar ingredientes.
- Definir quantidade de consumo.

---

## ReceitaIngrediente

Representa um ingrediente utilizado em uma receita.

### Responsabilidades

- Informar quantidade.
- Informar unidade.

---

## Ingrediente

Representa uma matéria-prima.

Exemplos

- Farinha
- Frango
- Leite
- Queijo

### Responsabilidades

- Controlar estoque.
- Registrar movimentações.

---

## MovimentaçãoEstoque

Representa entradas e ajustes de estoque.

### Responsabilidades

- Registrar entradas.
- Registrar ajustes.
- Manter histórico.

---

## Pagamento

Representa um pagamento realizado pelo cliente.

### Responsabilidades

- Registrar valor.
- Registrar forma de pagamento.
- Registrar data.

---

## Entrega

Representa a entrega do pedido.

### Responsabilidades

- Registrar data.
- Registrar situação.