---
layout: default
title: Autenticação
parent: Consulta CNPJ
nav_order: 1
---

# Autenticação
{: .no_toc }

## Índice
{: .no_toc .text-delta }

- TOC
{:toc}

---

## Método

Todas as rotas de nossa API, com exceção de links para dowload de arquivos, requerem autenticação através de uma Chave de API.

Esta Chave está vinculada ao e-mail utilizado para criação da conta, e pode ser obtida na página [Minha Conta](https://www.cnpja.com.br/me) de nosso website.

O padrão de caracteres obedece o seguinte formato:

```
xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx-xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
```

Sua chave de API deve ser adicionada na propriedade `Authorization` dos `Headers`.

A maneira de realizar isto é dependente da linguagem e biblioteca que estiver utilizando. 

Refira-se aos exemplos em nosso [Guia Rápido](./quickstart).

Não preceda a string por nenhum termo como `ApiKey`, `Token` ou `Bearer`.

---

## Utilização

Com a Chave de API devidamente configurado nos Headers, envie uma requisição `GET` para:

```
https://api.cnpja.com.br/companies/{cnpj}
```

Substitua o parâmetro `{cnpj}` pelos 14 dígitos do CNPJ que deseja consultar.

Não utilize pontos `.`, hífens `-`, ou barras `/`.

Sua Chave de API deve estar presente na propriedade `Authorization` dos `Headers`.


**Exemplos**:

```
CORRETO -> https://api.cnpja.com.br/companies/00000000000191
CORRETO -> https://api.cnpja.com.br/companies/33000167000101

INCORRETO -> https://api.cnpja.com.br/companies/33.000.167/0001-01
INCORRETO -> https://api.cnpja.com.br/companies/33.000.167\/0001-01
INCORRETO -> https://api.cnpja.com.br/companies/33.000.167%2F0001-01
```

