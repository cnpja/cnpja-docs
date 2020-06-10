---
layout: default
title: Histórico de Requisições
nav_order: 60
---

# Histórico de Requisições
{: .no_toc }

`/me/requests`{: .btn .btn-green }

## Índice
{: .no_toc .text-delta }

- TOC
{:toc}

---

## Objetivo

Retorna seu histórico de requisições dentro do intervalo de data especificado.

---

## Requisição

Envie uma requisição `GET` para:

```
https://api.cnpja.com.br/me/requests?start_date={data_inicio}&end_date={data_terminio}
```

Substitua os parâmetros `data_inicio` e `data_termino` pelo intervalo desejado.

O fornecimento das datas e mandatório e deve obedecer o formato `YYYY-MM-DD`.

Sua Chave de API deve estar presente na propriedade `Authorization` dos `Headers`.

---

## Retornos Esperados

### OK (200)

```json
{
  "count": 2,
  "results": [
    {
      "id": 2753,
      "path": "/companies/35565391000176?company_max_age=0",
      "requested": "2020-03-09T09:26:39.000Z",
      "status": 200,
      "time": 8485,
      "cost": 1
    },
    {
      "id": 2755,
      "path": "/companies/07506399000126?company_max_age=0&sintegra_max_age=0",
      "requested": "2020-03-10T01:29:32.000Z",
      "status": 200,
      "time": 11218,
      "cost": 16
    }
  ]
}
```

---

### Unauthorized (401)

Chave de API incorreta.
