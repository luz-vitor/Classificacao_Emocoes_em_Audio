# Classificação de Emoções em Áudio - Projeto Final de Aprendizado de Máquina

Feito em parceria com [@thiagomiyazaki](https://github.com/thiagomiyazaki) para conclusão da disciplina de aprendizado de máquina.

Este projeto visa a construção de modelos de aprendizado de máquina para a classificação de emoções em arquivos de áudio, utilizando os conjuntos de dados:
- TESS (Toronto Emotional Speech Set)
- RAVDESS (Ryerson Audio-Visual Database of Emotional Speech and Song)
- SAVEE (Surrey Audio-Visual Expressed Emotion)
- CREMA_D (Crowd Sourced Emotional Multimodal Actors Dataset)

O objetivo principal é comparar diferentes algoritmos de classificação e identificar o que apresenta o melhor desempenho na tarefa.

## Estrutura do Projeto

### Importação de Bibliotecas: 
As bibliotecas essenciais como pandas, numpy, librosa, e sklearn são carregadas para manipulação de dados, extração de características, e construção dos modelos de machine learning.

### Carregamento e Preparação dos Dados: 
Os arquivos de áudio são carregados e organizados em um DataFrame, onde as emoções e caminhos dos arquivos são mapeados.

### Extração de Características: 
Features como Mel-frequency cepstral coefficients (MFCCs), e outros (Dê uma espiadinha no código...) são extraídas dos arquivos de áudio para alimentar os modelos de classificação. 

### Construção de Modelos: 
Diversos modelos de machine learning são treinados, incluindo:
- DecisionTreeClassifier
- KNeighborsClassifier
- Support Vector Classifier
- MLPClassifier
- RandomForestClassifier

### Avaliação dos Modelos: 
Os modelos são avaliados com métricas como accuracy, f1-score, precision, e recall, utilizando validação cruzada.

### Otimização de Hiperparâmetros: 
A técnica de Grid Search é utilizada para encontrar a melhor combinação de hiperparâmetros para os modelos.

## Resultados dos Classificadores
Os resultados finais são apresentados em termos de acurácia e outras métricas de desempenho, permitindo uma comparação clara entre os diferentes modelos implementados.

| Classificador              | Conjunto | Instâncias | Atributos | Classes | Melhor Configuração                                                                 | Melhor Pontuação | Acurácia | Precisão | Recall  | F1-Score |
|----------------------------|----------|------------|-----------|---------|-------------------------------------------------------------------------------------|------------------|----------|----------|---------|----------|
| **DecisionTreeClassifier**  | ALL      | 38304      | 190       | 7       | `{'criterion': 'entropy', 'splitter': 'best'}`                                      | 0.475720          | 0.502715 | 0.523195 | 0.502715 | 0.490327 |
| **KNeighborsClassifier**    | ALL      | 38304      | 190       | 7       | `{'n_neighbors': 1, 'p': 2}`                                                        | 0.655136          | 0.699875 | 0.703737 | 0.699875 | 0.700111 |
| **SVC**                     | SVC      | 38304      | 190       | 7       | `{'C': 7, 'kernel': 'rbf'}`                                                         | 0.628053          | 0.642439 | 0.643620 | 0.642439 | 0.640558 |
| **MLPClassifier**           | ALL      | 38304      | 190       | 7       | `{'hidden_layer_sizes': 50}`                                                        | 0.607901          | 0.633041 | 0.632487 | 0.633041 | 0.631256 |
| **RandomForestClassifier**  | ALL      | 38304      | 190       | 7       | `{'max_features': 'sqrt', 'n_estimators': 100}`                                     | 0.702325          | 0.747911 | 0.753842 | 0.747911 | 0.745840 |

## Autores do projeto

- [@thiagomiyazaki](https://github.com/thiagomiyazaki)
- [@luz-vitor](https://github.com/luz-vitor)
