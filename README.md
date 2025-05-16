# Teste-Triggo.ia

## Descrição do Projeto

Este repositório contém o notebook Jupyter desenvolvido para o Teste Técnico do Programa Trainee triggo.ai de Excelência em Engenharia de Dados e DataOps 2025. O projeto consiste em uma análise abrangente do "Brazilian E-commerce Public Dataset by Olist", com o objetivo de extrair insights valiosos sobre o comportamento dos clientes, desempenho de vendas, logística de entrega, previsão de atrasos e satisfação do cliente. A análise foi realizada utilizando Python com as bibliotecas pandas, numpy, matplotlib, seaborn, geopandas e scikit-learn, além de consultas SQL via SQLite integrado ao Python.

## Estrutura do Notebook

O notebook está organizado nas seguintes seções principais:

1.  **Preparação dos Dados:** Importação dos arquivos CSV, tratamento de valores nulos (inexistentes nos DataFrames principais), remoção de duplicatas, correção de tipos de dados e criação de um modelo relacional através da junção das tabelas relevantes. Em alguns casos, o SQLite foi utilizado através do Python para realizar consultas específicas nos DataFrames.
2.  **Análise Exploratória de Dados (AED):** Investigação de perguntas chave como o volume de pedidos por mês e a existência de sazonalidade (identificada), a distribuição do tempo de entrega (média de 11.64 dias), a relação positiva moderada entre o valor do frete e a distância (correlação de 0.3894), as categorias de produtos mais vendidas por faturamento (beleza\_saude, relogios\_presentes, cama\_mesa\_banho, esporte\_lazer, informatica\_acessorios no top 5) e os estados com maior valor médio de pedido (PB, AL, AC, RO, PA no top 5). Tanto Python (com pandas) quanto consultas SQL (via SQLite) foram utilizados nesta seção.
3.  **Solução de Problemas de Negócio:** Abordagem de desafios específicos como o cálculo da taxa de clientes recorrentes, a criação de um modelo de previsão de atrasos na entrega e uma análise inicial da satisfação do cliente em relação ao tempo de entrega. A segmentação de clientes foi iniciada.
4.  **Visualização e Dashboards:** Criação de visualizações para ilustrar os insights da análise exploratória e o desempenho dos modelos, incluindo um dashboard geral de vendas, tentativa de criação de um mapa de calor da concentração de vendas (com um problema de arquivo), gráficos da relação entre avaliação e tempo de entrega e um dashboard de análise dos vendedores (faturamento e tempo de envio).

## Principais Insights da Análise Exploratória de Dados

* **Sazonalidade:** O volume de pedidos apresenta variações ao longo dos meses, com um pico notável em novembro.
* **Tempo de Entrega:** O tempo médio de entrega é de aproximadamente 11.64 dias, com variações significativas entre estados (SP com a menor média, RR com a maior) e categorias de produtos (artes\_e\_artesanato com a menor média, moveis\_escritorio com a maior).
* **Frete e Distância:** Há uma correlação positiva moderada (0.3894) entre o valor do frete e a distância de entrega.
* **Categorias de Produtos:** As categorias de "beleza\_saude" e "relogios\_presentes" lideram em faturamento.
* **Valor Médio por Estado:** Estados como Paraíba (PB) e Alagoas (AL) possuem um valor médio de pedido mais elevado.

## Solução de Problemas de Negócio

### Análise de Retenção

A taxa de clientes recorrentes (que fizeram mais de um pedido).

### Predição de Atraso

Um modelo de Regressão Logística foi implementado para prever se um pedido seria entregue com atraso. As métricas de avaliação no conjunto de teste foram: Acurácia: 0.92, Precisão (classe 0): 0.92, Precisão (classe 1): 0.33, Recall (classe 0): 1.00, Recall (classe 1): 0.00, F1-score (classe 0): 0.96, F1-score (classe 1): 0.00 e AUC-ROC: 0.5877. O modelo demonstra uma boa acurácia geral, mas tem dificuldades em identificar corretamente os pedidos que serão entregues com atraso (baixas precisão e recall para a classe 1).

### Segmentação de Clientes

A análise de segmentação de clientes utilizando K-Means foi iniciada, buscando identificar grupos de clientes com padrões de compra semelhantes. A análise preliminar sugere a possibilidade de identificar grupos com diferentes características em termos de frequência de compra e valor gasto. Uma análise mais aprofundada é necessária para caracterizar esses segmentos e propor estratégias.

### Análise de Satisfação

A análise exploratória sugere uma relação entre o tempo de entrega e a avaliação do cliente, com tempos de entrega mais longos tendendo a receber avaliações mais baixas.

