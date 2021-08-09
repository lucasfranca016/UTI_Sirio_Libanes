# Projeto de análise e previsão do número de pacientes que irão para UTI no hospital Sírio-Libanês.

<p align="center"><img src=https://agenciapara.com.br/midias/2021/grandes/up_ag_24788_5973351a-687b-7fe9-6463-644f12ee2d5d.jpg?quality=70&strip=info&resize=680,453 </p> 
![Alt](https://agenciapara.com.br/midias/2021/grandes/up_ag_24788_5973351a-687b-7fe9-6463-644f12ee2d5d.jpg)

# **Introdução**

Este é o meu quarto projeto feito em função do Bootcamp de Data Science aplicada da Alura. Nele usarei os processos de análise e manipulação de dataframes em conjunto com ferramentas gráficas e algoritmos de Machine Learning para trabalhar com dados oferecidos pelo hospital Sírio-Libanês que representam pacientes verdadeiros do próprio hospital e sua ficha médica. Meu objetivo aqui é tentar trabalhar em cima das técnicas de optimização por mim aprendidas durante o curso para construção de um bom algoritmo que consiga prever corretamente se um paciente irá para a UTI ou não.

# **Contexto**
  
- A pandemia de COVID-19 impactou todo o plane, exigindo de mais dos sistemas de saúde - despreparado para uma demando intensa e larga por camas de UTI, profissionais, equipamentos de proteção pessoal e recursos para cuidado da saúde.
Brasil registrou seu primeiro caso de COVID-19 em 26 de Fevereiro de 2020 e o começo da transmissão comunitária em 20 Março de 2020.
  
- Há urgência em obter precisão para melhor prever e preparar os sitemas de cuidado à saúde e evitar colapso, definido pela necessidade de camas de UTI acima da capacidade (assumindo que recursos humans, EPI's e profissionais estão disponíveis), usando dados clínicos individuais - no lugar de dados epidemiológicos e populacionais.
  
<p align="center"><img src=https://img.medscape.com/thumbnail_library/cdc_200313_flatten_the_curve_800x450.jpg?quality=70&strip=info&resize=680,453 </p> 
  
# **Dados e sua formatação inicial**

Os dados utilizados neste projeto foram obtidos da página referente ao problema no site do [Kaggle](https://neptune.ai/blog/f1-score-accuracy-roc-auc-pr-auc#slideDown).

Nele temos uma coluna referente ao id do paciente, colunas referentes a sua faixa etária, colunas referentes à algumas doenças anonimizadas que o mesmo já tenha contraído, resultados de exames de saúde(exames de sangue e de sinais vitais), a janela de tempo após admissão no hospital ao qual aqueles dados de referem e a coluna que nos diz se nessa janela ele foi internado ou não na UTI.

Algumas resalvas foram dadas à cerca do uso dos dados assim como as seguintes descrições:
  
  - "Cuidado para NÃO usar os dados quando a variável de destino estiver presente(UTI = 1), pois a ordem do evento é desconhecida (talvez o evento de destino tenha acontecido antes de os resultados serem obtidos). Eles foram mantidos lá para que possamos aumentar este conjunto de dados em outros resultados posteriormente."
  - "Este conjunto de dados contém dados anônimos do Hospital Sírio-Libanês, de São Paulo e de Brasília. Todos os dados foram tornados anônimos de acordo com as melhores práticas e recomendações internacionais."
  - Os dados foram limpos e escalados por coluna de acordo com Min Max Scaler para caber entre -1 e 1.

# **Estrutura do notebook:**

- Importação das bibliotecas usadas.

- Importação dos dados.

- Definição de Funções.

- Tratamento de Dados.

- Métrica.

- Construção de um modelo preditivo

- Resultado
  
No próprio notebook há uma análise de cada passo que foi dado e o porquê ele foi dado, desde a análise até a construção dos modelos, assim como uma breve descrição da utilização das funções empregadas.
  
## **Metodologia e resultado:**

- Eu comecei analisando 5 modelos amplamente usados para problemas de classificação de dados: GradientBoostingClassifier, AdaBoostClassifier, KNeighborsClassifier, RandomForestClassifier e DecisionTreeClassifier. Dado esses 5 modelos eu utilizei 3 parâmetros para os avaliar: o F1-Score, o ROC AUC Score e o número de falsos negativos.
- Após uma primeira avaliação eu levei para frente os modelos de RandomForestClassifier e GradientBoostingClassifier a fim de fazer uma análise expandindo o limite dos parâmetros testados e o número de testes para se chegar na melhor parametrização, agora usando somente à métrica de F1 Score como argumento de otimização das funções.
- O resultado final foi de que a segunda avaliação foi um pouco obsoleta, gerando resultados muito parecidos ao da primeira análise para os dois modelos em questão. O número de falsos negativos para os dois modelos foi igual, contudo, a métrica F1 do modelo de RandomForest foi ligeiramente maior do que a do modelo de AdaBoost, assim, sendo o modelo mais adequado para ser implementado segundo os testes realizados, obtendo no final um F1 Score de 70.75 % e acertando aproximadamente 69% das previsões para os pacientes que precisam ir para a UTI.

## **Projeções futuras**

  - Esse projeto se limitou ao teste apenas de 5 modelos por questões de falta de tempo, assim, em um futuro trabalho essa análise pode ser extendida a outros modelos de classificação.
  - Cabe também estudar mais afundo a documentação dos modelos testados para então fazer uma escolha mais precisa de quais parâmetros podemos variar e quais seriam os melhores limites possíveis.
  - Um melhor estudo das métricas a serem utilizadas é bem vindo também, a fim de obtermos uma melhor avaliação para este problema específico, que exige uma atenção extra no número de falsos negativos por exemplo.
  - Refinar o tratamento da base de dados também é uma possibilidade, tendo em vista que fizemos o treino utilizando 97 features ainda, quantidade que pode vir a ser reduzida para melhor otimização e aprendizado dos modelos.

## **Contato**

Obrigado por conferir meu trabalho, me chamo Lucas França e atualmente sou graduando no curso de Física na Universidade Federal do Rio de Janeiro (UFRJ). Meu objetivo é continuar aprimorando minhas técnicas referentes à área de Data Science e implementar em projetos cada vez mais inovadores. =]

- Eu estou aberto para colaborações e ofertas de trabalho, então se você achou meu trabalho interessante e acha que eu tenho potencial para contribuir em seus projetos sinta-se livre para me mandar uma mensagem! Mesmo que você não tenha achado isso, mande-me uma mensagem de qualquer forma! Você pode me achar nos seguintes lugares:

<p>
  <a href="mailto:lucas.c.franca@gmail.com?Subject=From%20github">
    <img alt="Gmail" src="https://img.shields.io/badge/gmail-EA4335?logo=gmail&logoColor=white&style=for-the-badge" />
  </a>
  <a href="https://www.linkedin.com/in/lucas-fran%C3%A7a-83133016b/"><img alt="Linkedin" src="https://img.shields.io/badge/linkedin-0077B5?logo=linkedin&logoColor=white&style=for-the-badge" /></a>
</p>
  

## **Referências**

[[1]](https://neptune.ai/blog/f1-score-accuracy-roc-auc-pr-auc#slideDown) "F1 Score vs ROC AUC vs Accuracy vs PR AUC: Which Evaluation Metric Should You Choose?    ".
