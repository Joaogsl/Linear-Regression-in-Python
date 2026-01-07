# Predição Salarial de Profissionais de Dados 📊

Este projeto aplica modelos de **Regressão Linear Múltipla** para investigar e prever salários anuais de profissionais da área de dados, identificando os principais fatores que influenciam a remuneração global.
Desenvolvido como parte da disciplina de **Métodos Quantitativos para Análise Multivariada (MQAM)** na EACH-USP.

## Objetivo
O objetivo central é modelar a associação entre variáveis demográficas, técnicas e profissionais (como experiência, gestão de equipe e país) e o salário anual em dólares (`SalaryUSD`).
O estudo busca não apenas a predição, mas a inferência estatística para entender o "peso" de cada fator.

## Metodologia e Processamento
O projeto seguiu um rigoroso pipeline estatístico:

- **Tratamento de Assimetria:** Aplicação de transformação logarítmica (`log1p`) na variável alvo e em preditores numéricos para normalizar distribuições assimétricas.
- **Engenharia de Features:** Discretização da variável de "Anos de Experiência" em faixas categóricas para capturar relações não-lineares (efeito platô).
- **Tratamento de Outliers:** Estratégia de *clipping* removendo o 1% dos valores extremos inferiores e superiores para evitar distorções no ajuste OLS.
- **Seleção de Variáveis:** Utilização do algoritmo *Stepwise Backward Elimination* para remover variáveis não significativas (p-valor > 0.05), resultando em um modelo parcimonioso.

## Resultados Principais
O modelo final alcançou um **R² Ajustado de 61.8%**, demonstrando alto poder explicativo.

### Insights de Negócio:
- **Experiência:** O impacto salarial cresce significativamente até a faixa de 16-20 anos, onde atinge um platô.
- **Tipo de Contrato:** Profissionais autônomos (*Freelancers*) apresentaram uma forte associação positiva com salários mais altos.
- **Geografia:** Países como Suíça e EUA apresentaram os maiores coeficientes positivos, enquanto Brasil e Índia mostraram associações negativas fortes em relação à remuneração em dólar.

### Validação Estatística (LINE):
O modelo atendeu aos pressupostos da regressão linear:
- ✅ **Linearidade:** Tratada via *binning* de variáveis.
- ✅ **Independência:** Teste Durbin-Watson de 1.97 (sem autocorrelação).
- ✅ **Normalidade dos Resíduos:** Confirmada visualmente por Histograma e QQ-Plot.
- ✅ **Homocedasticidade:** Confirmada pela dispersão aleatória dos resíduos.

## 👥 Autores
* **João Gabriel de Senna Lamolha**
* Gustavo Pompermayer Fulanetti Silva
