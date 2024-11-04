# Materia: Otimização de sistemas
# Codigo da turma: 962-94349
# Nome: Amós Meireles Diniz, Matricula: 2021101198
# Objetivo do Trabalho
Este projeto tem como objetivo a implementação de um algoritmo de otimização para a construção de uma carteira de investimentos usando o problema da mochila. O objetivo central é a maximização do retorno esperado de uma carteira de ativos financeiros, dada uma certa aversão ao risco aceitável (que é considerada como a capacidade da mochila). O processo de otimização emprega a volatilidade como medida de risco para escolher os melhores títulos que fornecem o maior trade-off risco-retorno.
  
## Método adotado para o problema considerado

**1. Modelagem Matemática**

**A modelagem consiste nas seguintes etapas:**

**Ativos como itens:** Cada ativo financeiro, ações, fundos mútuos e assim por diante, é tratado como um objeto no problema da mochila. Existem duas características principais do ativo:

**Retorno esperado:** Isso é semelhante ao valor do objeto em um problema de mochila, que é o lucro que o ativo traz para a carteira.

**Risco (Volatilidade):** Isso é semelhante ao peso do objeto. O risco expressa o grau de imprevisibilidade de quanto lucro ou prejuízo esse ativo irá gerar; Nesse caso, isso foi avaliado por fatores externos usando um método chamado volatilidade.

**Capacidade da Mochila (Taxa de Risco):** O limite de risco é caracterizado pelo peso máximo da volatilidade que pode ser tolerado pela carteira de ativos. Isso é semelhante ao problema da mochila clássica carregando a capacidade máxima de peso considerada. Esse limite pode variar dependendo de quanto risco um investidor está disposto a correr.

**Objetivo da Otimização:** O retorno total da carteira de investimentos deve ser maximizado sujeito a uma restrição de risco, que em termos básicos pode ser formulada matematicamente.

