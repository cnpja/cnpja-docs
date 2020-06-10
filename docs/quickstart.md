---
layout: default
title: Guia Rápido
nav_order: 1
permalink: /
---

# Guia Rápido
{: .no_toc }

## Índice
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Obtenha sua Chave de API

Acesse a página [Minha Conta](https://www.cnpja.com.br/me) e copie sua Chave de API.
Caso ainda não tenha confirmado seu e-mail, será necessário que o faça antes de poder visualizá-la.

Na biblioteca ou IDE de requisições HTTP de sua aplicação, configure a sua Chave de API na propriedade `Authorization` dos `Headers`.

_Caso não tenha certeza de como fazer isto, refira-se aos exemplos a seguir._

---

## Consulte a Receita Federal em Tempo Real `1 ₪`{: .label .label-yellow }

As consultas feitas em nossa API custam créditos, que indicamos pelo símbolo ₪. Este exemplo irá custar 1 ₪.

Envie uma requisição `GET` para:

```
https://api.cnpja.com.br/companies/07506399000126
```

Você pode substituir `07506399000126` por outro CNPJ que desejar.

O payload de retorno irá obedecer o tipo de objeto [Empresa](./companies/types).

---

### Exemplos Consulta Padrão

<iframe src="https://api.apiembed.com/?source=https://raw.githubusercontent.com/cnpja/api-cnpja/master/tools/har/example_company.json&amp;targets=shell:curl,php:curl,php:http1,php:http2,javascript:jquery,javascript:fetch,javascript:xhr,node:request,node:unirest,node:native,python:requests,python:python3,java:okhttp,java:unirest" frameborder="0" scrolling="no" width="100%" height="400px" seamless=""></iframe>

---

## Visualize o SINTEGRA e Simples Nacional em Cache `0 ₪`{: .label .label-yellow }

A resposta que você recebeu no passo anterior, irá incluir sem cobrança adicional de créditos, nossa última informação do SINTEGRA e Simples Nacional.

Localize dentro do objeto JSON as propriedas `sintegra` e `simples_nacional`.

Observe que cada uma delas possui seu próprio `last_update`, ele significa a data e hora em que o dado foi atualizado pela última vez.

Nos casos que não tivermos a informação, este valor estará `null`. Para obtê-lo com assertividade, você precisa se sujeitar a uma cobrança adicional de créditos explicada a seguir.

--- 

## Adicione o SINTEGRA em Tempo Real `+1 ₪`{: .label .label-yellow }

Em sua requisição `GET` adicione o parâmetro `sintegra_max_age=1` 

```
https://api.cnpja.com.br/companies/07506399000126?sintegra_max_age=1
```

Você pode substituir o número `1` pela quantidade de dias em que aceita o dado em Cache.

Por exemplo, ao utilizar `30`, se a nossa última atualização foi em menos de 30 dias da data de hoje, iremos lhe retornar o dado sem cobrar os créditos extras.

---

## Adicione o Simples Nacional em Tempo Real `+9 ₪`{: .label .label-yellow }

Em sua requisição `GET` adicione o parâmetro `simples_max_age=1` 

```
https://api.cnpja.com.br/companies/07506399000126?simples_max_age=1
```

Você pode substituir o número `1` pela quantidade de dias em que aceita o dado em Cache.

Por exemplo, ao utilizar `90`, se a nossa última atualização foi nos últimos 3 meses, iremos lhe retornar o dado sem cobrar os créditos extras.

---

### Exemplos SINTEGRA e Simples Tempo Real

<iframe src="https://api.apiembed.com/?source=https://raw.githubusercontent.com/cnpja/api-cnpja/master/tools/har/examplo_sintegra_simples.json&amp;targets=shell:curl,php:curl,php:http1,php:http2,javascript:jquery,javascript:fetch,javascript:xhr,node:request,node:unirest,node:native,python:requests,python:python3,java:okhttp,java:unirest" frameborder="0" scrolling="no" width="100%" height="400px" seamless=""></iframe>

--- 

## Consulte a Receita Federal em Cache `0,1 ₪`{: .label .label-yellow }

Para economizar créditos, você pode optar por receber o dado da Receita de nosso Cache.

Porém, caso não tenhamos o dado para o CNPJ específico, a consulta segue em Tempo Real.

Em sua requisição `GET` adicione o parâmetro `company_max_age=90` 

```
https://api.cnpja.com.br/companies/07506399000126?company_max_age=90
```

Você pode substituir o número `90` pela quantidade de dias em que aceita o dado em Cache.

---

## Habilite a Proteção Contra Serviço Indisponível

Avançado
{: .label }

Por padrão, se algum problema ocorrer durante as consultas em Tempo Real, nossa API irá retornar os status de erro `500` ou `503`.

Nestes casos, nenhum dado da empresa será fornecido, e sua aplicação deve gerenciar o tratamento da falha.
​
Para contornar este efeito, adicione o parâmetro `enable_cache_fallback=true` 

```
https://api.cnpja.com.br/companies/07506399000126?enable_cache_fallback=true
```

Com esta função habilitada, em caso de indisponibilidade, nosso serviço irá concluir a consulta com dados do Cache e retornar status `202`.

O payload será idem ao padrão de sucesso `200`, com adição de uma propriedade `errors` contendo uma matriz dos problemas.

Você não será cobrado os créditos referente ao Tempo Real se a requisção cair neste cenário.
