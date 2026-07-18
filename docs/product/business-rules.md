# Regras de Negócio

## Objetivo

Este documento descreve as regras de negócio do sistema.

As regras aqui definidas representam o funcionamento do negócio e devem ser respeitadas independentemente da tecnologia utilizada.

---

# Premissas

- O negócio trabalha exclusivamente por encomenda.
- Não existe venda imediata de produtos prontos.
- Não existe estoque de produtos acabados.
- O controle de estoque é realizado somente sobre ingredientes.
- Toda produção é planejada conforme os pedidos cadastrados e suas respectivas datas de entrega.
- O principal canal de comunicação com clientes é através de telefone/WhatsApp.

---

# Clientes

## RN-001

Todo pedido deve estar associado a um cliente.

---

## RN-002

Um cliente pode possuir diversos pedidos.

---

## RN-003

O histórico de pedidos do cliente deve ser preservado.

---

## RN-004

Todo cliente deve possuir:

- Nome.
- Telefone.
- Endereço.

---

## RN-005

O telefone do cliente deve ser único no sistema.

O telefone representa o principal meio de comunicação para contato sobre pedidos.

---

## RN-006

O email do cliente é opcional.

Quando informado, o email deve ser único no sistema.

---

## RN-007

O cadastro do cliente deve registrar a data de criação.

---

## RN-008

Alterações realizadas no cadastro devem atualizar a data de alteração.

---

## RN-009

Clientes que possuem pedidos vinculados não podem ser removidos.

---

# Pedidos

## RN-010

Todo pedido deve estar associado a um cliente.

---

## RN-011

Todo pedido deve possuir uma data de entrega.

---

## RN-012

Todo pedido deve possuir pelo menos um item.

---

## RN-013

Um pedido pode conter produtos e combos.

---

## RN-014

O pedido inicia com status **Pendente**.

---

## RN-015

Os status possíveis de um pedido são:

- Pendente
- Confirmado
- Em Produção
- Pronto
- Entregue
- Cancelado

---

## RN-016

A alteração de status deve respeitar o fluxo operacional.

Fluxo esperado:

Pendente

↓

Confirmado

↓

Em Produção

↓

Pronto

↓

Entregue

---

## RN-017

Pedidos cancelados não participam do planejamento da produção.

---

## RN-018

Pedidos entregues não podem ser alterados.

---

# Produtos

## RN-019

Produtos representam itens comercializados ao cliente.

Exemplos:

- Coxinha
- Brigadeiro
- Bolo

---

## RN-020

Produtos não possuem estoque próprio.

O controle é realizado através dos ingredientes utilizados na produção.

---

## RN-021

Um produto pode possuir variações.

Exemplo:

Coxinha:

- Frango
- Frango com Catupiry
- Carne

---

## RN-022

Cada variação de produto deve possuir preço definido.

---

## RN-023

Produtos utilizados em pedidos não podem ser removidos.

---

# Combos

## RN-024

Um combo é uma composição de diferentes produtos.

---

## RN-025

O combo possui preço próprio definido pelo negócio.

---

## RN-026

O preço do combo pode ser diferente da soma dos produtos que o compõem.

---

# Receitas

## RN-027

Produtos controlados pelo planejamento de produção devem possuir uma receita cadastrada.

---

## RN-028

Uma receita é composta por ingredientes.

---

## RN-029

Cada ingrediente utilizado em uma receita deve possuir uma quantidade definida.

---

# Ingredientes

## RN-030

Ingredientes representam matérias-primas utilizadas na produção.

---

## RN-031

Ingredientes possuem controle de estoque.

---

## RN-032

Entradas de estoque aumentam a quantidade disponível.

---

## RN-033

Ajustes de estoque podem aumentar ou diminuir a quantidade disponível.

---

## RN-034

O sistema deve impedir operações que deixem o estoque disponível negativo.

---

## RN-035

Ingredientes utilizados em receitas não podem ser removidos.

---

# Produção

## RN-036

A produção é organizada conforme a data de entrega dos pedidos.

---

## RN-037

Pedidos com entrega mais próxima possuem prioridade.

---

## RN-038

Pedidos cancelados não aparecem no planejamento de produção.

---

## RN-039

O sistema deve permitir visualizar os pedidos que precisam ser produzidos em determinada data.

---

# Planejamento de Ingredientes

## RN-040

O sistema deve calcular os ingredientes necessários com base nos pedidos planejados.

---

## RN-041

O cálculo deve considerar:

- Produtos solicitados.
- Quantidade dos itens.
- Receitas cadastradas.
- Estoque disponível.

---

## RN-042

Quando o estoque disponível for insuficiente, o ingrediente deve ser incluído na lista de compras.

---

# Pagamentos

## RN-043

Um pedido pode possuir pagamento parcial.

---

## RN-044

O sistema deve permitir identificar:

- Valor total do pedido.
- Valor pago.
- Valor pendente.

---

## RN-045

Um pedido pode ser entregue mesmo com pagamento pendente, conforme decisão do negócio.

---

# Auditoria

## RN-046

Os registros principais do sistema devem possuir data de criação.

---

## RN-047

Alterações em registros devem atualizar a data de alteração.

---

# Exclusões

## RN-048

Clientes não podem ser removidos caso possuam pedidos vinculados.

---

## RN-049

Produtos não podem ser removidos caso estejam associados a pedidos ou receitas.

---

## RN-050

Ingredientes utilizados em receitas não podem ser removidos.

---

# Glossário

## Cliente

Pessoa responsável por realizar pedidos.

---

## Pedido

Solicitação de produtos realizada por um cliente para uma determinada data de entrega.

---

## Produto

Item comercializado pelo negócio.

---

## Ingrediente

Matéria-prima utilizada para produzir os produtos.

---

## Receita

Definição dos ingredientes e quantidades necessários para produzir um produto.

---

## Combo

Conjunto de produtos vendidos por um preço único.

---

## Produção

Processo de fabricação dos produtos conforme os pedidos recebidos.

---

## Planejamento

Processo de organização dos pedidos e ingredientes necessários para atender as entregas.