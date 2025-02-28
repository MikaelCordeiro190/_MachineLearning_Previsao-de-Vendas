# Problema de Negocio
Prever as proximas semanas de vendas diárias para 32 lojas localizadas em Brasilia. Previsões de vendas confiáveis ​​permitem que os gerentes de loja criem cronogramas de equipe eficazes que aumentam a produtividade e a motivação.

# Sobre o Clientes
Uma Rede de Farmacia  do setor de varejo, especializada em produtos farmacêuticos, saúde, beleza, cuidados pessoais e bem-estar. Hoje, a empresa é uma das maiores redes de drogarias de Brasilia.  
O contexto deste projeto é baseado em uma reunião juntamento com o Gerentes e CCO, na qual o CCO da empresa fez uma solicitação de resultados mensais com todos os gerentes de loja e requisitou que cada um deles trouxesse uma previsão diária semanas de vendas, a fim de obter um orçamento para realizar uma reforma nas lojas. Portanto, é de fundamental importância obter essa previsão nas vendas. Em seguida, os gerentes entraram em contato com o time de dados da empresa, solicitando uma previsão de vendas das lojas as quais gerenciam.

# Descrição dos Dados

![image](https://github.com/user-attachments/assets/340cd3a5-15c8-49b1-9d66-52b883b4f8e5)


# Estratégia da Solução
Para garantir uma entrega rápida e eficiente do primeiro modelo, com o objetivo de trazer valor para a empresa e permitir decisões ágeis por parte do CCO, foi adotado o método CRISP-DM.

O método CRISP-DM é composto por 9 etapas cíclicas, em que a cada iteração dessas etapas, o resultado de negócio é aprimorado, buscando entregas cada vez mais rápidas e de maior qualidade, com maior precisão. Isso possibilita que as equipes que utilizarão os resultados desenvolvidos tenham um produto minimamente utilizável já na primeira entrega, e que seja aprimorado ao longo do tempo.

![image](https://github.com/user-attachments/assets/76d3e2c9-a5e1-4836-92f4-b092fe3d6fea)


CRISP-DM:

1. Problema de Negócio: Esta etapa tem como objtive receber o problema de negócio que será resolvido. É nesta etapa que é recebido a pergutna ou o pedido feito pelo dono do problema, que no caso deste projeto, é o CFO da rede Rossmann.

2. Entendimento de Negócio: Esta etapa tem como objetivo entender a dor do dono do problema e qual a sua real necessidade. Nesta etapa podem surgir protótipos da solução para validar com o dono do problema o que ele deseja como solução.

3. Coleta de Dados: Esta etapa tem como objetivo realizar a coleta dos dados, buscando eles nas tabelas do(s) banco(s) de dados da empresa.

4. Limpeza dos Dados: Esta etapa tem como objetivo remover toda e qualquer sujeira nos dados. Um dado sujo pode ser entendido como um dado que irá atrapalhar a performance final do algoritmo de Machine Learning. Tomando o cuidado entender bem o fenômeno que está sendo estudado para que não sejam removidos dados importantes para a modelagem do problema.

5. Exploração dos Dados: Esta etapa tem como objetivo entender os dados e como eles se relacionam entre si. Normalmente, são criadas hipóteses acionáveis de negócio que são posteriormente validadas utilizando técnicas de análise de dados. Além da criação de novas features que serão utilizadas na etapa de Modelagem de Dados.

6. Modelagem dos Dados: Esta etapa tem como objetivo preparar os dados para que eles sejam utilizados pelos algoritmos de Machine Learning. É nesta etapa que são feitos as transformações e encodign dos dados, a fim de facilitar o aprendizado do algoritmo utilizado.

7. Aplicação de Algoritmos de Machine Learning: Esta etapa tem como objetivo selecionar e aplicar algoritmos de Machine Learning nos dados preparados nas etapas anteriores. É nesta etapa que são selecionados os algoritmos e feito a comparação de performance enetre eles, para selecionar o algoritmos que melhor performou como algoritmo final.

8. Avaliação de Performance: Esta etapa tem como objetivo verificar a performance do algoritmo selecionado na etapa anterior com os resultados atuais, ou base line atual. Neste momento é feito a tradução da performance do algoritmo para perfomance de negócio. Ou seja, quanto a solução criada tratrá de retorno financeiro para a empresa. Caso a performance seja aceitável, o algoritmo é publicado e é retornado para a etapa de entendimento de negócio novamente, a fim entender melhor possíveis lacunas e assim melhorar a performance do algoritmo selecionado. Caso a performance não seja aceitável, o algoritmo não é publicado e é retornado para a etapa de entendimento de negócio para fazer uma nova iteração e assim melhorar a performance da solução.

9. Publicação da Solução: Esta etapa tem como objetivo publicar o algoritmo selecionado, deixando publico e utilizável a solução criada.

# Mindmap e Principais Insights
Para facilitar a análise exploratória foi criado um Mindmap para ajudar na construção de Hipóteses.

Mapa de Hipóteses foi criado na Ferramenta Coggle.

![image](https://github.com/user-attachments/assets/24638154-523f-476b-88bc-58cbe66485ef)


Através do Mindmap, foram geradas 19 hipóteses de negócio. Dessas, 12 foram selecionadas para validação, confirmando premissas da equipe de negócios e do responsável pelo problema. Além disso, foram gerados insights relevantes para ambos os grupos.

Dos 12 hipóteses verificadas, destacaram-se 3 principais insights.

# 1.1 Lojas deveriam vender mais depois do dia 10 de cada mês.

VERDADEIRA Lojas vendem mais depois do dia 10 de cada mes.

![image](https://github.com/user-attachments/assets/dcb96691-5aa1-4db5-ba13-2cb1f08790ed)


# 1.1 Lojas deveriam vender menos aos finais de semana.

VERDADEIRA Lojas vendem menos nos final de semana

![image](https://github.com/user-attachments/assets/5f8c5119-2f60-458d-a1cf-c608c4bf6790)


# 1.2 Lojas deveriam vender menos durante os feriados escolares.

VERDADEIRA Lojas vendem menos durante os feriadso escolares, except os meses de Julho e Agosto.

![image](https://github.com/user-attachments/assets/9bfa0bae-296f-4127-9007-903db611538a)


# Definição de Modelos de Machine Learning
No primeiro ciclo do projeto, foram selecionados cinco algoritmos para teste, visando identificar o algoritmo com melhor desempenho e custo de implementação. Nessa etapa inicial, optou-se pela simplicidade, considerando que era o primeiro ciclo do projeto e o objetivo principal era entregar uma solução mínima utilizável para a equipe de negócios e pelo CFO.

Os algotitmos selecionados foram:

Avarege Model
Linear Regression
Linear Regression - Lasso
Random Forest Regressor
XGBRegressor

Após a seleção dos algoritmos, procedemos com o treinamento e teste de cada um deles para avaliar sua performance. Além disso, utilizamos o método de seleção de features RFE para identificar as variáveis mais relevantes e impactantes na base de dados.

Os 5 algoritmos foram treinados e as métricas MAE, MAPE e RMSE. Aqui, nesta etapa também é realizado o processo de Cross-Validation (validação cruzada) visando impedir que o modelo esteja enviesado, devio a uma separação específica para os dados de validação.

*MAE* (Mean Absolute Error): O MAE é uma métrica de avaliação comum para modelos de regressão que calcula a média das diferenças absolutas entre as previsões do modelo e os valores reais. Ele fornece uma medida da magnitude média dos erros no modelo, onde valores menores indicam uma melhor precisão do modelo.

*MAPE* (Mean Absolute Percentage Error): O MAPE é uma métrica de avaliação frequentemente utilizada em previsões de séries temporais e modelagem de demanda. Ele calcula a média das diferenças percentuais absolutas entre as previsões do modelo e os valores reais. O MAPE é útil para interpretar o erro do modelo em termos percentuais, permitindo uma compreensão melhor da precisão do modelo em relação à magnitude das observações.

*RMSE* (Root Mean Squared Error): O RMSE é uma métrica de avaliação comum em modelos de regressão que calcula a raiz quadrada da média dos quadrados das diferenças entre as previsões do modelo e os valores reais. O RMSE fornece uma medida da dispersão dos erros no modelo, onde valores menores indicam uma melhor precisão do modelo. Ele é sensível a grandes erros devido à natureza quadrática do cálculo.

![image](https://github.com/user-attachments/assets/a95011b4-d31e-45ee-8091-bc9d2b9a7dd4)


# 1.2 Time Series Cross-Validation

Cross Validation é uma técnica muito utilizada para avaliação de desempenho de modelos de aprendizado de máquina. O CV consiste em particionar os dados em conjuntos(partes), onde um conjunto é utilizado para treino e outro conjunto é utilizado para teste e avaliação do desempenho do modelo.

![image](https://github.com/user-attachments/assets/20d33226-a156-4bf1-b50c-162607bf872b)


Com esse método de validação, foram obtidas as seguintes performances:

![image](https://github.com/user-attachments/assets/2cdfab23-59d6-4f43-8fd9-b4a4f01d2efd)



# 1.1 Escolha do Modelo

Apesar do modelo de Random Forest Regressor apresentar melhor desempenho, o modelo escolhido para prosseguimento e otimização dos hiperparâmetros (Hyperparameter Fine Tuning) foi o XGBoost Regressor. O processamento do XGBosst foi escolhido, por ser mais rápido e mais simples que a Random Forest, além de verificar que a diferença entre os RMSE dos dois modelos não foi tão relevante.

Performance Final: após a utilização da técnica de Random Forest, na otimização dos Hyperparameter Fine Tuning, o modelo final apresentou as seguintes métricas de erro:

![image](https://github.com/user-attachments/assets/2aaf7f23-737b-4406-98da-7ef0d832443e)



# Hiperparâmetros

Foi empregada a técnica de Bayesian SearchCV para otimizar a busca dos melhores hiperparâmetros. A fim de identificar o parâmetro ideal, optei por utilizar uma amostra referente a um período de 1 ano. Essa escolha permite aumentar o número de iterações em um espaço de tempo reduzido, maximizando a probabilidade de localizar um mínimo global.

![image](https://github.com/user-attachments/assets/d7059dfa-59f3-4de1-974e-dee3d4f2300d)


# Performance do modelo

Ao analisar os dois primeiros gráficos abaixo, é evidente que o modelo é capaz de capturar o comportamento cíclico das vendas, embora apresente alguns períodos com taxas de erro mais elevadas.

Já nos dois últimos gráficos, a distribuição das previsões parece seguir uma distribuição normal. No entanto, é notável que tanto a kurtosis (43.03) quanto a Skewness (2.31) apresentam valores elevados. Além disso, ao examinarmos o quarto gráfico, onde estão plotados os erros, podemos observar que muitas previsões estão fora dos limites do "bigode do boxplot", indicado por uma linha tracejada, e também podemos identificar valores extremos destacados em vermelho.

![image](https://github.com/user-attachments/assets/9aefa6b8-7553-4b04-b12b-b199ed4e0e5d)



# 1.2 Performance por Loja

Como mencionado anteriormente, há lojas com erros muito acima da média, podendo ultrapassar os 60%, conforme evidenciado no primeiro gráfico desta seção. No segundo conjunto de gráficos, observamos que aproximadamente 700 lojas apresentam erros de até 10%, o que é um desempenho excelente para o nosso problema de negócio. Além disso, temos um grupo com pouco mais de 300 lojas, nas quais os erros variam entre 10% e 15%, enquanto as demais lojas apresentam erros superiores a 20%.

![image](https://github.com/user-attachments/assets/2ee0f622-72d2-412f-a35d-8c10250b317d)


![image](https://github.com/user-attachments/assets/b2f5d9fd-4f3b-443c-afd8-3279a5b999ce)


# Final Resultado em R$

Realizando-se a somatória de cada loja, em cada cenário, conseguimos chegar a uma predição de valor para receita final, considerando todas as lojas Rossmann Store:

![image](https://github.com/user-attachments/assets/3105927e-4931-4460-81d6-410d3a6aee98)


# Conclusões

Neste estágio do projeto, podemos tirar algumas conclusões importantes. É evidente que o modelo não apresenta um desempenho uniforme para todas as lojas. Nesse sentido, sugiro ao CCO que priorize um levantamento das 700 lojas que demonstraram bom desempenho até o momento.

Para o próximo passo, nossa recomendação é que concentremos nossa análise nas demais lojas. Isso nos permitirá alcançar resultados mais adequados para prever as vendas das próximas semanas. A partir dessas informações sólidas, o CcO poderá tomar decisões embasadas para elaborar os orçamentos.

Essa abordagem direcionada nos permitirá otimizar nossos recursos e concentrar nossos esforços onde têm maior probabilidade de impacto positivo.

# Ferramentas Utilizados

Ferramentas: Hadoop, R, SQL, Python, XGBoost Regressor , Random Forest Regressor , Linear Regression , Linear Regression Regularized , Linear Regression , Average Model, Excel , Power BI , Power Point , Oracle , SQL Server , Colab e Jupyter Notebook

# Proximos Passos

Em projetos seguintes, além do que já foi feito, podem ser incrementados:

Testar outros algoritmos de Machine Learning

Trabalhar com outras features em outros ciclos do CRISP

Utilizar outra estratégia para Fine Tuning Hyperparameter

Criar outras opções de comunicação no chat do Bot Telegram


