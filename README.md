# UCIRSS

Esse projeto foi uma analise da base de dados **Indoor User Movement Prediction** do respositório [UCI](http://archive.ics.uci.edu/ml/datasets/Indoor+User+Movement+Prediction+from+RSS+data#)

Esse pequeno projeto foi focado na classificação dos usuarios que realizaram ou não mudança de salas durante sua estadia nos comodos.
Mais informações [aqui](http://wnlab.isti.cnr.it/paolo/index.php/dataset/6rooms)

Basicamente, foi realizada uma analise de 3 comodos com 2 salas separadas. O objetivo é criar um classificador que com sucesso entenda quando 
o usuario muda ou não de sala durante sua estadia. Isso tudo apartir da coleta de dados por 4 roteadores fixos e um móvel (atrelado ao usuario).


#NoteBooks
Cada notebook tem informações a respeito do problema; Desde uma pequena analise dos dados até a construção de diversos classificadores abordando diversas formada de lidar ou não 
com os dados coletados.

##NoteBooks: `Problem analysis.ipynb`

Nesse notebook é visto como os dados são dispostos e qual a importancia dos passos anteriores para a os próximos passos.
Em suma, uma pequena analise dos dados.

##Apresentação do projeto

  1. O código do projeto;

      **Em todos os NoteBooks com excessão `Problem analysis.ipynb`**

  2. Instruções de como rodar o projeto no README;
      
      **Como foi utilizado** [ipython notebooks](http://blog.revolutionanalytics.com/2015/09/using-r-with-jupyter-notebooks.html) **apenas copiar o arquivo e rodar. As dependencias se encontram na parte superior de cada script.**

  3. Uma breve explanação concisa das suas principais decisões de projeto em um arquivo "REPORT.txt", tais como (mas não limitadas a):

      *O "Report.txt" Se encontra no mesmo README.md. Abaixo*

      **a. Qual algoritmo de classificação foi utilizado e o motivo;**
      
      Utilizei apenas 2 classificadores, KNN e SVM, considerei que o problema pode ser linearmente separavel.
      Mais importante que os classificadores, são as estratégias de manipulações dos dados e o entendimento da base e do problema.
      
      O classificador é a ultima coisa que o analista deve se preocupar. Nos notebooks é feita uma pequena e inicial analise do problema e o seu comportamento diante de alguns classificaores.
      
      Utilizei no total 4 estratégias diferentes, descritas no cabeçalho de cada arquivo.
      
     **b. Qual a técnica de split utilizada e o motivo;**
      
      Nese projeto apenas usei 2 bases, uma base de treinamento e uma de teste. Durante o split as bases foram estratificadas, para que as bases sejam devidamente porporcionais em ambas classes binárias. Para manter o processo simples decidir não utilzier a base de validação. Decidir explorar de forma mais adequada o etendimento do problema e o comportamento dele diantes das estratégias utilizadas.
      
      Diante de cada modelo utilizamos 10-fold cross validation. Após isso fazemos a média e o desvio padrão da taxa de acerto (accuracy). A média e o sd (desvio padrão) nos informa se o modelo criado é robusto e que a solução oferecida é estável.
      
      **c. Processo de feature engineering, caso haja;**
      
      Foi utilizado DTW, DWT e PCA, todos em cada arquivos separado e com suas respectivas explicações.
      
      **d. Descrição das métricas através das quais o modelo foi avaliado**
      
      Além da taxa de acerto, usamos matrix de confusão. 
      
      Na parte final usamos também curva **ROC** e **AUC** (area under curve). Essas métricas nos permite comparar modelos diferentes diantes do mesmo problema de forma efetiva (quantitativa usando **AUC**) e gráfica (usando curva **ROC**).
      
      Essas métricas são as clássicas e mais utilizadas no processo de criação de modelos de classificadores binários.
      


