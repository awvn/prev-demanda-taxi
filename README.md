### Project - Taxi Demand Prediction

**Problema de Negócio:** Prever a quantidade de pedidos de táxi para a próxima hora nos aeroportos, otimizando a alocação de motoristas nos horários de pico.

**Solução:** Reamostragem de séries temporais, criação de atributos de calendário e médias móveis, e avaliação comparativa entre Linear Regression, Random Forest, Gradient Boosting e LightGBM. Sendo o modelo Random Forest Regressor, o campeão ao atingir REQM (RMSE) de 45,65 no conjunto de teste, superando a meta estabelecida de 48. 

## ⚠️ Limitações e Evolução Futura

### Limitações dos Dados e do Modelo
* **Desempenho Experimental vs. Produção:** O erro obtido pelo **Random Forest Regressor** (**REQM / RMSE de 45,65 pedidos por hora** no conjunto de teste) valida a eficácia da preparação da série temporal (criação de *lags*, médias móveis e atributos de calendário) neste recorte histórico. Contudo, esse valor representa uma **referência experimental em dados históricos estáticos**, e não uma garantia de precisão contínua em ambiente de produção.
* **Ausência de Variáveis Exógenas e Limite de Extrapolação:** Modelos baseados em árvores (como o *Random Forest*) não extrapolam tendências de crescimento fora do intervalo observado no treino. Além disso, o dataset contém apenas o histórico de pedidos agregados por hora, sem variáveis externas que causam picos abruptos na demanda real — como condições meteorológicas (chuva intensa), feriados locais, grandes eventos ou interrupções no transporte público.

### Melhorias Futuras
* **Enriquecimento com Dados Externos:** Integrar dados climáticos horários, calendário de feriados e eventos locais para reduzir erros residuais em horários de pico atípicos.
* **Validação Temporal Robusta e Re-treinamento:** Substituir a divisão única de treino/teste por **validação cruzada em janela deslizante (*TimeSeriesSplit / Walk-Forward Validation*)** e estabelecer rotinas de re-treinamento periódico para acompanhar mudanças sazonais na mobilidade urbana.
* **Experimentação de Arquiteturas Híbridas:** Testar modelos especializados em séries temporais com tendência (como *LightGBM* com diferenciação, *Prophet* ou modelos autorregressivos) e monitorar o desvio de previsão (*prediction drift*) antes de qualquer uso operacional para alocação dinâmica de frota.


**Foco Técnico:** Validação temporal e minimização do erro quadrático médio (RMSE).

### 🚀 Tecnologias
- Python
- Pandas
- Matplotlib
- seaborn
- Sklearn
- LGBMRegressor
- Linear Regression
- Random Forest
- seasonal_decompose

### 📦 Como instalar

``` bash
git clone https://github.com/awvn/prev-demanda-taxi.git
cd prev-demanda-taxi
pip install -r requirements.txt
