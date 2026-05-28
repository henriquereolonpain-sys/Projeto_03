# Projeto_03 — Lakehouse com Arquitetura Medallion

Pipeline de dados construído no Databricks Community Edition como parte do desafio da Comunidados,
simulando o ambiente de engenharia de dados de um e-commerce de produtos eletrônicos e móveis (TechVenda).

## Arquitetura

A solução segue o padrão Medallion com três camadas:

- **Bronze** — Ingestão bruta dos arquivos CSV para Delta Tables, sem transformações
- **Silver** — Limpeza, tipagem, joins entre tabelas e cálculo de valor por item com desconto
- **Gold** — Visões analíticas agregadas para responder perguntas de negócio

## Visões Analíticas (Gold)

- Faturamento mensal em 2024
- Ranking de vendedores por receita gerada
- Top 3 produtos por categoria (via Window Function)

## Tecnologias

- Databricks Community Edition
- PySpark
- Delta Lake
- Unity Catalog (Volumes)

## Orquestração

Os notebooks são executados em sequência via Databricks Workflow:
`Bronze → Silver → Gold`

## Estrutura

```
├── Bronze.ipynb
├── Silver.ipynb
└── Gold.ipynb
```
