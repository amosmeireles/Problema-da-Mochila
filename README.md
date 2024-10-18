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

## Visualização dos Resultados:

Fronteira eficiente: Um gráfico que mostra o equilíbrio entre retorno e risco.

Distribuição de Ativos: Gráfico de pizza ou barras para ilustrar a alocação dos ativos.

Evolução do Retorno e Risco: Gráficos que mostram a evolução dos retornos e do risco ao longo do tempo.

## Instruções de Instalação e Execução
Este projeto foi desenvolvido utilizando o Google Colab, uma plataforma online gratuita que permite a execução de código Python em notebooks de forma interativa. Abaixo estão os passos detalhados para abrir e executar o código:

Passos para Acessar o Projeto:

1. Acesse o Repositório no GitHub:
No GitHub, navegue até a pasta que contém o arquivo Problema_da_mochila.ipynb.
Esse arquivo contém todo o código necessário para realizar a otimização da carteira de investimentos utilizando a formulação do problema da mochila.

2. Abrir o Arquivo no Google Colab:
Dentro da pasta do repositório, clique no arquivo Problema_da_mochila.ipynb.
No canto superior direito da tela do GitHub, você verá um botão com a opção "Abrir no Colab" (ou "Open in Colab"). Clique nesse botão. Se a opção não aparecer, use o link direto: Google Colab.

3. Executar o Código no Google Colab:
Após o notebook ser aberto no Google Colab, você poderá ver todo o código e as células que precisam ser executadas.
No Google Colab, execute cada célula do notebook, começando pela primeira (clicando no ícone de "play" à esquerda de cada célula) ou use a opção Executar tudo (Run All) no menu superior para rodar todas as células de uma vez.

4. Instalação de Bibliotecas:
O Google Colab já possui muitas bibliotecas pré-instaladas, mas se for necessário instalar bibliotecas adicionais (como yfinance), isso será feito automaticamente pelo código quando você rodar o notebook.

5. Visualização dos Resultados:
Após a execução, você verá os gráficos e resultados diretamente no notebook, incluindo os pesos ótimos da carteira de investimentos, que são proporcionais ao risco de cada ativo, e as visualizações correspondentes.

## Requisitos
Google Account: Para acessar e executar o notebook no Google Colab, você precisará de uma conta do Google.

Conexão com a Internet: O Google Colab roda online, então é necessário estar conectado à internet.

Bibliotecas Necessárias: O código instala automaticamente as bibliotecas necessárias, como numpy, pandas, scipy, matplotlib, seaborn e yfinance.

## Personalização e Alteração
Se desejar realizar alterações no código ou ajustar parâmetros, como a lista de ativos financeiros ou o limite de risco, basta editar as células relevantes no notebook diretamente no Google Colab. Em seguida, execute novamente as células para ver os resultados atualizados.

##Dicas
Salvar uma Cópia: Para salvar uma cópia do notebook com suas alterações, vá em Arquivo > Salvar uma cópia no Drive, assim você poderá manter suas mudanças no seu próprio Google Drive.

Download do Notebook: Você também pode baixar o notebook como um arquivo .ipynb para rodá-lo localmente, caso tenha um ambiente Python configurado em sua máquina.
