# projeto-de-data-science-com-dados-do-titanic
## 1. Introdução
O naufrágio do Titanic, ocorrido em 1912, é um dos desastres marítimos mais estudados. A base de dados do Titanic é frequentemente utilizada em projetos de **ciência de dados** por conter informações sobre os passageiros (idade, sexo, classe social, tarifa paga, local de embarque, etc.) e a variável alvo **“Survived”** (sobreviveu ou não).  

O objetivo deste projeto é **aplicar técnicas de aprendizado de máquina para prever a sobrevivência de passageiros**, utilizando um modelo supervisionado de classificação.

---

## 2. Metodologia

### 2.1 Coleta de Dados
Os dados foram obtidos a partir de um **dataset público** hospedado no GitHub, em formato CSV.  

### 2.2 Preparação dos Dados
As seguintes etapas de pré-processamento foram realizadas:
- **Remoção de colunas irrelevantes**: `PassengerId`, `Name`, `Ticket`, `Cabin`.  
- **Tratamento de valores ausentes**:
  - `Age`: preenchido com a média.  
  - `Embarked`: preenchido com a moda.  
- **Codificação de variáveis categóricas**: uso de **one-hot encoding** (variáveis dummies).  

### 2.3 Divisão dos Dados
O dataset foi dividido em:
- **Treino**: 80%  
- **Teste**: 20%  
com `random_state=42` para reprodutibilidade.  

### 2.4 Modelo Utilizado
Foi implementado o algoritmo **Random Forest Classifier**, com os seguintes parâmetros principais:
- `n_estimators=100`  
- `random_state=42`  

---

## 3. Resultados

### 3.1 Avaliação do Modelo
O modelo foi avaliado com as métricas de classificação do **Scikit-learn**:
- **Acurácia**: aproximadamente **0.77 – 0.82** (dependendo da divisão treino/teste).  
- Relatório de classificação: apresentou desempenho balanceado entre precisão, recall e f1-score para as classes **sobreviveu (1)** e **não sobreviveu (0)**.  

### 3.2 Importância das Variáveis
As principais variáveis preditoras da sobrevivência foram:  
1. **Sex (female/male)**  
2. **Fare (valor da tarifa paga)**  
3. **Pclass (classe do passageiro)**  
4. **Age (idade)**  
5. **SibSp (número de irmãos/cônjuges a bordo)**  

Esses resultados estão em linha com registros históricos, nos quais mulheres, crianças e passageiros de classes mais altas tiveram maior taxa de sobrevivência.

---

## 4. Conclusão
O modelo de **Random Forest** mostrou-se eficaz na previsão da sobrevivência de passageiros do Titanic, alcançando uma acurácia consistente em torno de **80%**.  

### Pontos fortes:
- Boa performance com poucas etapas de engenharia de atributos.  
- Capacidade de identificar as variáveis mais relevantes para o problema.  

### Limitações:
- Modelo treinado apenas com as features originais; engenharia de atributos adicionais poderia melhorar os resultados.  
- Dataset restrito ao conjunto de treino fornecido (não contém todos os registros históricos).  

### Próximos Passos:
- Testar outros algoritmos de classificação (Logistic Regression, XGBoost, etc.).  
- Implementar técnicas de otimização de hiperparâmetros (GridSearchCV, RandomizedSearchCV).  
- Avaliar o impacto de variáveis derivadas, como faixas etárias e grupos familiares.  

---

## 5. Referências
- Kaggle Titanic Dataset: [https://www.kaggle.com/c/titanic](https://www.kaggle.com/c/titanic)  
- Documentação Scikit-learn: [https://scikit-learn.org](https://scikit-learn.org)  
- Hastie, T., Tibshirani, R., Friedman, J. (2009). *The Elements of Statistical Learning*. Springer.  
