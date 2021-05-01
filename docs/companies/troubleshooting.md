---
layout: default
title: Solução de Problemas
parent: Consulta CNPJ
nav_order: 30
---

# Solução de Problemas
{: .no_toc }

## Índice
{: .no_toc .text-delta }

- TOC
{:toc}

---

## Bad Request (400)

CNPJ inválido, certifique-se que:
- No parâmetro `cnpj` foi enviado apenas dígitos
- No parâmetro `cnpj` foi enviado 14 dígitos
- Os dígitos obedecem o [algoritmo de CNPJ](https://www.geradorcnpj.com/algoritmo_do_cnpj.htm)

```json
{
  "error": 400,
  "message": "parameter validation failed",
  "details": {
    "constraints": [
      "tax_id must be shorter than or equal to 14 characters",
      "tax_id must be a number string"
    ]
  }
}
```

---

## Unauthorized (401)

Não foi possível autenticar sua requisição, certifique-se que:
- Sua Chave de API está na propriedade `Authorization` dos `Headers`
- Sua chave está no formato correto incluindo hífens `-`

```json
{
  "error": 401,
  "message": "invalid authorization",
  "details": { }
}
```

---

## Not Found (404)

O CNPJ consultado não está registrado na Receita Federal

```json
{
  "error": 404,
  "message": "tax id is not registered at revenue service",
  "details": { }
}
```

---

## Too Many Requests (429)

Este erro será exibido em duas ocasiões:
- Seus créditos acabaram
- Você excedeu o limite de 25 requisições concorrentes

```json
{
  "error": 429,
  "message": "not enough credits",
  "details": {
    "credits_required": 16,
    "credits_remaining": 0
  }
}
```

---

## Internal Server Error (500)

Um erro imprevisto ocorreu em nosso serviço.

Temos um sistema de monitoramento que irá nos alertar sobre o ocorrido e atuaremos sobre o problema imediatamente.

```json
{
  "error": 500,
  "message": "unexpected server error",
  "details": { }
}
```

---

## Service Unavailable (503)

A fonte de dados da consulta em Tempo Real que tentou executar está indisponível.

Você pode previnir que este erro ocorra customizando a consulta com o `enable_cache_fallback`.

```json
{
  "error": 503,
  "message": "revenue service is unavailable",
  "details": { }
}
```
