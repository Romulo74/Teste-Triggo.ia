# Teste-Triggo.ia

## Descrição do Projeto

Este repositório contém o notebook Jupyter desenvolvido para o Teste Técnico do Programa Trainee triggo.ai de Excelência em Engenharia de Dados e DataOps 2025. O projeto consiste em uma análise abrangente do "Brazilian E-commerce Public Dataset by Olist", com o objetivo de extrair insights valiosos sobre o comportamento dos clientes, desempenho de vendas, logística de entrega, previsão de atrasos e satisfação do cliente. A análise foi realizada utilizando Python com as bibliotecas pandas, numpy, matplotlib e seaborn.

## Estrutura do Notebook

O notebook está organizado nas seguintes seções principais:

1.  **Preparação dos Dados:** Importação dos arquivos CSV, tratamento de valores nulos, remoção de duplicatas, correção de tipos de dados e criação de um modelo relacional através da junção das tabelas relevantes. **Em alguns casos, o SQLite foi utilizado através do Python para realizar consultas específicas nos DataFrames.**
2.  **Análise Exploratória de Dados (AED):** Investigação de perguntas chave como o volume de pedidos por mês e a existência de sazonalidade, a distribuição do tempo de entrega, a relação entre o valor do frete e a distância, as categorias de produtos mais vendidas por faturamento e os estados com maior valor médio de pedido. **Tanto Python (com pandas) quanto consultas SQL (via SQLite) foram utilizados nesta seção.**
3.  **Solução de Problemas de Negócio:** Abordagem de desafios específicos como o cálculo da taxa de clientes recorrentes, a criação de um modelo de previsão de atrasos na entrega e uma análise inicial da satisfação do cliente em relação ao tempo de entrega. A segmentação de clientes foi iniciada.
4.  **Visualização e Dashboards:** Criação de visualizações para ilustrar os insights da análise exploratória e o desempenho dos modelos, incluindo um dashboard geral de vendas, um mapa de calor da concentração de vendas, gráficos da relação entre avaliação e tempo de entrega e um dashboard de análise dos vendedores.

## Decisões Técnicas

* A biblioteca pandas foi extensivamente utilizada para manipulação e análise dos dados devido à sua flexibilidade e poder para trabalhar com DataFrames. **Para algumas consultas e agregações específicas, o SQLite foi integrado ao Python para realizar operações SQL diretamente nos DataFrames, demonstrando o uso de SQL no projeto.**
* Para visualizações, foram utilizadas as bibliotecas matplotlib e seaborn, escolhidas por sua capacidade de gerar gráficos informativos e personalizáveis.
* O modelo de Regressão Logística foi selecionado para a predição de atrasos devido à sua interpretabilidade e eficiência como um classificador linear para problemas binários.
* A técnica de K-Means foi escolhida para a segmentação de clientes por ser um algoritmo de clustering amplamente utilizado e eficiente.
* A biblioteca numpy foi utilizada para operações numéricas eficientes.
* A biblioteca geopandas foi utilizada para a criação do mapa de calor da concentração de vendas.
* A biblioteca geopy foi utilizada para o cálculo da distância geodésica entre vendedores e clientes.
## Principais Insights da Análise Exploratória de Dados

* **Sazonalidade:** Foi observada uma certa sazonalidade nas vendas ao longo do ano, com alguns meses apresentando um volume de pedidos maior que outros. A análise da evolução anual também indica tendências de crescimento.
* **Distribuição do Tempo de Entrega:** O tempo de entrega dos pedidos apresenta uma distribuição com uma mediana específica, variabilidade considerável e alguns outliers, indicando entregas tanto rápidas quanto lentas.
* **Relação Frete-Distância:** Há uma correlação positiva entre o valor do frete e a distância de entrega, sugerindo que o custo do frete tende a aumentar com a distância entre o vendedor e o cliente.
* **Categorias Mais Vendidas:** As categorias de produtos com maior faturamento foram identificadas, permitindo focar em produtos de alto desempenho.
* **Valor Médio por Estado:** Alguns estados brasileiros se destacam por possuírem um valor médio de pedido mais elevado.

