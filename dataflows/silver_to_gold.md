# Silver para Gold - Dataflow Gen2

## Visão Geral

Este Dataflow Gen2 é responsável por transformar os dados da camada Silver em um modelo analítico na camada Gold.

As transformações foram desenvolvidas utilizando o Microsoft Fabric Dataflow Gen2 (Power Query), preparando os dados para consumo pelo Modelo Semântico e pelos relatórios do Power BI.

---

## Origem dos Dados

- Silver Lakehouse

---

## Destino dos Dados

- Gold Lakehouse

---

## Principais Transformações

- Remoção de colunas desnecessárias
- Alteração dos tipos de dados
- Renomeação de colunas
- Mesclagem de tabelas
- Criação de tabelas dimensão
- Criação da tabela fato

---

## Tabelas Geradas

- dim_turbine
- dim_location
- fact_wind_power

---

## Tecnologias Utilizadas

- Microsoft Fabric
- Dataflow Gen2
- Power Query (M)