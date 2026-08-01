# Documentação

Esta pasta reúne toda a documentação técnica do projeto **Fabric Wind Power Lakehouse**, descrevendo a arquitetura da solução, o fluxo de dados, as tecnologias utilizadas e a organização do ambiente desenvolvido no Microsoft Fabric.

---

# Arquitetura da Solução

O projeto foi desenvolvido utilizando a arquitetura Medallion no Microsoft Fabric, separando os dados em camadas para facilitar a manutenção, escalabilidade e reutilização.

Fluxo da solução:

Fonte de Dados

↓

Bronze Lakehouse

↓

Notebook (Bronze → Silver)

↓

Silver Lakehouse

↓

Dataflow Gen2 (Silver → Gold)

↓

Gold Lakehouse

↓

Modelo Semântico

↓

Power BI

---

# Pipeline de Dados

## Bronze

Camada responsável pelo armazenamento dos dados brutos, preservando as informações exatamente como foram recebidas da fonte.

## Silver

Nesta etapa os dados passam por tratamento e padronização.

Principais atividades:

- Limpeza de registros
- Ajuste dos tipos de dados
- Padronização de colunas
- Remoção de dados desnecessários

As transformações foram realizadas através de Notebooks utilizando Spark SQL.

## Gold

Camada analítica destinada ao consumo pelo Power BI.

Nesta etapa foram desenvolvidas:

- Tabelas dimensão
- Tabela fato
- Modelagem dimensional
- Regras de negócio

As transformações foram realizadas utilizando Dataflow Gen2.

---

# Arquitetura Medallion

O projeto segue o padrão Medallion Architecture.

## Bronze

- Dados brutos
- Sem transformações

## Silver

- Dados tratados
- Dados padronizados
- Preparação para modelagem

## Gold

- Dados analíticos
- Modelo dimensional
- Otimizado para consultas

Principais benefícios:

- Organização dos dados
- Melhor desempenho
- Facilidade de manutenção
- Reutilização das informações
- Escalabilidade

---

# Modelo Analítico

A camada Gold foi organizada utilizando um modelo dimensional composto por tabelas fato e dimensão.

Principais tabelas:

- fact_wind_power
- dim_turbine
- dim_location

Esse modelo foi utilizado na construção do Modelo Semântico consumido pelo Power BI.

---

# Tecnologias Utilizadas

- Microsoft Fabric
- OneLake
- Lakehouse
- Notebook
- Spark SQL
- SQL Endpoint
- Dataflow Gen2
- Power BI Desktop
- Modelo Semântico
- DAX
- Power Query
- Git
- GitHub

---

# Organização do Projeto

```text
fabric-wind-power-lakehouse
│
├── Architecture
├── Dataflows
├── Docs
├── Notebooks
├── Power BI
├── Screenshots
├── SQL
├── README.md
└── LICENSE
```

---

# Objetivo

Demonstrar a implementação de uma solução completa de Engenharia de Dados utilizando Microsoft Fabric, contemplando ingestão, transformação, modelagem e visualização dos dados através de uma arquitetura moderna baseada em Lakehouse e Medallion Architecture.