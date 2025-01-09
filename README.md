# Análise de Séries Temporais e Volatilidade da Ação da Tesla

Este repositório contém uma análise exploratória de dados (EDA) e implementação de modelos preditivos com dados históricos da ação da Tesla (TSLA). O objetivo é entender o comportamento da ação, sua volatilidade, e tentar prever seus preços.

## Conteúdo

1.  **`TESLA.csv`**: Arquivo CSV contendo os dados históricos da ação da Tesla.
2.  **`S&P500.csv`**: Arquivo CSV contendo os dados históricos do índice S\&P 500 (usado como referência na análise).
3.  **`analysis.ipynb`**: Notebook Jupyter com a análise exploratória dos dados, a implementação de modelos de séries temporais (ARIMA, Prophet, e LSTM) e a análise da volatilidade e da relação com o índice S\&P 500.
4.  **`README.md`**: Este arquivo, contendo informações sobre o projeto e as análises realizadas.
5.  **`ts_plot.png`**: Imagem com o gráfico da variação dos preços ao longo do tempo.
6.  **`volatility_plot.png`**: Imagem com o gráfico da variação da volatilidade da ação.
7.   **`rmse_plot.png`**: Imagem com o gráfico das métricas dos modelos.
8. **`candle_stick.gif`**: GIF mostrando o gráfico de candlestick dos preços da Tesla.

## Análise Realizada

A análise exploratória e preditiva foi feita usando Python, com o auxílio de bibliotecas como `pandas`, `matplotlib`, `seaborn`, `statsmodels`, `prophet`, `tensorflow` e `plotly`. As seguintes análises foram conduzidas:

*   **Importação e limpeza dos dados:** Carregamento, limpeza, e preparação do CSV para a análise, incluindo a conversão da coluna de data e remoção da coluna de index.
*   **Análise de séries temporais:** Implementação e comparação dos modelos ARIMA, Prophet, e LSTM para a previsão dos preços de fechamento da ação da Tesla. Os modelos ARIMA e Prophet foram implementados com otimização automática de parâmetros.
*   **Análise de volatilidade:** Cálculo e visualização da variação percentual diária, mostrando a volatilidade da ação ao longo do tempo e fornecendo estatísticas descritivas da variação.
*   **Análise de eventos:** Identificação de datas de eventos relevantes nos últimos anos e visualização de como a ação reagiu a esses momentos de mercado.
*   **Análise de outros fatores:** Introdução do índice S\&P 500 como variável preditora em um modelo de regressão linear simples, avaliando seu impacto no preço da ação da Tesla.
*   **Visualizações adicionais:**
    *   Média móvel dos preços para suavizar a variação e facilitar a identificação de tendências.
    *   Gráfico de candlestick para visualizar a evolução da ação dia a dia.

## Insights e Conclusões

*   **Tendência de Alta:** Os preços das ações da Tesla demonstraram um crescimento substancial ao longo do tempo, com flutuações e momentos de alta volatilidade.
    <img src="ts_plot.png" alt="Preços ao longo do tempo" width="500">

*   **Volatilidade:** A ação apresenta alta volatilidade diária, com períodos de picos expressivos de volume de negociação.
   <img src="volatility_plot.png" alt="Volatilidade ao longo do tempo" width="500">

*   **Outliers:** Foram identificados outliers, especialmente nos dados de volume e preço. É necessária uma investigação mais aprofundada sobre os eventos que causam esses outliers.
*   **Correlação:** Os preços de abertura, máxima, mínima e fechamento são altamente correlacionados, conforme o esperado. O volume tem baixa correlação com os preços.

*   **Modelos de Séries Temporais:**
    *   O modelo ARIMA, ajustado automaticamente, conseguiu capturar tendências gerais, mas com resultados pouco precisos na previsão de curto prazo.
    *   O modelo Prophet, utilizando sazonalidades anuais e semanais, teve um desempenho melhor que o ARIMA, porém ainda com alta volatilidade.
    *   O modelo LSTM conseguiu gerar previsões com menor RMSE do que os outros modelos, apresentando resultados mais precisos nas ultimas datas.

    <img src="rmse_plot.png" alt="Resultados dos modelos de regressão" width="500">

*   **Fatores Externos:** A variação dos preços da ação da Tesla apresenta uma correlação com a variação do índice S\&P 500, indicando uma influência do mercado no preço da ação.
*   **Impacto de Eventos:** O mercado reage fortemente a notícias e informações relevantes, impactando o preço da ação de forma positiva ou negativa.

     ![Gráfico Candlestick](candle_stick.gif)

## Recomendações

*   **Aprimoramento dos Modelos:** Testar diferentes configurações de modelos de séries temporais, principalmente no LSTM, para ver se é possível aprimorar sua precisão e avaliar como parâmetros como `look_back`, `epochs` e `batch_size` podem afetar a previsão do modelo.
*   **Dados Externos:** Incluir mais dados externos como taxas de juros, notícias macroeconômicas, e outras informações relevantes para a empresa.
*   **Análise de Sentimento:** Implementar a análise de sentimento com uso de APIs para correlacionar o sentimento do mercado com o desempenho da ação.
*  **Atenção à Volatilidade:** Ao analisar a ação da Tesla, considerar sua alta volatilidade, buscando modelos preditivos mais robustos e, para investidores, estratégias mais conservadoras.

## Como Usar

1.  Clone este repositório.
2.  Certifique-se de ter o Python instalado (versão 3.6 ou superior).
3.  Instale as bibliotecas necessárias:
    ```bash
    pip install pandas matplotlib seaborn statsmodels pmdarima prophet tensorflow scikit-learn plotly
    ```
4.  Execute o notebook `analysis.ipynb` para reproduzir as análises e visualizar os resultados.

