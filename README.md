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

### 1. Coleta de Dados

Coletaremos dados sobre o status dos voos e as condições climáticas correspondentes durante um período de 30 dias, a partir de 7 de abril de 2024.

### 2. Pré-processamento dos Dados

- Definição de tipos
- Tratamento de dados ausentes
- Normalização e discretização
- Limpeza de dados (univariado, bivariado e multivariado)

### 3. Estatísticas Descritivas

Apresentaremos estatísticas descritivas dos dados coletados, incluindo visualizações para melhor compreensão.

### 4. Teste de Hipóteses

Realizaremos testes de hipóteses para comparar valores de categorias, como a taxa de cancelamento em diferentes condições climáticas. Visualizaremos as diferenças encontradas.

#### Bônus

- Integração de dados ou extração de dados da Web.
- Utilização de técnicas não cobertas nas aulas.

## Análise

A partir dos dados coletados, realizaremos uma análise para identificar possíveis correlações entre as condições climáticas e o status dos voos (atrasos, cancelamentos, etc.). Essa análise permitirá entender melhor como diferentes variáveis climáticas podem impactar as operações de voo nos principais aeroportos do Brasil.
