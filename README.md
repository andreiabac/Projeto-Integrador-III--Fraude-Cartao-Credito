
# PROJETO INTEGRADOR III - Fraude Cartão de Crédito

O objetivo do PROJETO INTEGRADOR III é criar e avaliar modelos de modelos de classificação que possam prever probabilidade de transações de artões de crédito serem fraudes.
O banco de dados utilizado para testar os modelos foi da base de dados do Kaggle, https://www.kaggle.com/code/hiteshpradhan1408/creditcard-fraud-classification.
Esse projeto foi desenvolvido por um grupo de alunos de Data Science da Digital House.


## Autores

- [@aleeexp](https://github.com/aleeexp)
- [@guilherme-atomo](https://github.com/guilherme-atomo)
- [@gentile95](https://github.com/gentile95)


## Documentação

   1 - FEATURES DA BASE DE DADOS
        As colunas do banco de dados card_transdata são:
        Distância do local da transação até o endereço do dono do cartão (distancefromhome);
        Distância do local da transação até o local da transação anterior (distancefromlast_transaction);
        Proporção do preço da transação em relação ao preço médio de transações (ratiotomedianpurchaseprice);
        Transação ocorreu ou não no mesmo estabelecimento (repeat_retailer);
        Transação realizada ou não usando chip - cartão de crédito (used_chip).
        Transação realizada ou não usando número PIN (usedpinnumber);
        Transação é ou não uma compra online (online_order);.
        Transação é ou não fraudulenta (fraud).

   2 - ANÁLISE EXPLORATÓRIA.
        Primeiramente foi analisada a correlação entre as features de conjunto de dados com a variável meta ‘fraud’.
        Encontramos maior correlação com as variáveis: 
            ● Proporção ao preço de compra da média (0,46)
            ● Pedido Online (0,19)
            ● Distância de casa (0,19)
            ● Distância da última transação (0,092)

   3 - BALANCEAMENTO DOS DADOS
        A quantidade de registros que correspondem aos dados fraudados no conjunto representa 8.7% do total, então os dados estão totalmente desbalanceados.
        Para resolver esse problema iremos usar a técnica UNDER-sampling dividindo a base de treino com 50% de dados fraudados e 50% de dados não fraudados.
        A base de dados foi reduzida para 50.000 registros, depois o split separando 30% dos dados para teste. Após o 
        split foi feito o undersampling na base de treino. 

   4 - MODELOS TREINADOS
        - lOGISTIC REGRESSION
        - RANDOM FOREST
        - KNEIGHBORS CLASSIFIER
        - DECISION TREE

   5 - RESULTADOS
        - A maior parte dos modelos apresentaram a curva ROC próxima da linha “perfect”, sendo que o modelo de Logistic Regression é mais próxima a linha “random”:
        ● Random (chance) Prediction: AUROC = 0.500
        ● Logistic Regression: AUROC = 0.980
        ● Random Forest: AUROC = 1.000
        ● KNeighbors Classifier: AUROC = 0.991
        ● Decision Tree: AUROC = 0.997
       - RESUMO DAS MÉTRICAS DOS MODELOS
        Para todos os modelos testados foram coletadas as métricas acurácia de treino e teste, recall, curva auc e F1 score. 
        Notamos que para os modelos de classificação Random Forest e Decision Tree, foram os que obtiveram melhor Recall, 
        indicando maior sensibilidade a resultados positivos.
        Também observamos que a métrica F1 score para os modelos Randon Forest e Decision Tree também é alta, confirmando que ambos foram os que tiveram melhor resultado.



## Conclusões
   Todos os modelos treinados trouxeram boas previsões, porém como o conjunto de dados é desbalanceado a métrica F1 score, que é a média harmônica entre Recall e Precision, neste caso é a que teve maior peso em nossa análise. 
    Portanto o modelo de classificação RandomForest seguido pelo Decision Tree, foram os que tiveram melhor desempenho levando em consideração o F1score.