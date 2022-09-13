Notebook das aulas e minhas tentativas de resolução para a introducação de machine learning.

001 - carregamento do arquivo e utilização do describe.
002 - escolhendo o alvo e os recursos do m.l.
-especificando o modelo: variavel = DecisionTreeRegressor(random_state=x)
-formatando a árvore: variavel.fit(features, alvo)
-prevendo os valoes: variavel.predict(recurso).
o alvo, geralmente será uma unica coluna onde a mesma fará referencia a valor
as features serão um conjunto de colunas que auxiliarão nas predições.
Se não for retirado uma amostra e não o conjunto inteiro, a resposta da predcit será muito próxima da real, o que é para gerar desconfiança.
Para retirar essa incerteza tem a parte 003 abaixo.
003 - utilização de código para separar os dados por meio do "train_test_split".
-modelo do "train_test_split": train_X, val_X, train_y, val_y = train_test_split(X, y, random_state=1)
onde train_X e train_y, são dados de treino, onde em média, contém 70% do conjunto de dados, enquanto os demais 30% se encontram em val_X e val_y.
- em variavel = DecisionTreeRegressor(random_state=1);
- variavel.fit(train_X, train_y)
- variavel.predict(val_X)
- Apresenta novo conceito:  MEAN ABSOLUTE ERROR, em que se busca a diferença entre os valores do predcit com o real (val_y): from sklearn.metrics import mean_absolute_error
- mean_aboslute_error(val_y, variavel da predict)
