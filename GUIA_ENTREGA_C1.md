# Guia de Entrega — C1

Este guia junta tudo que foi preparado e o que você ainda precisa fazer manualmente (por exigir Power BI Desktop, GitHub e gravação de tela — coisas que não dá pra automatizar por aqui).

## O que já está pronto (nesta entrega)
- `README.md` — completo, com estrutura, indicadores, tecnologias e checklist de evolução
- `Dados/exemplo_finais.csv` e `Dados/exemplo_resultados.csv` — dados de exemplo no formato certo, pra você testar o modelo antes de baixar o dataset real
- `powerquery_import.md` — script Power Query (M) pronto pra importar os CSVs e criar o parâmetro de caminho
- `medidas_dax_c1.md` — todas as medidas DAX do C1 já escritas
- `GitHub_Board/checklist_c1.md` — checklist pronto pra virar cards no board

## O que você precisa fazer (passo a passo)

### 1. GitHub
1. Crie um repositório novo (ex: `ChampionsLeague-PowerBI`).
2. Suba a estrutura de pastas e os arquivos gerados aqui (`README.md`, `Dados/`, `powerquery_import.md`, `medidas_dax_c1.md`).
3. Crie o board em **Projects** (veja instruções em `GitHub_Board/checklist_c1.md`).

### 2. Dataset real
1. Baixe em: https://www.kaggle.com/datasets/fardifaalam170041060/champions-league-dataset-1955-2023
2. Coloque os CSVs reais na pasta `Dados/` (pode manter os de exemplo também, ou substituir).

### 3. Power BI Desktop
1. Abra o Power BI Desktop e crie um novo arquivo `.pbix`.
2. Siga o `powerquery_import.md` para importar os dados.
3. Cole as medidas de `medidas_dax_c1.md` (ajustando nomes de tabela/coluna conforme o dataset real).
4. Monte os visuais:
   - Cards com os principais indicadores (jogos, vitórias, % vitórias, títulos)
   - Gráfico de barras: vitórias por clube
   - Gráfico de linha: evolução por temporada
   - Segmentações de dados (slicers): temporada, clube, fase
5. Salve como `ChampionsLeague_PowerBI_C1.pbix` na pasta `PowerBI/`.

### 4. Vídeo
1. Grave a tela mostrando o dashboard funcionando, explicando os indicadores e testando os filtros (2-4 minutos costuma ser suficiente).
2. Suba no YouTube (pode ser "não listado").
3. Cole o link no `README.md`, na seção "Vídeo de apresentação da C1".

### 5. Finalizar
1. Atualize o link do board no README.
2. Faça commit e push de tudo.
3. Confira se o repositório tem: vídeo (link no README), board (link no README) e código-fonte (arquivos `.pbix`, CSVs, README) — os três itens exigidos na entrega.
