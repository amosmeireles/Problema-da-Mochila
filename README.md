# Materia: Otimização de sistemas
# Codigo da turma: 962-94349
# Nome: Amós Meireles Diniz, Matricula: 2021101198
# Objetivo do Trabalho
  Este projeto tem como objetivo implementar um algoritmo de otimização para construção de uma carteira de investimentos baseado no problema da mochila. O objetivo principal é maximizar o retorno esperado de uma    carteira de ativos financeiros, respeitando um limite de risco aceitável (equivalente à capacidade da mochila).
  A otimização utiliza a volatilidade como modelo de medição de risco de forma a selecionar os melhores ativos que otimizam a relação risco-retorno.
  
# Abordagem Utilizada para a Otimização
A otimização foi implementada em três etapas:

Modelagem Matemática:

## Ativos Financeiros: Os ativos são modelados como itens no problema da mochila, onde o retorno esperado é análogo ao valor e o risco ao peso.
Capacidade da Mochila: Define o limite máximo de risco tolerado na carteira.
Objetivo: Maximizar o retorno total da carteira, garantindo que o risco (volatilidade ou VaR/CVaR) permaneça dentro de um limite estabelecido.
Implementação em Python:

## Bibliotecas utilizadas:
numpy e pandas: Manipulação de dados financeiros.
scipy.optimize: Resolver o problema de otimização.
matplotlib e seaborn: Visualização dos resultados.
yfinance: Coleta de dados financeiros de ativos via API do Yahoo Finanças.
Visualização dos Resultados:

## Fronteira eficiente: Um gráfico que mostra o equilíbrio entre retorno e risco.
Distribuição de Ativos: Gráfico de pizza ou barras para ilustrar a alocação dos ativos.
Evolução do Retorno e Risco: Gráficos que mostram a evolução dos retornos e do risco ao longo do tempo.
