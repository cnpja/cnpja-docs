---
layout: default
title: Tempo Real e Cache
parent: Consulta CNPJ
nav_order: 10
---

# Tempo Real e Cache
{: .no_toc }

## Índice
{: .no_toc .text-delta }

- TOC
{:toc}

---

## Conceito

Os nossos dados são sensíveis a data e hora irão retornar com uma estampa de tempo UTC de sua aquisição.

Utilizamos os termos a seguir para se referir a sua idade:
- **Tempo Real**: Adquiridos na fonte no mesmo momento em que recebemos a requisição
- **Cache**: Retornados de nosso banco de dados

Por padrão, requisições em Tempo Real, consomem uma quantidade maior de seus créditos em relação as feitas ao Cache.

É possível controlar de maneira inteligente a idade dos dados utilizando parâmetros opcionais a seguir na requisição.

---

## Customização

Através dos parâmetros a seguir você pode configurar a consulta da maneira que melhor o atenda.

Se todos forem omitidos, nossa consulta padrão é:
- Dados da Receita Federal Tempo Real
- Dados do Simples Nacional do Cache
- Dados do SINTEGRA do Cache
- Retorno 5xx em Caso de falhas nas consultas em Tempo Real

Parâmetro | Padrão | Descrição
:-- | :-- | :--
company_max_age | 1 | Idade máxima em dias para retornar dados da empresa do Cache
simples_max_age | null | Idade máxima em dias para retornar dados do Simples do Cache
sintegra_max_age | null | Idade máxima em dias para retornar dados do SINTEGRA
enable_cache_fallback | false | Habilita retorno em Cache no caso de uma requisição em Tempo Real falhar

**Exemplos**:
```
# Consultar CNPJ em Tempo Real e Simples Nacional do Cache:
https://api.cnpja.com.br/companies/00000000000191

# Consultar CNPJ em Tempo Real e Simples Nacional em Tempo Real:
https://api.cnpja.com.br/companies/00000000000191?simples_max_age=1

# Aceitar Cache do CNPJ de até um mês atrás e do Simples de até uma semana:
https://api.cnpja.com.br/companies/00000000000191?company_max_age=30&simples_max_age=7

# Consultar CNPJ em Tempo Real, Simples Nacional em Tempo Real e SINTEGRA em Tempo Real:
https://api.cnpja.com.br/companies/00000000000191?simples_max_age=1&sintegra_max_age=1

# Consultar Simples Nacional em Tempo Real e retornar informação do Cache em caso de falha:
https://api.cnpja.com.br/companies/00000000000191?simples_max_age=1&enable_cache_fallback=true
```
