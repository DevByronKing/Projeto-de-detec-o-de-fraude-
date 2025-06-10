Projeto de detecção de fraude em cartão de crédito.

Este projeto tem como objetivo construir modelos de Machine Learning capazes de identificar transações fraudulentas em um conjunto de dados, lidando eficazmente com as características específicas de dados desequilibrados (fraudes são raras) e utilizando considerações de avaliação específicas.

O objetivo deste modelo é que ele seja capaz de reconhecer transações fraudulentas de cartão de crédito.
A métrica utilizada será: Área sob a Curva ROC (AUC-ROC)
A AUC-ROC é uma métrica que avalia o desempenho de modelos de classificação binária em diferentes limites de decisão. Ela mede a área sob a curva da Taxa de Verdadeiros Positivos ( Recall ) em função da Taxa de Falsos Positivos.

Etapa 1: Aquisição de Dados (Dataset Kaggle):
link: https://www.kaggle.com/mlg-ulb/creditcardfraud

Etapa 2: Baixando o dataset:
Aquivo baixado em formato zip e em seguida descompactado.

Etapa 3: Configurando o ambiente de trabalho:
A ferramenta escolhida foi Google Colab e o projeto será feito em Python.
Instalação de biblbiotecas essênciais: Pandas, Numpy, Scikit-learn, Matplotlib e Seaborn, com o prompt de comando: 

pip install pandas numpy scikit-learn matplotlib seaborn

![Captura de tela 2025-06-10 154956](https://github.com/user-attachments/assets/a0c6761c-58c5-4db7-90a2-1e9e011657b8)

Etapa 4: Carregando os dados no Colab fazendo o upload dos dados feitos anteriormente.

![Captura de tela 2025-06-10 161830](https://github.com/user-attachments/assets/015c70b3-31df-4096-b9c7-87be8e5f9201)

Etapa 5: Primeira Visualização e Entendimento Rápido (O Início da EDA):

![Captura de tela 2025-06-10 154019](https://github.com/user-attachments/assets/1c5ac33e-f25a-44f4-b607-d39536a0fd72)


Após o carregamento, é fundamental fazer uma inspeção inicial para confirmar se o carregamento foi preenchido e ter uma primeira ideia dos dados:

![Captura de tela 2025-06-10 152630](https://github.com/user-attachments/assets/78fcc8a3-db65-4cfb-9526-4f0d465e5e13)

Etapa 6: Análise exploratória de dados (EDA):
6.1 O objetivo é investigar, resumir e visualizar os dados para descobrir insights e preparar o terreno para a modelagem.
Utilizo o prompt abaixo para entender a distribuição das classes FRAUDE/NÃO-FERAUDE
utilizando o prompt:

![Captura de tela 2025-06-10 161556](https://github.com/user-attachments/assets/dccd1a8b-7cd0-45dc-8318-debd64483035)

Obtém o seguinte resultado: 

![Captura de tela 2025-06-10 161706](https://github.com/user-attachments/assets/10dcc955-f8b4-4dcd-b90f-9ecdf93bb4c9)

No resultado acima constata-se um número muito menor de transações fraudulentas (Classe 1) em comparação com as não fraudulentas (Classe 0). Isso confirma a natureza desequilibrada do problema e valida a necessidade das técnicas que usarei no tratamento de dados desequilibrados.

6.2 Análise de Variáveis ​​Numéricas Chave ('Valor' e 'Tempo')

![image](https://github.com/user-attachments/assets/d57f8494-9fa9-47a9-85cc-0a7944e5f738) 

Resultdo: 

![image](https://github.com/user-attachments/assets/aaa45ccf-b2fe-4772-a9f4-a587caa6dab1)

6.3 Pode-se obter o tempo de transação delatlhado:

![image](https://github.com/user-attachments/assets/abd6f36b-0e3a-4bd7-ae31-b6c29b7d98b7)

Esta coluna representa o tempo decorrido desde a primeira transação no conjunto de dados. Pode indicar padrões de fraude em determinados períodos do dia, existem horários específicos onde a fraude é mais comum.

![image](https://github.com/user-attachments/assets/18a780c5-752c-42e0-8d58-13baedf16814)

6.4 Análise dos Componentes Principais (Recursos V1-V28)
No conjunto de dados de crédito, as colunas V1a V28são os resultados de uma Análise de Componentes Principais (PCA) para preservar a privacidade do usuário. Comparar distribuições por classe: Use box plots ou histplotpara comparar a distribuição de cada Ventre transações fraudulentas e não fraudulentas. Para fraudes, alguns desses componentes podem ter distribuições visivelmente diferentes.

![image](https://github.com/user-attachments/assets/e3e6e670-dec5-45f3-b19b-6254f840935f)

Resultando: 

![image](https://github.com/user-attachments/assets/97860e6b-dfba-47e1-abb8-43fc9f328e1d)

Nota-se características que mostram distribuições muito distintas entre as classes 0 e 1 são potencialmente as mais importantes para a detecção de fraudes.
 
6.5 Análise de Correlação (Entre Features e com a Classe Alvo)

![image](https://github.com/user-attachments/assets/1a9a789f-7667-4d2c-9ca6-baeda4bdd72f)

Resultando:

![image](https://github.com/user-attachments/assets/ee98b259-9a6e-4c12-8eb1-8fb114aac3d5)


Ao final desta etapa de análise exploratória de dados se tem um entendimento profundo do conjunto de dados, das características de transações fraudulentas e o do desequilíbrio das classes.































