# Power Query — Importação dos Dados (C1)

## 1. Criar o parâmetro de caminho

No Power BI Desktop: **Página Inicial → Transformar Dados → Gerenciar Parâmetros → Novo Parâmetro**

- Nome: `CaminhoBaseChampions`
- Tipo: Texto
- Valor atual: `C:\Users\SeuUsuario\ChampionsLeague_PowerBI\Dados\` (ajuste para o seu caminho local)

## 2. Importar cada CSV usando o parâmetro

No Editor Poder Query, para cada arquivo (ex: `exemplo_resultados.csv`), use o código M abaixo como fonte (Editor Avançado):

```m
let
    Origem = Csv.Document(
        File.Contents(CaminhoBaseChampions & "exemplo_resultados.csv"),
        [Delimiter=",", Columns=7, Encoding=65001, QuoteStyle=QuoteStyle.None]
    ),
    CabecalhoPromovido = Table.PromoteHeaders(Origem, [PromoteAllScalars=true]),
    TiposAlterados = Table.TransformColumnTypes(CabecalhoPromovido,{
        {"Temporada", type text},
        {"Clube", type text},
        {"Fase", type text},
        {"Adversario", type text},
        {"GolsMarcados", Int64.Type},
        {"GolsSofridos", Int64.Type},
        {"Resultado", type text}
    })
in
    TiposAlterados
```

Repita o processo para `exemplo_finais.csv` (ajustando os tipos de coluna: `Temporada` texto, `Vencedor` texto, `Placar` texto, `Finalista2` texto, `Publico` número inteiro, `PaisSede` texto).

## 3. Quando trocar pelo dataset real do Kaggle

1. Baixe o dataset em: https://www.kaggle.com/datasets/fardifaalam170041060/champions-league-dataset-1955-2023
2. Copie os arquivos CSV reais para a pasta `Dados/`, substituindo (ou complementando) os arquivos de exemplo.
3. No Power Query, ajuste os nomes de arquivo e de colunas no código M acima conforme os nomes reais das colunas do dataset baixado (confira os cabeçalhos antes de colar as fórmulas DAX do outro arquivo).
4. Atualize o parâmetro `CaminhoBaseChampions` se o caminho da pasta mudar.

## 4. Criar a tabela de dimensão "Clubes" (opcional, recomendado)

Para facilitar os filtros e a medida de "Títulos", crie uma tabela separada com um clube por linha, usando **Página Inicial → Nova Fonte → Consulta em Branco** e depois:

```m
= Table.Distinct(Table.SelectColumns(exemplo_resultados, {"Clube"}))
```

Relacione essa tabela `Clubes[Clube]` com `exemplo_resultados[Clube]` e `exemplo_finais[Vencedor]` (relação um-para-muitos) no Modelo de Dados.
