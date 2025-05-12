# Análise de Atraso de Pagamentos de Locação de Imóveis

## Objetivo

Este repositório contém um notebook do Google Colab para análise de atrasos nos pagamentos de locação de imóveis. A análise inclui a normalização de dados, tratamento de valores faltantes e cálculo de métricas como dias de atraso e status dos pagamentos. O objetivo principal é identificar padrões de atrasos nos pagamentos e visualizar as estatísticas relacionadas.

## Dependências
Este projeto utiliza as seguintes bibliotecas Python para análise de dados e visualizações:

pandas: Manipulação e análise de dados.

matplotlib: Geração de gráficos.

seaborn: Visualizações avançadas e personalizadas.

## Arquivos
* dados_locacao_imoveis.json: Arquivo JSON contendo os dados de locação dos imóveis, incluindo informações sobre as datas de pagamento acordadas e efetivadas.

* analise_atrasos_locacao.ipynb: Notebook do Google Colab com a análise dos dados de locação, incluindo visualizações dos atrasos e status de pagamento.

## Base de Dados
```bash
https://cdn3.gnarususercontent.com.br/2928-transformacao-manipulacao-dados/dados_locacao_imoveis.json
```

## Descrição do Notebook

### 1. Carregamento e Normalização dos Dados
   
O primeiro passo no notebook é carregar o arquivo JSON e normalizar os dados para facilitar a análise. A normalização é feita utilizando a função json_normalize da biblioteca pandas, que transforma a estrutura de dados aninhada em um formato tabular

```bash
dados = pd.read_json('/content/dados_locacao_imoveis.json')
dados_normalizados = pd.json_normalize(dados['dados_locacao'])
```

### 2. Extração e Tratamento das Datas de Pagamento
O código realiza a extração das datas de pagamento acordadas e efetivadas, além de tratar valores faltantes na coluna de pagamento efetivado.

```bash
dados_normalizados['data_acordada_pagamento'] = ...
dados_normalizados['data_efetivacao_pagamento'] = ...
```

### 3. Cálculo de Dias de Atraso
Com as datas extraídas, a diferença entre as datas de pagamento acordadas e efetivadas é calculada para determinar os dias de atraso. Também é atribuído um status de pagamento ("Em Dia" ou "Atrasado").

```bash
dados_normalizados['dias_atraso'] = ...
dados_normalizados['status_pagamento'] = ...
```

### 4. Análises Estatísticas e Visualizações

Vários gráficos e análises são realizados para entender o comportamento dos pagamentos, incluindo:

  * Distribuição dos Dias de Atraso: Exibido por meio de um histograma com a densidade da distribuição.

  * Status de Pagamento: Gráfico de barras mostrando a quantidade de pagamentos "Em Dia" e "Atrasado".

  * Top 5 Apartamentos com Mais Atrasos: Identificação dos apartamentos que mais apresentaram atrasos.

  * Média de Dias de Atraso por Apartamento: Análise da média de dias de atraso para os apartamentos.

### 5. Conclusões
 
O notebook termina com a exibição das colunas do dataset para uma revisão final e análise dos dados. A visualização de gráficos ajuda a identificar padrões e a tomar decisões baseadas nos dados.

## Como Rodar o Projeto

1. Faça o clone deste repositório em seu ambiente local:

```bash
git clone https://github.com/seu-usuario/seu-repositorio.git
```
2. Abra o arquivo analise_atrasos_locacao.ipynb no Google Colab.

3. Execute o notebook célula por célula para realizar a análise dos atrasos nos pagamentos de locação de imóveis.

## Resultados Esperados
Estatísticas sobre os atrasos nos pagamentos.

  * Visualizações da distribuição dos dias de atraso.

  * Análise dos apartamentos com maiores atrasos.

  * Identificação de padrões de pagamentos atrasados que podem ser utilizados para otimizar o processo de cobrança ou gestão de locação.

## Contribuições
Contribuições são bem-vindas! Se você deseja melhorar este projeto, sinta-se à vontade para fazer um fork e enviar um pull request.

## Licença
Este projeto está licenciado sob a Licença MIT.

