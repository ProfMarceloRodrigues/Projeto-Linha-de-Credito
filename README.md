# Projeto: Análise de Dados - Linha_Creditos

> Arquivo principal: `Projeto_Analise_Dados_Linha _Creditos.ipynb`

---

## Sumário

1. Visão geral
2. Objetivos
3. Estrutura do repositório
4. Requisitos (software e bibliotecas)
5. Instalação e setup
6. Como executar
7. Descrição dos dados
8. Fluxo de processamento e análises realizadas
9. Principais funções / células importantes
10. Output esperado
11. Boas práticas e melhorias sugeridas
12. Checklist para entrega
13. Contato

---

## 1. Visão geral

Este projeto tem por objetivo analisar a **linha de créditos** (dados financeiros/operacionais) presente no notebook `Projeto_Analise_Dados_Linha _Creditos.ipynb`. O foco é limpar, transformar, analisar e gerar relatórios/insights que permitam entender comportamento, performance e problemas na base de crédito.

## 2. Objetivos

* Extrair, limpar e consolidar os dados da(s) fonte(s).
* Gerar indicadores-chave (ex.: volume de crédito, taxas de inadimplência, tempo médio de aprovação, churn por segmento).
* Visualizar distribuições e séries temporais relevantes.
* Preparar dataset para modelos preditivos (se aplicável).
* Produzir relatório resumido com gráficos e tabelas.

## 3. Estrutura do repositório

```
/ (root)
├─ data/                  # arquivos de dados brutos e processados (gitignore grandes)
├─ notebooks/             # notebooks (inclui o Projeto_Analise_Dados_Linha _Creditos.ipynb)
├─ src/                   # scripts Python reutilizáveis (etl.py, utils.py, plots.py)
├─ outputs/               # gráficos, relatórios, tabelas geradas
├─ requirements.txt       # dependências Python
├─ README.md              # explicação resumida do projeto
└─ LICENSE
```

> Observação: ajuste os nomes de pastas conforme seu repositório real.

## 4. Requisitos (software e bibliotecas)

* Python 3.8+ recomendado
* Bibliotecas principais (exemplo):

  * pandas
  * numpy
  * matplotlib
  * seaborn
  * jupyterlab / notebook
  * openpyxl (se ler/extrair Excel)
  * scikit-learn (se houver modelagem)

Colete as dependências reais do notebook e gere um `requirements.txt` com:

```bash
pip freeze | grep -E "pandas|numpy|matplotlib|seaborn|openpyxl|scikit-learn|jupyter" > requirements.txt
```

## 5. Instalação e setup

1. Criar e ativar virtualenv (exemplo com venv):

```bash
python -m venv .venv
source .venv/bin/activate    # Linux/Mac
.\.venv\Scripts\activate   # Windows
pip install -r requirements.txt
```

2. Colocar arquivos de dados na pasta `data/`.
3. Abrir o notebook em JupyterLab ou executar os scripts em `src/`.

## 6. Como executar

### Executar notebook (interativo)

```bash
jupyter lab
# ou
jupyter notebook
# abrir Projeto_Analise_Dados_Linha _Creditos.ipynb
```

### Executar como script (não interativo)

Se houver conversões para scripts em `src/`:

```bash
python src/etl.py --input data/raw.csv --output data/processed.csv
python src/analyze.py --input data/processed.csv --out outputs/report.pdf
```

## 7. Descrição dos dados

> IMPORTANTE: atualizar este bloco com os nomes/colunas reais do seu dataset.

Exemplo de schema esperado:

* id_transacao: identificador único
* cliente_id: identificador do cliente
* produto: tipo de crédito
* valor: valor solicitado/concedido
* data_solicitacao: datetime
* data_aprovacao: datetime
* status: aprovado/rejeitado/cancelado
* taxa: percentual
* inadimplencia: 0/1

## 8. Fluxo de processamento e análises realizadas

1. Ingestão dos dados brutos (CSV/Excel/DB).
2. Limpeza: tratamento de nulos, formatação de datas, normalização de colunas.
3. Enriquecimento: cálculo de idade do cliente, categoria de valor, tempo entre solicitação e aprovação.
4. Agregações: por mês, por produto, por região.
5. Visualizações: séries temporais, histogramas, boxplots e heatmaps de correlação.
6. Exportação de outputs: tabelas agregadas e gráficos em `outputs/`.

## 9. Principais funções / células importantes

* **Carregamento**: função `load_data(path)` — lê e padroniza tipos.
* **Limpeza**: `clean_data(df)` — trata nulos e outliers.
* **Feature engineering**: `create_features(df)` — cria colunas úteis (tempo_aprovacao, faixa_valor).
* **Análises**: funções que retornam DataFrames com indicadores (ex.: `monthly_kpis(df)`).
* **Plots**: `plot_kpi_time_series(df, kpi, filename)` — gera gráfico e salva em `outputs/`.

> Se preferir, eu posso extrair automaticamente essas funções do notebook e criar arquivos em `src/`.

## 10. Output esperado

* `outputs/report_summary.csv` — resumo dos KPIs mensais
* `outputs/fig_kpi_tempo.png` — série temporal do KPI principal
* `outputs/dashboard.ipynb` — versão resumida para apresentação

## 11. Boas práticas e melhorias sugeridas

* Colocar dados brutos em `data/raw/` e evitar versionar arquivos grandes.
* Adicionar testes unitários para funções críticas (ex.: pipeline de ETL).
* Criar um `Makefile` ou `tasks` (invoke) para automatizar execução.
* Adicionar CI (GitHub Actions) para rodar lint e testes ao comitar.
* Gerar `requirements.txt` e `environment.yml` (conda) para reprodutibilidade.

## 12. Checklist para entrega

* [ ] Notebook comentado e reprodutível
* [ ] `requirements.txt` atualizado
* [ ] Scripts em `src/` para ETL e análise
* [ ] Outputs salvos em `outputs/`
* [ ] README.md com instruções básicas

## 13. Contato

Projeto documentado por: **Marcelo Rodrigues** / Lodes Transportes & Starts Treinamentos & Consultoria

---

### Próximos passos sugeridos

* Gerar um `README.md` a partir desta documentação.
* Extrair funções do notebook para `src/` (posso fazer automaticamente).
* Produzir um relatório em PDF ou slides com os principais insights.

*FIM da documentação gerada.*