## Solução de Problemas de Negócio

### Análise de Retenção

A taxa de clientes recorrentes foi calculada em [**Inserir a taxa de recorrência que você obteve**]%, indicando a proporção de clientes que realizaram mais de um pedido no período analisado. Este insight é crucial para avaliar a lealdade do cliente e a eficácia das estratégias de retenção.

### Predição de Atraso

Um modelo de Regressão Logística foi implementado para prever se um pedido será entregue com atraso, utilizando features como o tempo estimado de entrega, tempo de aprovação, dia e mês da compra, número de itens e valor do frete. O modelo alcançou uma performance de [**Inserir as métricas de avaliação do modelo, como acurácia, precisão, recall, F1-score e AUC-ROC**], demonstrando uma capacidade razoável de identificar pedidos com potencial atraso.

### Segmentação de Clientes

A segmentação de clientes utilizando a técnica de K-Means foi iniciada, com base em variáveis como número de pedidos, valor total gasto e frequência de compra. A análise dos perfis dos clusters identificados permitirá a criação de estratégias de marketing mais direcionadas. [**Se você tiver resultados parciais ou ideias de estratégias, pode incluí-las aqui.**]

### Análise de Satisfação

Uma análise inicial explorou a relação entre a nota de avaliação dos clientes e o tempo de entrega real dos pedidos. Os resultados sugerem [**Inserir suas observações sobre a relação entre avaliação e tempo de entrega**], indicando uma possível influência do tempo de entrega na satisfação do cliente.

## Visualização e Dashboards

### Dashboard Geral de Vendas

Este dashboard apresenta a evolução do volume de pedidos ao longo do tempo, permitindo visualizar tendências e sazonalidade. Também exibe as categorias de produtos com maior faturamento, fornecendo uma visão do desempenho das diferentes linhas de produto.

### Mapa de Calor da Concentração de Vendas

O mapa de calor ilustra a distribuição geográfica das vendas por estado brasileiro, evidenciando as regiões com maior volume de pedidos.

### Relação entre Avaliação e Tempo de Entrega

Gráficos de dispersão e boxplots foram criados para visualizar a relação entre a nota de avaliação dos clientes e o tempo de entrega dos pedidos, buscando identificar padrões que possam indicar o impacto do tempo de entrega na satisfação.

### Dashboard de Análise dos Vendedores

Este dashboard exibe o desempenho dos vendedores em termos de faturamento total e tempo médio de envio, permitindo identificar os vendedores com melhor desempenho nessas métricas.

## Como Executar o Projeto

Para executar o código e visualizar as análises, é necessário ter o Python instalado em seu ambiente, juntamente com as seguintes bibliotecas:

* pandas
* SQLite
* numpy
* matplotlib
* seaborn
* geopandas (para o mapa de calor, caso tenha sido utilizado)
* scikit-learn (para o modelo de predição e segmentação)
* geopy (para cálculo de distância, caso tenha sido utilizado)

Certifique-se de que o notebook Jupyter (`.ipynb`) esteja no mesmo diretório que os arquivos CSV do dataset original (ou que os caminhos para os arquivos no código estejam corretos). O notebook pode ser executado em um ambiente Jupyter Notebook ou Google Colab.

## Decisões Técnicas

* A biblioteca pandas foi extensivamente utilizada para manipulação e análise dos dados devido à sua flexibilidade e poder para trabalhar com DataFrames.
* Para visualizações, foram utilizadas as bibliotecas matplotlib e seaborn, escolhidas por sua capacidade de gerar gráficos informativos e personalizáveis.
* O modelo de Regressão Logística foi selecionado para a predição de atrasos devido à sua interpretabilidade e eficiência como um classificador linear para problemas binários.
* A técnica de K-Means foi escolhida para a segmentação de clientes por ser um algoritmo de clustering amplamente utilizado e eficiente.

## Autor

Romulo Augusto Vieira

## Link para o Dataset

[https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)
