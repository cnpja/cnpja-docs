---
layout: default
title: Perguntas Frequentes
nav_order: 70
---

# Perguntas Frequentes
{: .no_toc }

## Índice
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Sobre a API

### Por que às vezes os dados do SINTEGRA / Simples Nacional não estão vindo?

Você não está utilizando as propriedades `sintegra_max_age` ou `simples_max_age`.

Para receber estes dados com 100% de disponibilidade você precisa se sujeitar a uma cobrança de créditos mais elevada, que chamamos de consulta em Tempo Real.

Caso contrário, irá recebê-los do Cache que não garante retorno todas as vezes.

---

### Os créditos que eu não utilizar acumulam?

Não, os créditos são reiniciados para o valor contratado todos os dias a meia-noite (UTC).

---

### Existe limite de requisições?

Sim, sempre que enviar uma requisição iremos contar quantas outras não finalizadas você possui.

Cada Chave de API pode ter até 100 requisições concorrentes não finalizadas.

---

## Sobre os Planos

### Posso pagar em boleto?

Sim, aceitamos pagamento em boleto para transações acima de R$ 95,00.

Este método de pagamento será automaticamente habilitado ao selecionar um plano que atenda o valor mínimo.

---

### Vocês emitem nota fiscal?

Sim, as notas fiscais serão automaticamente emitidas e enviadas para o e-mail do responsável financeiro.

Ou seja, o e-mail que configurou para emissão de boleto, ou o e-mail da conta pagante PayPal.

---

### Como cancelo a assinatura?

Acesse sua página de pagamentos recorrentes no portal do Paypal através [deste link](https://www.paypal.com/myaccount/autopay/) e cancele a assinatura.

Em caso de pagamentos via boleto bancário por gentileza entre em contato conosco para cancelamento.

---

### Existe multa de cancelamento?

Não. Todavia não reembolsaremos o pagamento já realizado do mês vigente.
