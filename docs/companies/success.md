---
layout: default
title: Retornos Esperados
parent: Consulta CNPJ
nav_order: 20
---

# Retornos Esperados
{: .no_toc }

## Índice
{: .no_toc .text-delta }

- TOC
{:toc}

---

## OK (200)

Requisição realizada com sucesso.

```json
{
    "last_update": "2020-04-08T20:28:47.000Z",
    "name": "PETROLEO BRASILEIRO S A PETROBRAS",
    "alias": "PETROBRAS",
    "tax_id": "33000167000101",
    "type": "MATRIZ",
    "founded": "1966-09-28",
    "size": "DEMAIS",
    "capital": 205431960490.52,
    "email": "atendimentofiscossco@petrobras.com.br",
    "phone": "(21) 3224-8091",
    "phone_alt": "(21) 3224-4477",
    "federal_entity": "UNIÃO",
    "registration": {
        "status": "ATIVA",
        "status_date": "2005-11-03",
        "status_reason": null,
        "special_status": null,
        "special_status_date": null
    },
    "address": {
        "street": "AV REPUBLICA DO CHILE",
        "number": "65",
        "details": null,
        "zip": "20031170",
        "neighborhood": "CENTRO",
        "city": "RIO DE JANEIRO",
        "state": "RJ",
        "city_ibge": "3304557",
        "state_ibge": "33"
    },
    "legal_nature": {
        "code": "2038",
        "description": "Sociedade de Economia Mista"
    },
    "primary_activity": {
        "code": "1921700",
        "description": "Fabricação de produtos do refino de petróleo"
    },
    "secondary_activities": [
        {
            "code": "0600001",
            "description": "Extração de petróleo e gás natural"
        },
        {
            "code": "3520401",
            "description": "Produção de gás; processamento de gás natural"
        },
        {
            "code": "4681801",
            "description": "Comércio atacadista de álcool carburante, biodiesel, gasolina e demais derivados de petróleo, exceto lubrificantes, não realizado por transportador retalhista (T.R.R.)"
        }
    ],
    "membership": [
        {
            "name": "ROBERTO FURIAN ARDENGHY",
            "tax_id": "***581500**",
            "role": {
                "code": "10",
                "description": "Diretor"
            }
        },
        {
            "name": "EBERALDO DE ALMEIDA NETO",
            "tax_id": "***109897**",
            "role": {
                "code": "10",
                "description": "Diretor"
            }
        },
        {
            "name": "EBERALDO DE ALMEIDA NETO",
            "tax_id": "***109897**",
            "role": {
                "code": "10",
                "description": "Diretor"
            }
        },
        {
            "name": "ROBERTO FURIAN ARDENGHY",
            "tax_id": "***581500**",
            "role": {
                "code": "10",
                "description": "Diretor"
            }
        }
    ],
    "partnership": [
        {
            "name": "CONSORCIO PROJETO TERMOCEARA",
            "alias": "CONSORCIO TERMOCEARA",
            "tax_id": "05141091000107",
            "founded": "2002-06-20",
            "capital": null
        },
        {
            "name": "CONSORCIO DA USINA TERMELETRICA DE IBIRITE",
            "alias": null,
            "tax_id": "03577255000100",
            "founded": "1999-05-06",
            "capital": null
        },
        {
            "name": "CONSORCIO PROJETO TERMOCEARA",
            "alias": null,
            "tax_id": "05232025000134",
            "founded": "2002-06-20",
            "capital": null
        },
        {
            "name": "CONSORCIO BC-20",
            "alias": "CONSORCIO BC-20",
            "tax_id": "05259140000100",
            "founded": "2000-04-18",
            "capital": null
        },
        {
            "name": "CONSORCIO BCAM-40",
            "alias": "CONSORCIO BCAM-40",
            "tax_id": "05259144000180",
            "founded": "2000-04-04",
            "capital": null
        }
    ],
    "simples_nacional": {
        "last_update": "2020-04-08T20:26:45.000Z",
        "simples_optant": false,
        "simples_included": null,
        "simples_excluded": null,
        "simei_optant": false
    },
    "sintegra": {
        "last_update": "2020-04-08T20:28:47.000Z",
        "home_state_registration": "81281882",
        "registrations": [
            {
                "number": "81281882",
                "state": "RJ",
                "enabled": true
            },
            {
                "number": "0240026870",
                "state": "RS",
                "enabled": false
            },
            {
                "number": "0748878600131",
                "state": "DF",
                "enabled": false
            },
            {
                "number": "283058749",
                "state": "MS",
                "enabled": false
            }
        ]
    },
    "files": {
        "registration": "https://api.cnpja.com.br/files/******************5IiwieCI6IjMzMDAwMTY3MDAwMTAxIiwidCI6IkNSIn0",
        "membership": "https://api.cnpja.com.br/files/******************5IiwieCI6IjMzMDAwMTY3MDAwMTAxIiwidCI6IkNNIn0"
    },
    "maps": {
        "roads": "https://api.cnpja.com.br/files/******************5IiwieCI6IjMzMDAwMTY3MDAwMTAxIiwidCI6IkdSIn0",
        "satellite": "https://api.cnpja.com.br/files/******************5IiwieCI6IjMzMDAwMTY3MDAwMTAxIiwidCI6IkdTIn0",
        "street": "https://api.cnpja.com.br/files/******************5IiwieCI6IjMzMDAwMTY3MDAwMTAxIiwidCI6IkdUIn0"
    }
}
```

---

## Accepted (202)

Este status está disponível apenas se habilitado o `enable_cache_fallback`.

Ele indica que alguma consulta em Tempo Real falhou e o dado foi retornado do Cache.

```json
{
  // Detalhes sobre o(s) serviço(s) que falharam em Tempo Real
  "errors": [
    {
      "status": 500,
      "service": "sintegra",
      "message": "unexpected server error"
    }
  ],

  // Dados intermediários idem ao Retorno OK (200)
  "last_update": "2020-03-19T20:03:12.000Z",
  "name": "PETROLEO BRASILEIRO S A PETROBRAS",
  "alias": "PETROBRAS",
  "tax_id": "33000167000101",
  ... ,

  // O objeto do serviço que falhou conterá uma estampa de tempo retroativa
  "sintegra": 
    "last_update": "2019-12-31T00:00:00.000Z",
    "home_state_registration": "81281882",
    "registrations": [
      {
        "number": "81281882",
        "state": "RJ",
        "enabled": true
      },
      {
        "number": "748878600131",
        "state": "DF",
        "enabled": false
      },
      {
        "number": "283058749",
        "state": "MS",
        "enabled": false
      },
      {
        "number": "240026870",
        "state": "RS",
        "enabled": false
      }
    ]
  }
}
```
