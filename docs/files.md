---
layout: default
title: Download de Arquivos
nav_order: 40
---

# Download de Arquivos
{: .no_toc }

`/files/{file_token}`{: .btn .btn-green }

## Índice
{: .no_toc .text-delta }

- TOC
{:toc}

---

## Objetivo

Esta rota visa expôr uma URL pública para download de arquivos.

Tenha cuidado ao compartilhar ou exibir estes endereços.

Embora a chamada não requira Chave de API, ela é vinculada a sua conta e você está sujeito a cobrança de créditos. 


## Requisição

Envie uma requisição `GET` para:

```
https://api.cnpja.com.br/files/{file_token}
```

Substitua o parâmetro `{file_token}` pelo código do arquivo.

Não é necessário autenticação, você pode utilizar diretamente do navegador.


## Retornos Esperados

### OK (200)

Será retornado o buffer do arquivo.

### Not Found (404)

O arquivo não existe ou expirou.
