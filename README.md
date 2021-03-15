# Projeto Airbnb: Previsão do preço da estadia (feature 'price')

## a. Como foi a definição da sua estratégia?
1. Baixar os dados
2. Análise Exploratória
3. Machine Learning
4. Separar o conjunto de dados original em dois conjuntos TREINO/TESTE:
 * 90% para TREINO e VALIDAÇÃO
 * 10% somente para TESTE no final
5. Transformação dos dados
6. Definição da Baseline
7. Analisar os resultados iniciais de vários modelos
8. Selecionar 2 com melhores resultados
9. Treino e validação variando entre as variáveis e transformações, e seleção de features
10. Selecinar somente um modelo
11. Criar um grid para testar os hiperparâmetros com RandomSearchCV
12. Com os melhores hiperparâmetros encontrados, criar um grid variando entre esses e rodar com GridSearchCV, para "ajuste fino"
13. Treinar o modelo com todos os dados (90% que separamos para conjunto de treino)
14. Usar esse modelo treinado para prever os valores no conjunto de teste (10% separados)
15. Avaliar o resultado Final

## b. Como foi definida a função de custo utilizada
A função de custo foi definida avaliando a performance, reduzindo o MAE (Mean Absolute Error) e MSE (Mean Squared Error) e aumentando R^2 (R squared).

## c. Qual foi o critério utilizado na seleção do Modelo Final?
O modelo que obteve a melhor performance entre as variações das features, transformações e definição dos melhores hiperparâmetros

## d. Qual foi o critério utilizado para validação do modelo? Por que escolheu utilizar esse método?
Acompanhei 3 métricas, olhando individualmente cada uma tem sua característica. O MAE basicamente ajusta com base na mediana e o MSE com base na média e o R^2 mostra o quanto o resultado do modelo é explicado pelas variáveis. Outro fator relevante e que influencia nessas métricas, são os outliers no qual tomei um certo cuidado em removê-los para não reduzir muito o conjunto de dados.

## e. Quais evidências você possui de que seu modelo é suficientemente bom?
Tive uma melhora significativa entre a baseline e o modelo final, separei 10% somente para testar o modelo final, afim de simular uma situação próximo do real, no qual chegam dados que o modelo nunca viu. Além de ter tomado todo o cuidado para não ter vazamento de dados no treino e validação.

O resultado final, com o conjunto de teste, ficou próximo do que eu tinha validado com os dados de treino e validação, não havendo overfitting e nem underfitting.

Conclusões e Resultados

BASELINE:

    MSE: 14404.359124812358
    MAE: 98.5996424320113
    R^2: 0.2230869229876291

MODELO FINAL:

    MSE: 0.22092239961241997
    MAE: 0.38204143416778236
    R^2: 0.40775596609311504
