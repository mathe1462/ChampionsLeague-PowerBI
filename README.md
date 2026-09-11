# ChampionsLeague PowerBI

Projeto acadêmico de Business Intelligence desenvolvido em Microsoft Power BI, com foco na análise de dados históricos da UEFA Champions League.

O projeto está sendo desenvolvido de forma incremental, com novas análises sendo adicionadas a cada entrega acadêmica.

## Objetivo do Projeto

Transformar dados históricos da UEFA Champions League em informações visuais e indicadores que permitam analisar o desempenho de clubes, temporadas, finais e trajetórias ao longo da história da competição.

## Tecnologias Utilizadas

- Microsoft Power BI
- Power Query
- DAX
- CSV
- GitHub

## C1 — Desempenho dos Clubes

A primeira entrega do projeto tem como foco a análise de desempenho dos clubes na UEFA Champions League.

### Principais indicadores

- Temporadas disputadas
- Jogos disputados
- Vitórias, empates e derrotas
- Percentual de vitórias
- Gols marcados
- Gols sofridos
- Saldo de gols
- Títulos conquistados
- Percentual de aproveitamento
- Fase mais avançada alcançada
- Participações em finais

### Filtros disponíveis

- Temporada
- Clube
- Fase da competição

Os indicadores e gráficos são atualizados dinamicamente conforme os filtros selecionados.

### Vídeo de apresentação da C1

_(adicionar link do vídeo aqui após a gravação)_

## Estrutura do Projeto

```
ChampionsLeague_PowerBI
│
├── Dados
│   └── (arquivos CSV do dataset histórico 1955-2023)
│
├── PowerBI
│   └── ChampionsLeague_PowerBI_C1.pbix
│
└── README.md
```

## Tratamento dos Dados

Os arquivos utilizados como fonte são carregados no Power BI por meio do Power Query.

Recomenda-se criar um parâmetro para centralizar o diretório dos arquivos utilizados pelo projeto, facilitando a manutenção e atualização das fontes de dados.

O modelo utiliza medidas desenvolvidas em DAX para realizar os cálculos e alimentar os indicadores e visualizações do dashboard.

## Fonte dos Dados

Os dados utilizados neste projeto são provenientes do dataset **UEFA Champions League Historical Dataset (1955-2023)**, disponível no Kaggle.

Fonte de referência: [Kaggle - UEFA Champions League Historical Dataset 1955-2023](https://www.kaggle.com/datasets/fardifaalam170041060/champions-league-dataset-1955-2023)

## 📋 Acompanhamento do Projeto

O desenvolvimento e a evolução das entregas podem ser acompanhados pelo Board do projeto no GitHub.

[Champions League BI — Roteiro](https://github.com/users/mathe1462/projects/2)

## Evolução do Projeto

- [x] C1 — Análise de Desempenho dos Clubes
- [ ] C2 — Próxima análise
- [ ] C3 — Próxima análise
- [ ] Prova — Análise final

## 👨‍💻 Autor

Matheus

Projeto desenvolvido para fins acadêmicos.
