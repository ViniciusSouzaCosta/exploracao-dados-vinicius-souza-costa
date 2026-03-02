Análise Exploratória: Renúncias Fiscais de Importação (II e IPI)

Este documento apresenta a análise exploratória e estatística do conjunto de dados público de Renúncia Fiscal referente ao Imposto de Importação (II) e ao Imposto sobre Produtos Industrializados (IPI), disponibilizado pelo Governo Federal brasileiro.

Sobre o Conjunto de Dados

Os dados foram extraídos do portal de Dados Abertos do governo brasileiro e são mantidos pela Secretaria da Receita Federal do Brasil. O ficheiro detalha as importações que receberam benefícios fiscais, tais como isenção, suspensão ou redução de impostos. O objetivo desta análise é compreender o comportamento dos dados, a distribuição dos montantes que deixaram de ser arrecadados pelo Estado e identificar possíveis anomalias ou padrões.

O conjunto de dados possui 109.678 linhas de registos e 8 colunas de variáveis, incluindo CNPJ, Razão Social, Regime Tributário, Ano de Desembaraço e os valores de renúncia em Reais.

Tecnologias Utilizadas

A análise foi desenvolvida em Python, utilizando as bibliotecas pandas para manipulação e análise tabular, numpy para cálculos matemáticos avançados, bem como matplotlib e seaborn para a geração de gráficos.

O Que Foi Feito neste Projeto

O fluxo de trabalho foi dividido nas seguintes etapas:

Limpeza e Tratamento de Dados
Os valores financeiros vieram originalmente em formato de texto. Foi criada uma função de limpeza para remover pontos de separação de milhares, substituir vírgulas por pontos e tratar dados vazios, convertendo-os para o formato numérico correto.

Análise Estatística Descritiva
Foram calculadas métricas estatísticas essenciais para compreender a distribuição do dinheiro nos dois impostos, incluindo média, desvio padrão, mínimo, máximo e quartis. Também foram realizados cálculos manuais complementares para a moda, variância e intervalo interquartil. A exibição dos dados foi formatada para facilitar a leitura humana, removendo a notação científica e padronizando as casas decimais.

Visualização de Dados
Devido à extrema assimetria dos dados, onde algumas poucas empresas recebem milhares de milhões em isenções enquanto a maioria recebe valores muito menores, aplicou-se uma transformação logarítmica combinada com um filtro limitador para lidar com valores negativos e permitir uma visualização gráfica coerente. Foram gerados histogramas para observar a distribuição da frequência dos valores, boxplots para visualizar a dispersão e identificar a forte presença de valores atípicos na cauda superior, e gráficos de dispersão para analisar a correlação entre os benefícios concedidos numa mesma operação.

Principais Conclusões

Primeiro, observou-se uma alta concentração de capital. A média de renúncia do Imposto de Importação é muito superior à mediana. Isto comprova que a maior parte das empresas tem benefícios de pequeno porte, mas poucas operações gigantescas distorcem a média para cima, com o valor máximo a chegar a mais de 4 mil milhões de Reais.

Segundo, a moda observada foi zero. O valor que mais se repete em ambas as colunas financeiras é zero Reais, indicando que é comum uma operação receber isenção de apenas um dos impostos.

Por fim, a análise revelou a presença de anomalias, como valores negativos no conjunto de dados original, o que sugere possíveis ajustes contabilísticos, devoluções ou erros de sistema da Receita Federal.
