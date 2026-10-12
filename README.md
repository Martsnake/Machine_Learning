# 90-Day Repeat Purchase Prediction

Estrutura inicial para Machine Learning 2026/2027: prever `repeat_purchase_90d` por ocasião de compra. Os CSV ainda não foram fornecidos; esta estrutura não contém modelos treinados ou resultados experimentais.

## Preparação

Requer Python 3.10 ou superior. Na raiz do repositório, em PowerShell:

```powershell
python -m venv .venv
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
.\.venv\Scripts\python.exe -m jupyter lab
```

Colocar `train.csv`, `test.csv`, `sample_submission.csv` e, opcionalmente, `clientes.csv` em `data/raw/`. Não alterar os originais. Confirmar as condições de partilha dos dados antes de os publicar.

## Organização

```text
data/raw/                         CSV originais
data/processed/                   Dados derivados
notebooks/01_homework.ipynb        Trabalho compacto
notebooks/02_final_project.ipynb   Projeto completo
src/repeat_purchase/              Funções reutilizáveis de leitura e validação
models/                           Pipelines serializados
results/                          Métricas e comparações
submissions/                      CSV para Kaggle
reports/figures/                  Gráficos exportados
reports/homework_report_outline.md Guião do PDF de 2 páginas
docs/project_plan.md              Plano e checklist
```

Abrir primeiro o notebook do homework e desenvolver depois o projeto final. Os notebooks localizam a raiz quando executados da raiz ou de `notebooks/`. Acrescentar módulos de features, preprocessing, avaliação e treino em `src/repeat_purchase/` quando existir lógica reutilizável. As decisões, os resultados e a discussão devem constar nos notebooks entregues. Incluir os módulos importados no ZIP e verificar a execução num ambiente limpo.

## Entregas dos enunciados

| Entrega | Conteúdo | Prazo indicado |
| --- | --- | --- |
| Homework | Notebook(s), previsões e PDF de 2 páginas sobre estrutura e fundamentação | 26/10/2026, 17:59 |
| Projeto final | Notebook(s), pelo menos 5 algoritmos abordados nas aulas, otimização, secção adicional e geração da solução selecionada para Kaggle | 22/12/2026, 17:59 |

Usar `Homework_GroupXX` nos ficheiros do homework, substituindo `XX` pelo número real do grupo.

## Regras de trabalho

- Ajustar imputação, encoding, scaling e seleção apenas nos dados de treino de cada split; usar pipelines.
- Justificar a avaliação considerando que test contém compras posteriores e que o target depende dos 90 dias seguintes.
- Preservar `ID` na submissão; avaliar criticamente `customer_id`, `random_noise` e outros identificadores como preditores.
- Validar unicidade, cobertura e disponibilidade temporal dos atributos antes de integrar clientes.
- Confirmar no Kaggle a métrica oficial e se a submissão exige classes ou probabilidades: os PDFs não especificam estes detalhes.
- Não usar Lazy Predict ou AutoML equivalente, conforme o enunciado.
- Não preencher conclusões ou métricas antes de as obter com os dados reais.

Dados e artefactos gerados ficam excluídos do Git por defeito. Consultar `docs/project_plan.md` para o plano e a verificação final.
