### Project - Taxi Demand Prediction

**Problema de Negócio:** Prever a quantidade de pedidos de táxi para a próxima hora nos aeroportos, otimizando a alocação de motoristas nos horários de pico.

**Solução:** Reamostragem de séries temporais, criação de atributos de calendário e médias móveis, e avaliação comparativa entre Linear Regression, Random Forest, Gradient Boosting e LightGBM. Sendo o modelo Random Forest Regressor, o campeão ao atingir REQM (RMSE) de 45,65 no conjunto de teste, superando a meta estabelecida de 48. 

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
