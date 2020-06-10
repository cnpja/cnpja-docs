---
layout: default
title: Tipos de Objeto
parent: Consulta CNPJ
nav_order: 40
---

# Tipos de Objeto
{: .no_toc }

## Índice
{: .no_toc .text-delta }

- TOC
{:toc}

---

## Empresa (Company)

Propriedade | Tipo | Descrição
:-- | :-- | :--
last_update | string | Estampa de tempo da última atualização na Receita Federal
name | string | Razão social
alias | string | Nome fantasia
tax_id | string | Número do CNPJ
type | string | Tipo de empresa (MATRIZ ou FILIAL)
founded | string | Data de fundação em formato 'YYYY-MM-DD'
size | string |  Porte da empresa (MEI, ME, EPP ou DEMAIS)
capital | number | Valor declarado do capital social com duas casas decimais
email | string | E-mail
phone | string | Telefone principal
phone_alt | string | Telefone alternativo
federal_entity | string | Ente Federativo Responsável (EFR)
registration | [Registration](#situação-cadastral-registration) | Infomações da situação cadastral
address | [Address](#endereço-address) | Endereço detalhado
legal_nature | [Legal Nature](#natureza-jurídica-legal-nature) | Natureza jurídica
simples_nacional | [Simples Nacional](#simples-nacional) | Dados do Simples Nacional
primary_activity | [Activity](#atividade-econômica-activity) | Atividade econômica primária
secondary_activities | [Activity](#atividade-econômica-activity)[ ] | Atividades econômicas secundárias
membership | ([Acting](#sócio-atuante-acting-member)\|[Assisted](#sócio-representado-assisted-member))[ ] | Quadro de sócios e administradores (QSA)
partnership | [Partner](#sociedade-partner)[ ] | Empresas cuja consultada é sócia
sintegra | [SINTEGRA](#sintegra) | Dados do SINTEGRA (Inscrição Estadual)
files | [Files](#arquivos-files) | Comprovantes em PDF da Consulta
maps | [Maps](#mapas-maps) | Mapas e foto da rua em PNG

---

## Situação Cadastral (Registration)

Propriedade | Tipo | Descrição
:-- | :-- | :--
status | string | Situação cadastral (ATIVA, SUSPENSA, INAPTA, BAIXA ou NULA)
status_date | string | Data da situação cadastral em formato 'YYYY-MM-DD'
status_reason | string | Motivo da situação cadastral
special_status | string | Situação especial
special\_status\_date | string | Data da situação especial em formato 'YYYY-MM-DD'

---

## Endereço (Address)

Propriedade | Tipo | Descrição
:-- | :-- | :--
street | string | Logradouro
number | string | Número
details | string | Complemento
zip | string | CEP
neighborhood | string | Bairro ou Distrito
city | string | Cidade
city_ibge | string | Código IBGE do município
state | string | Estado
state_ibge | string | Código IBGE da UF

---

## Natureza Jurídica (Legal Nature)

Obedece a [Tabela de Natureza Jurídica](https://receita.economia.gov.br/orientacao/tributaria/cadastros/cadastro-nacional-de-pessoas-juridicas-cnpj/tabelas-utilizadas-pelo-programa-cnpj/tabela-de-natureza-juridica-e-qualificacao-do-quadro-de-socios-e-administradores).

Propriedade | Tipo | Descrição
:-- | :-- | :--
code | string | Código de 4 dígitos da natureza jurídica
description | string | Descrição da natureza jurídica

---

## Atividade Econômica (Activity)

Obedece os [Códigos CNAE do IBGE](https://cnae.ibge.gov.br/?view=estrutura&amp;tipo=cnae&amp;versao_classe=7.0.0&amp;versao_subclasse=9.1.0).

Propriedade | Tipo | Descrição
:-- | :-- | :--
code | string | Código de 7 dígitos da atividade econômica
description | string | Descrição da atividade econômica

---

## Sócio Atuante (Acting Member)

Sócio ou administrador que responde legalmente pela empresa.

Propriedade | Tipo | Descrição
:-- | :-- | :--
name | string | Nome completo ou razão social
tax_id | string | CPF ou CNPJ (sujeito a censura)
role | [Role](#qualificação-role) | Qualificação no quadro de sócios

---

## Sócio Representado (Assisted Member)

Sócio ou administrador que possui participação mas não é o responsável legal.

Propriedade | Tipo | Descrição
:-- | :-- | :--
name | string | Nome completo ou razão social
tax_id | string | CPF ou CNPJ (sujeito a censura)
home_country | string | País de origem (apenas se situado no exterior)
role | [Role](#qualificação-role) | Qualificação no quadro de sócios
legal_rep | [Acting Member](#sócio-atuante-acting-member) | Representante legal

---

## Qualificação (Role)

Propriedade | Tipo | Descrição
:-- | :-- | :--
code | string | Código de 2 dígitos da qualificação
description | string | Descrição da qualificação

---

## Sociedade (Partner)

Outras empresas cuja a consultada faz parte do quadro de sócios.

Propriedade | Tipo | Descrição
:-- | :-- | :--
name | string | Razão social
alias | string | Nome fantasia
tax_id | string | Número do CNPJ
founded | string | Data de fundação em formato 'YYYY-MM-DD'
capital | number | Valor declarado do capital social com duas casas decimais

---

## SINTEGRA

Propriedade | Tipo | Descrição
:-- | :-- | :--
last_update | string | Estampa de tempo da última atualização no SINTEGRA
home_state_registration | string | I.E. habilitada no estado de origem da empresa
registrations | [State Registration](#inscrição-estadual-state-registration)[ ] | Inscrições Estaduais da empresa

---

## Inscrição Estadual (State Registration)

Propriedade | Tipo | Descrição
:-- | :-- | :--
number | string | Número da Inscrição Estadual
state | string | Unidade Federal da inscrição
enabled | boolean | Define se habilitada ou não

---

## Simples Nacional

Propriedade | Tipo | Descrição
:-- | :-- | :--
last_update | string | Estampa de tempo da última atualização no Simples Nacional
simples_optant | boolan | Define a opção pelo Simples Nacional
simples_included | string | Data de inclusão no Simples Nacional
simples_excluded | string | Data de exclusão do Simples Nacional
simei_optant | boolan | Define a opção pelo SIMEI

---

## Arquivos (Files)

_Ao acessar estes links você está sujeito a cobrança de créditos._

Propriedade | Tipo | Descrição
:-- | :-- | :--
registration | string | Comprovante de Inscrição em PDF
membership | string | Quadro de Sócios e Administradores em PDF

---

## Mapas (Maps)

_Ao acessar estes links você está sujeito a cobrança de créditos._

Propriedade | Tipo | Descrição
:-- | :-- | :--
roads | string | Mapa Aéreo 2D em PNG
satellite | string | Mapa Visão Satélite em PNG
street | string | Foto da Rua (Street View) em PNG

---

## Exceção (Error)

Propriedade | Tipo | Descrição
:-- | :-- | :--
error |  number | Código HTTP do erro
message | string | Breve mensagem sobre o ocorrido
details | object | Detalhes extras sobre o erro
