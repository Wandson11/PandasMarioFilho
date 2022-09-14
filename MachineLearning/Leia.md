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
004 - Explicacao do que é overfitting e underfitting.
- Overfitting, modelo em que cada elemento do conjunto de dados, terá a sua própria folha ou nós, remete a árvore com muita profundidade, e nao dará resultados bons;
- Underfitting, modelo que é o inverso do over, pouca profundidade, resultados ruins tanto no treino quanto na validação.
- Solução para qualquer um dos dois casos: max_leaf_nopes, onde é definido a quantidade de elementos que cada elemento/nós, vai ter, tendo-se assim, uma média.
005 - Random Forest é uma alternativa ao modelo de decision tree, sendo o r.f. mais sofisticado na elaboração das médias.
- Para chamar esse modelo, é parecido com o decision: from sklearn.ensemble import RandomForestRegressor
- Nesse caso: variavel = RandomForestRegressor(random_state=x), é essencial repassar "random_state" como parâmetro.
- Explicando o funcionamento: sao criadas diversas arvores que receberam dados aleatórios e features aleatórias para fazer o cálculo.
- Os demais procedimentos são os mesmos: variavel.fit(train_X, train_y); variavel.predict(val_X); mean_absolute_error(val_y, predict).
- Tem commo definir a profundidade das árvores/números de árvores: RandomForestRegressor(n_estimators= x) (por padrao, são 100 árvores)
- min_sample_leaf, é parecido com o max_leaf_nopes,porém, voce indica a quantidade por nó. É bom usar em datasets pequeno min_sample_leaft = 2
- Também pode ser alterado o máximo de features por árvore: max_features
