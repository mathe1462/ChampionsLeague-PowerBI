# Medidas DAX sugeridas — C1

> Ajuste os nomes de tabelas/colunas conforme o dataset que você baixar do Kaggle.
> Estes exemplos assumem uma tabela `Jogos` (ou `Matches`) com colunas como `Clube`, `Temporada`, `GolsMarcados`, `GolsSofridos`, `Resultado`, `Fase`.

## Jogos Disputados
```dax
Jogos Disputados = COUNTROWS(Jogos)
```

## Vitórias
```dax
Vitorias = CALCULATE(COUNTROWS(Jogos), Jogos[Resultado] = "Vitória")
```

## Empates
```dax
Empates = CALCULATE(COUNTROWS(Jogos), Jogos[Resultado] = "Empate")
```

## Derrotas
```dax
Derrotas = CALCULATE(COUNTROWS(Jogos), Jogos[Resultado] = "Derrota")
```

## Percentual de Vitórias
```dax
% Vitorias = DIVIDE([Vitorias], [Jogos Disputados], 0)
```

## Gols Marcados
```dax
Gols Marcados = SUM(Jogos[GolsMarcados])
```

## Gols Sofridos
```dax
Gols Sofridos = SUM(Jogos[GolsSofridos])
```

## Saldo de Gols
```dax
Saldo de Gols = [Gols Marcados] - [Gols Sofridos]
```

## Títulos Conquistados
```dax
Titulos = CALCULATE(
    DISTINCTCOUNT(Finais[Temporada]),
    Finais[Vencedor] = SELECTEDVALUE(Clubes[Clube])
)
```

## Participações em Finais
```dax
Participacoes em Finais = CALCULATE(
    COUNTROWS(Finais),
    Finais[Finalista1] = SELECTEDVALUE(Clubes[Clube])
        || Finais[Finalista2] = SELECTEDVALUE(Clubes[Clube])
)
```

## Percentual de Aproveitamento
```dax
% Aproveitamento = DIVIDE(([Vitorias] * 3 + [Empates]), [Jogos Disputados] * 3, 0)
```

---

**Dica:** depois de importar o CSV do Kaggle, confira os nomes reais das colunas no Power Query antes de colar essas fórmulas — provavelmente vai precisar ajustar nomes de tabela/coluna (ex: `results.csv`, `matches.csv`).
