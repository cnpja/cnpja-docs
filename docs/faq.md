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

### Qual o tempo de resposta?

Para consultas ao Cache em torno de 0,3s.

Já os serviços em Tempo Real disponibilizamos estatísticas com mínimo, máximo e médio a seguir:

https://status.cnpja.com

---

### Vocês tem consulta de CPF?

No momento não trabalhamos com consulta de CPFs.

---

### Por que os dados do SINTEGRA / Simples Nacional não estão vindo?

Você não está utilizando as propriedades `sintegra_max_age` ou `simples_max_age`.

Para receber estes dados com 100% de disponibilidade você precisa se sujeitar a uma cobrança de créditos mais elevada, que chamamos de consulta em Tempo Real.

Caso contrário, irá recebê-los do Cache que não garante retorno todas as vezes.

---

### Existe limite de requisições?

Sim, sempre que enviar uma requisição iremos contar quantas outras não finalizadas você possui.

Cada Chave de API pode ter até 25 requisições concorrentes não finalizadas.

---

## Sobre os Planos

### Os créditos que eu não utilizar acumulam?

Não, os créditos são reiniciados para o valor contratado todos os dias a meia-noite (UTC).

---

### Posso pagar em boleto?

Sim, aceitamos pagamento em boleto para transações acima de R$ 95,00.

Este método de pagamento será automaticamente habilitado ao selecionar um plano que atenda o valor mínimo.

---

### Vocês emitem nota fiscal?

Sim, as notas fiscais serão automaticamente emitidas e enviadas para o e-mail do responsável financeiro.

Ou seja, o e-mail que configurou para emissão de boleto, ou o e-mail da conta pagante PayPal.

---

### Preciso permanecer por tempo mínimo no plano?

Não há permanência mínima nem fidelidade. Você pode cancelar e recontratar quando quiser.

---

### Como cancelo a assinatura?

**Cartão de Crédito**

Acesse sua página de pagamentos recorrentes no portal do Paypal através [deste link](https://www.paypal.com/myaccount/autopay/) e cancele a assinatura.


**Boleto Bancário**

Basta não efetuar o pagamento e a assinatura automaticamente cancelado.
