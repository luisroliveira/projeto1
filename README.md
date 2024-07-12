# Projeto de Ciência de Dados

## Análise do Impacto das Condições Climáticas na Partida dos Voos

### Professor: Luciano Barbosa

### 2024.1

---

### Grupo

* Camila Barbosa Vieira (cbv2)
* Luis Felipe Rodrigues de Oliveira (lfro2)

---

## Objetivo

O objetivo deste trabalho é analisar como as condições climáticas afetam a partida ou não dos voos nos dez maiores aeroportos do Brasil. Para isso, coletaremos dados sobre o status dos voos e as condições climáticas correspondentes durante um período de 30 dias, a partir de 7 de abril de 2024.

## Coleta de Dados

### Dados dos Voos

Utilizaremos o site Avionio (www.avionio.com) para coletar informações sobre os voos, incluindo:

* Horário (Time)
* Data (Date)
* Código IATA do aeroporto (IATA)
* Destino (Destination)
* Número do voo (Flight)
* Companhia aérea (Airline)
* Status do voo (Status)
* Origem (Origin)

A coleta será feita por meio de um web crawler utilizando a biblioteca BeautifulSoup, que permitirá extrair essas informações das classes HTML correspondentes.

### Dados Climáticos

Os dados climáticos serão obtidos por meio da API da Open-Meteo (https://api.open-meteo.com/v1/forecast). As variáveis climáticas a serem coletadas incluem:

* Temperatura a 2 metros (temperature_2m)
* Umidade relativa a 2 metros (relative_humidity_2m)
* Ponto de orvalho a 2 metros (dew_point_2m)
* Temperatura aparente (apparent_temperature)
* Probabilidade de precipitação (precipitation_probability)
* Precipitação (precipitation)
* Chuva (rain)
* Pancadas de chuva (showers)
* Queda de neve (snowfall)
* Pressão ao nível do mar (pressure_msl)
* Cobertura de nuvens (cloud_cover)
* Visibilidade (visibility)
* Velocidade do vento a 10 metros (wind_speed_10m)
* Direção do vento a 10 metros (wind_direction_10m)
* Rajadas de vento a 10 metros (wind_gusts_10m)

## Passos do Projeto

### Parte 1

#### 1. Coleta de Dados

Coletaremos dados sobre o status dos voos e as condições climáticas correspondentes durante um período de 30 dias, a partir de 7 de abril de 2024.

#### 2. Pré-processamento dos Dados

- Definição de tipos
- Tratamento de dados ausentes
- Normalização e discretização
- Limpeza de dados (univariado, bivariado e multivariado)

#### 3. Estatísticas Descritivas

Apresentaremos estatísticas descritivas dos dados coletados, incluindo visualizações para melhor compreensão.

#### 4. Teste de Hipóteses

Realizaremos testes de hipóteses para comparar valores de categorias, como a taxa de cancelamento em diferentes condições climáticas. Visualizaremos as diferenças encontradas.

#### Bônus

- Integração de dados ou extração de dados da Web.
- Utilização de técnicas não cobertas nas aulas.

### Parte 2

#### 1. Definir a coluna alvo

Transformaremos o problema em uma tarefa de classificação, utilizando a coluna 'Status' como alvo. Esta coluna será binarizada para indicar se o voo ocorreu sem problemas ('Voos sem Problemas') ou se foi atrasado ou cancelado ('Atrasado ou Cancelado'). O objetivo é estabelecer uma relação entre as condições climáticas na origem e no destino com a variável alvo.

#### 2. Separar os dados em treinamento, validação e teste

Os dados serão divididos de forma estratificada em três conjuntos:

- 70% para treinamento
- 15% para validação
- 15% para teste
  
Em seguida, aplicaremos técnicas de balanceamento por oversampling nos conjuntos de treinamento e validação para lidar com qualquer desequilíbrio na variável alvo.

#### 3. Selecionar 4 algoritmos

Selecionamos quatro algoritmos de aprendizado de máquina disponíveis na biblioteca scikit-learn para a tarefa de classificação:

- Logistic Regression
- Decision Tree
- Random Forest
- Gradient Boosting

#### 4. Adicionar MLFlow no treinamento dos modelos para rastreamento

Implementaremos o MLFlow para rastrear e registrar todos os experimentos. Isso inclui:

- Registro dos hiperparâmetros utilizados em cada experimento
- Armazenamento dos modelos treinados
- Registro das métricas de avaliação
- Salvamento dos resultados na pasta mlruns para consulta futura

#### 5.  Executar uma ferramenta de seleção de hiper-parâmetros

Utilizaremos a biblioteca Optuna para a otimização de hiperparâmetros, garantindo a escolha dos melhores valores para cada algoritmo. O processo será realizado da seguinte forma:

- Selecionar poucos hiperparâmetros por algortimo (max. 3)
- Selecionar o modelo com melhor resultado na métrica de avaliação
- Executar o melhor modelo de cada algoritmo no conjunto de teste

#### 6. Realizar diagnóstico do melhor modelo geral e melhorá-lo

Após a seleção do melhor modelo, realizaremos um diagnóstico detalhado utilizando técnicas de interpretação de modelo como SHAP e LIME. Essas técnicas nos permitirão entender melhor as influências das variáveis climáticas nas previsões do modelo. A partir dessa análise, faremos ajustes adicionais para melhorar o desempenho do modelo.

#### Bônus
- Utilizar auto-sklearn: Implementação do auto-sklearn para automatizar o processo de seleção de modelos e ajuste de hiperparâmetros.
- Clustering para entendimento dos dados: Aplicação de técnicas de clustering para identificar padrões nos dados que possam fornecer insights adicionais sobre as condições climáticas e seu impacto nos voos.

## Análise

A partir dos dados coletados, realizaremos uma análise abrangente para identificar possíveis correlações entre as condições climáticas e o status dos voos (atrasos, cancelamentos, etc.). Esta análise permitirá entender melhor como diferentes variáveis climáticas impactam as operações de voo nos principais aeroportos do Brasil. Isso fornecerá insights valiosos para as companhias aéreas e autoridades aeroportuárias na tomada de decisões informadas para melhorar a pontualidade e a segurança dos voos.
