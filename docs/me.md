---
layout: default
title: Dados da Conta
nav_order: 50
---

# Dados da Conta
{: .no_toc }

`/me`{: .btn .btn-green }

## Índice
{: .no_toc .text-delta }

- TOC
{:toc}

---

## Objetivo

Provê informações sobre sua conta, incluindo cadastro, plano e créditos restantes.

---

## Requisição

Envie uma requisição `GET` para:

```
https://api.cnpja.com.br/me
```

Sua Chave de API deve estar presente na propriedade `Authorization` dos `Headers`.

---

## Retornos Esperados

### OK (200)

```json
{
  "email": "contato@cnpja.com",
  "name": "Contato CNPJá",
  "given_name": "Contato",
  "family_name": "CNPJá",
  "nickname": "CNPJá",
  "status": "ACTIVE",
  "remaining_credits": 9321.8,
  "profile_picture": null,
  "subscriptions": [
    {
      "status": "ACTIVE",
      "payment_method": "CREDIT_CARD",
      "activated": "2020-03-24T10:42:08.000Z",
      "plan": {
        "name": "PRO",
        "price": "99.00",
        "credits": 10000,
        "reffils": "DAILY",
        "reccurence": "MONTHLY"
      }
    }
  ]
}
```

---

### Unauthorized (401)

Chave de API incorreta.