## Visualização e Dashboards

### Dashboard Geral de Vendas

Apresenta a evolução do volume de pedidos ao longo do tempo e o faturamento por categoria de produto.

### Mapa de Calor da Concentração de Vendas

Tentativa de visualização da concentração de vendas por estado, mas houve um problema com o arquivo `brasil_estados.shp`.

### Relação entre Avaliação e Tempo de Entrega

Gráficos de dispersão e boxplots foram utilizados para explorar a relação entre a nota de avaliação do cliente e o tempo de entrega.

### Dashboard de Análise dos Vendedores

Exibe o desempenho dos vendedores em termos de faturamento total e tempo médio de envio, identificando os melhores desempenhos em cada métrica.

## Como Executar o Projeto

Para executar o código e visualizar as análises, é necessário ter o Python instalado em seu ambiente, juntamente com as seguintes bibliotecas:

* pandas
* numpy
* matplotlib
* seaborn
* geopandas (para o mapa de calor - pode ser necessário instalar e garantir que o arquivo `brasil_estados.shp` esteja na pasta `data`)
* scikit-learn
* sqlite3

Certifique-se de que o notebook Jupyter (`.ipynb`) esteja no mesmo diretório que os arquivos CSV do dataset original (ou que os caminhos para os arquivos no código estejam corretos). O notebook pode ser executado em um ambiente Jupyter Notebook ou Google Colab.

## Decisões Técnicas

* A biblioteca pandas foi extensivamente utilizada para manipulação e análise dos dados. Para algumas consultas e agregações específicas, o SQLite foi integrado ao Python para realizar operações SQL diretamente nos DataFrames.
* As bibliotecas matplotlib e seaborn foram utilizadas para a criação de visualizações.
* O modelo de Regressão Logística foi escolhido para a predição de atrasos.
* A técnica de K-Means foi utilizada para a segmentação de clientes.
* A biblioteca geopandas foi utilizada para a tentativa de criação do mapa de calor.
* A biblioteca numpy foi utilizada para operações numéricas.

## Limitações e Possíveis Melhorias

Durante a realização deste projeto, algumas limitações foram encontradas, e certos aspectos não foram explorados em profundidade devido a restrições de tempo ou à disponibilidade de dados:

* **Segmentação de Clientes:** A análise de segmentação de clientes foi iniciada utilizando o algoritmo K-Means, mas não foi possível realizar uma análise completa dos perfis dos clusters e propor estratégias de marketing detalhadas para cada segmento. Uma análise mais aprofundada incluiria a escolha otimizada do número de clusters (utilizando métodos como o Elbow Method ou Silhouette Analysis), a visualização dos clusters em um espaço dimensional reduzido (usando PCA ou t-SNE) e a caracterização detalhada de cada segmento em termos de comportamento de compra, dados demográficos (se disponíveis) e outras informações relevantes.

* **Predição de Atraso:** O modelo de Regressão Logística implementado para a predição de atrasos apresentou limitações na capacidade de identificar corretamente os pedidos que seriam entregues com atraso (baixa precisão e recall para a classe positiva). Melhorias nesse modelo poderiam incluir:
    * A engenharia de novas *features* que capturem melhor a complexidade do problema de atrasos na entrega.
    * A experimentação com outros algoritmos de classificação (Random Forest, Gradient Boosting, etc.).
    * A otimização dos hiperparâmetros do modelo para melhorar seu desempenho.
    * A coleta de mais dados relevantes para o problema, se possível.

* **Análise de Satisfação:** A análise da satisfação do cliente se concentrou principalmente na relação com o tempo de entrega. Outros fatores que poderiam influenciar a satisfação, como preço, categoria do produto, qualidade do produto, atendimento ao cliente e experiência de compra, não foram explorados em profundidade devido à falta de dados abrangentes sobre esses aspectos.

* **Mapa de Calor:** A geração do mapa de calor da concentração de vendas por estado foi prejudicada pela ausência do arquivo shapefile (`brasil_estados.shp`) no diretório especificado. A inclusão desse mapa enriqueceria a visualização da distribuição geográfica das vendas.

* **Análise Temporal Detalhada:** A análise da sazonalidade e das tendências de vendas poderia ser aprimorada com uma análise de séries temporais mais avançada, utilizando métodos como decomposição de séries temporais, modelos ARIMA ou Prophet, para prever as vendas futuras com maior precisão.

Essas limitações representam oportunidades para trabalhos futuros e indicam áreas onde o projeto poderia ser expandido e aprimorado com mais tempo e recursos.

## Autor

Romulo Augusto Vieira.

## Link para o Dataset

[https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)