![image](https://github.com/user-attachments/assets/b587e2b9-af7f-41f1-83b0-78ca5396c92a)


**2. Dados e Retornos**

Os dados de ativos financeiros são obtidos da API do Yahoo Finance usando a biblioteca yfinance. Esses dados incorporam preços históricos para os ativos selecionados, necessários para calcular os retornos.

**Cálculo dos retornos diários:** Os retornos diários foram determinados calculando a variação percentual no preço dos ativos por dias consecutivos. Isso é obtido usando a função pct_change() da biblioteca pandas, que calcula a variação percentual entre n observações consecutivas de uma série.

**3. Modelagem de Portfólio**

A carteira de investimentos é construída no envelope cônico pela ponderação de seus ativos Wi. Esses pesos, denotando a fração do capital investido, devem somar um (1).

**Retorno esperado da carteira:** O retorno da carteira é estimado como sendo a média ponderada dos retornos diários dos ativos ao longo do período, considerando os pesos atribuídos a cada ativo. Isso é obtido por meio do procedimento de multiplicação de matrizes entre a matriz de retorno e o vetor de alocação de peso.

![image](https://github.com/user-attachments/assets/5ff65ba3-ff69-4758-99f5-c65fc01bfae5)

**Risco (Volatilidade) da Carteira:** O risco de uma carteira é definido em termos de volatilidade anualizada, que é determinada a partir da volatilidade dos retornos diários. A volatilidade é definida como o desvio padrão dos retornos ajustados para a raiz quadrada de 252, que representa o número de dias de negociação em um ano.

![image](https://github.com/user-attachments/assets/c1bee81a-2ad6-44c4-a5c4-494158d3ae62)

**4. Função de Otimização**

O objetivo da otimização do portfólio é encontrar a combinação apropriada de pesos para atingir o máximo retorno esperado possível, sujeito a uma restrição de risco (volatilidade máxima). Para isso, o algoritmo de otimização é realizado usando a função minimize() da biblioteca scipy.optimize. Essa função minimiza o nível de risco de um portfólio em um determinado retorno esperado ou vice-versa.

**Função Objetivo:** A função objetivo pode ser expressa para maximizar o retorno ou minimizar o risco da carteira, tomando o produto dos retornos diários e os pesos alocados para encontrar o retorno esperado e o risco da carteira.

**5. Visualização dos Resultados**
Após a otimização, diferentes gráficos são gerados para permitir uma análise visual clara dos resultados da carteira otimizada:
  
**Fronteira Eficiente:** Um gráfico que mostra a relação entre o retorno esperado e o risco para diferentes combinações de ativos, destacando as carteiras mais eficientes para cada nível de risco.

 **Codigo utilizado para fazer o grafico de Fronteira Eficiente:** 

![image](https://github.com/user-attachments/assets/94582352-af2e-4d21-a8c4-96a503cb2cbf)

 **Resultado do grafico Fronteira Eficiente apresentado pelo codigo funcionando:**

![image](https://github.com/user-attachments/assets/a071408b-1047-4eff-b5e7-7791c9956a80)

**Distribuição de Ativos:** Um gráfico de pizza (ou barras) exibe a proporção alocada em cada ativo, com base nos pesos calculados pelo algoritmo de otimização.

 **Codigo utilizado para fazer o grafico de Distribuição de Ativos:** 

![image](https://github.com/user-attachments/assets/6ffe89ba-a086-4759-82cc-c72ba31df2ef)

  **Resultado do grafico Distribuição de Ativos apresentado pelo codigo funcionando:**

  ![image](https://github.com/user-attachments/assets/68230884-8127-499d-b6b2-4c1c905c4181)

  
**Evolução do Retorno e Risco:** A evolução dos retornos e do risco da carteira é mostrada em um gráfico de linha. Isso inclui:
  
**Retorno Cumulativo:** Calculado com base no crescimento dos retornos da carteira ao longo do tempo.
**Volatilidade Rolante:** A volatilidade (risco) da carteira é calculada para janelas móveis de 21 dias, permitindo observar como o risco varia ao longo do tempo.

 **Codigo utilizado para fazer o grafico de Evolução do Retorno e Risco:** 

![image](https://github.com/user-attachments/assets/b3a1e088-8501-4844-bb51-bb0583cba492)

 **Resultado do grafico Evolução do Retorno e Risco apresentado pelo codigo funcionando:**
 
![image](https://github.com/user-attachments/assets/227f85b4-1664-4146-a12f-8149a06428f3)

## Instruções de Instalação e Execução
Este projeto foi desenvolvido utilizando o Google Colab, uma plataforma online gratuita que permite a execução de código Python em notebooks de forma interativa. Abaixo estão os passos detalhados para abrir  e executar o código:

**Passos para Acessar o Projeto:**

**1. Acesse o Repositório no GitHub:**
No GitHub, navegue até a pasta que contém o arquivo Problema_da_mochila.ipynb.
Esse arquivo contém todo o código necessário para realizar a otimização da carteira de investimentos utilizando a formulação do problema da mochila.
  
**2. Abrir o Arquivo no Google Colab:**
Dentro da pasta do repositório, clique no arquivo Problema_da_mochila.ipynb.
No canto superior direito da tela do GitHub, você verá um botão com a opção "Abrir no Colab" (ou "Open in Colab"). Clique nesse botão. Se a opção não aparecer, use o link direto: Google Colab.
  
**3. Executar o Código no Google Colab:**
Após o notebook ser aberto no Google Colab, você poderá ver todo o código e as células que precisam ser executadas.
No Google Colab, execute cada célula do notebook, começando pela primeira (clicando no ícone de "play" à esquerda de cada célula) ou use a opção Executar tudo (Run All) no menu superior para rodar todas as   células de uma vez.
  
**4. Instalação de Bibliotecas:**
O Google Colab já possui muitas bibliotecas pré-instaladas, mas se for necessário instalar bibliotecas adicionais (como yfinance), isso será feito automaticamente pelo código quando você rodar o notebook.
  
**5. Visualização dos Resultados:**
Após a execução, você verá os gráficos e resultados diretamente no notebook, incluindo os pesos ótimos da carteira de investimentos, que são proporcionais ao risco de cada ativo, e as visualizações           correspondentes.
  
## Requisitos
**Google Account:** Para acessar e executar o notebook no Google Colab, você precisará de uma conta do Google.
  
**Conexão com a Internet:** O Google Colab roda online, então é necessário estar conectado à internet.
  
**Bibliotecas Necessárias:** O código instala automaticamente as bibliotecas necessárias, como numpy, pandas, scipy, matplotlib, seaborn e yfinance.
  
## Personalização e Alteração
Se desejar realizar alterações no código ou ajustar parâmetros, como a lista de ativos financeiros ou o limite de risco, basta editar as células relevantes no notebook diretamente no Google Colab. Em         seguida, execute novamente as células para ver os resultados atualizados.
  
## Dicas
**Salvar uma Cópia:** Para salvar uma cópia do notebook com suas alterações, vá em Arquivo > Salvar uma cópia no Drive, assim você poderá manter suas mudanças no seu próprio Google Drive.

**Download do Notebook:** Você também pode baixar o notebook como um arquivo .ipynb para rodá-lo localmente, caso tenha um ambiente Python configurado em sua máquina.
