# Dashboard de Gestão de Clínicas

Projeto desenvolvido no Power BI para analisar dados fictícios de atendimentos de uma rede de clínicas. O dashboard permite acompanhar indicadores operacionais e financeiros, identificar padrões mensais e comparar unidades e especialidades.

## Visão geral

O painel apresenta:

- Receita total: **R$ 61,41 mil**
- Total de atendimentos: **562**
- Atendimentos realizados: **425**
- Taxa de faltas: **13,7%**
- Evolução mensal dos atendimentos
- Distribuição dos atendimentos por status
- Receita por unidade
- Atendimentos por especialidade
- Filtros interativos por unidade e especialidade

## Ferramentas utilizadas

- **Power BI Desktop** — criação do dashboard e das visualizações
- **Power Query** — importação e preparação dos dados
- **DAX** — criação de medidas e indicadores
- **Microsoft Excel** — fonte de dados do projeto

## Medidas DAX

```DAX
Total Atendimentos = COUNTROWS(TabelaAtendimentos)
```

```DAX
Atendimentos Realizados =
CALCULATE(
    [Total Atendimentos],
    TabelaAtendimentos[Status] = "Realizado"
)
```

```DAX
Total Faltas =
CALCULATE(
    [Total Atendimentos],
    TabelaAtendimentos[Status] = "Falta"
)
```

```DAX
Taxa de Faltas =
DIVIDE(
    [Total Faltas],
    [Total Atendimentos],
    0
)
```

## Principais análises

- Aproximadamente **75,6%** dos atendimentos foram realizados.
- A taxa de faltas foi de **13,7%**.
- Os cancelamentos representaram aproximadamente **10,7%** do total.
- O maior volume mensal ocorreu em **abril**.
- O painel permite comparar o desempenho das três unidades e das diferentes especialidades.

## Arquivos do projeto

- `Dashboard_Clinicas_Flavia.pbix` — arquivo editável do Power BI
- `Dashboard_Clinicas_Flavia.pdf` — visualização do dashboard
- `Base_Dashboard_Clinicas.xlsx` — base de dados fictícia utilizada

## Observação

Os dados utilizados neste projeto são fictícios e foram criados exclusivamente para fins de estudo e portfólio.

## Autora

**Flávia Ribeiro**  
Estudante de pós-graduação em Data Warehouse e Business Intelligence, em transição para a área de Dados e BI.
