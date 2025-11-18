# 🏡 Análise de Preços de Imóveis para Aluguel em São Paulo — Meu Primeiro Projeto de Machine Learning

Este repositório contém **meu primeiro projeto prático na área de Machine Learning**, onde aplico técnicas fundamentais de análise, preparação de dados e regressão para prever **preços de aluguel de imóveis** na cidade de São Paulo.

Foi meu **ponto de partida** no aprendizado de ML, servindo como base para entender o fluxo completo:

- Coleta e leitura de dados
- Limpeza e preparação
- Codificação de variáveis categóricas
- Separação entre treino e teste
- Treinamento de modelos
- Avaliação com métricas
- Validação cruzada
- Ajuste de hiperparâmetros
- Visualização de previsões

---

## 📂 Dataset Utilizado

Este projeto utiliza um arquivo CSV contendo imóveis anunciados em São Paulo.

### 🔗 Link do Dataset (Kaggle)
➡️ https://www.kaggle.com/datasets/argonalyst/sao-paulo-real-estate-sale-rent-april-2019

---

## 🧹 1. Limpeza e Preparação dos Dados

As etapas realizadas foram:

- Leitura do dataset via `pandas`
- Filtragem para considerar somente imóveis **do tipo "rent"**
- Remoção das colunas:
  - `New`
  - `Negotiation Type`
  - `Property Type`
- Conversão da coluna **District** para variáveis dummies via *One-Hot Encoding*
- Separação em:
  - `X` — features (todas as colunas exceto preço)
  - `y` — preço (`Price`)
- Divisão dos dados em treino e teste com 70/30

---

## 🤖 2. Modelos Treinados

Três modelos foram testados para prever os preços:

---

### 🔹 **1. Linear Regression**

- Modelo mais simples e usado como baseline
- Serve como referência inicial
- Obteve o maior erro entre os três modelos

---

### 🔹 **2. DecisionTreeRegressor**

- Modelo de árvore de decisão
- Captura relações não-lineares entre os atributos
- Apresentou desempenho melhor que a regressão linear
- Porém demonstrou sinais de overfitting

---

### 🔹 **3. RandomForestRegressor (Melhor Modelo)**

- Ensemble de múltiplas árvores de decisão
- Mais estável e com menor variância
- Utilizou validação cruzada (10-fold)
- Passou por ajuste fino (GridSearchCV)

Melhores hiperparâmetros:

```python
{'max_features': 6, 'n_estimators': 30}
```

Este se tornou o **modelo final** do projeto.

---

## 🧪 3. Resultados Obtidos

Abaixo está a comparação qualitativa entre os modelos utilizados:

| Modelo                   | Desempenho Geral | Observações |
|-------------------------|------------------|-------------|
| Linear Regression       | ❌ Fraco         | Não capturou padrões complexos |
| Decision Tree           | ⚠️ Médio         | Overfitting evidente |
| Random Forest           | ✅ Melhor        | Melhor RMSE e maior estabilidade |

---

## 🖼️ 4. Espaço para Prints Gerais do Projeto

### Dataset inicial:

<img width="1113" height="204" alt="image" src="https://github.com/user-attachments/assets/c7e917b2-1a88-4522-bf9f-e1d3b2a0a127" />


### Gráfico plotado:

<img width="1545" height="371" alt="image" src="https://github.com/user-attachments/assets/bd26e826-acdc-4217-803b-3cf5ce55a60e" />


---

## 🚀 5. Próximos Passos

- Aplicar normalização/standardização
- Testar modelos mais avançados (XGBoost, LightGBM, CatBoost)
- Criar novas features que expliquem melhor o preço
- Avaliação por SHAP (explicabilidade)
- Deploy simples via API ou Streamlit

---

## 🎯 Conclusão

Este projeto representou meu **primeiro contato real com Machine Learning**, onde consegui:

- Preparar dados reais
- Treinar e avaliar múltiplos modelos
- Entender o impacto da validação cruzada
- Explorar ajuste de hiperparâmetros
- Visualizar resultados reais vs previstos

Foi o início da minha jornada prática no universo da IA e abriu espaço para projetos mais complexos e avançados.

