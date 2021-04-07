# Wrangle_Twitter

Dados do mundo real raramente vem limpos.

Coletar dados de uma série de fontes em uma variedade de formatos, requerem avaliação de sua qualidade e arrumação e, só então, poderão ser limpos. Isso é chamado de data wrangling.

Extrair dados por meio de programação. Após a extração é feita uma avaliação e limpeza de dados para que sejam preparados  para uma análise e visualização

O conjunto de dados que será utilizado é o arquivo de tweets do usuário do Twitter @dog_rates, também conhecido como WeRateDogs. WeRateDogs é uma conta no Twitter que classifica os cães das pessoas com um comentário bem humorado sobre o cão. Ele foi iniciado em 2015 pelo estudante universitário Matt Nelson e recebeu cobertura da mídia internacional. Em outubro de 2017 tinha mais 3,7 milhões de seguidores.

Os seguintes pacotes foram necessários para realizar essa análise:

pandas
numpy
requests
tweepy
json

### Contexto
Este arquivo contém dados básicos de tweets para os mais de 5000 de seus tweets, mas não tudo. Uma coluna o arquivo contém com certeza: cada texto de tweet, o que eu usei para extrair classificação, nome e "estágio" do cachorro (ou seja, doggo, floofer, pupper e puppo).

![image](https://user-images.githubusercontent.com/38633413/113936551-4a449d80-97ce-11eb-81a6-7c9aa031977b.png)


O Problema é que as avaliações provavelmente não estão todas corretas. O mesmo acontece para os nomes e estágios de cachorros. Por isso a necessidade de avaliar e limpar essas colunas para usá-las em análises e visualizações.

***O básico desse conjunto de dados:*** a contagem de retweets e favoritos são duas colunas omissas notáveis. Mas os dados adicionais foram coletados da API do Twitter, mas, só porque tive acesso aos IDs no arquivo de tweets (sem essas identificações, o público só tem acesso aos últimos ~3000 tweets pela API do Twitter).

Foi utilizada uma rede neural que consegue classificar as raças dos cachorros. **Resultados:** uma tabela cheia de previsões de imagens ao lado de cada ID de tweet, URL de imagem e o número de imagem de corresponde à previsão mais confiante (1 a 4, já que tweets podem ter quatro imagens).

### Exemplo:
para a última linha dessa tabela:

- tweet_id é a última parte da URL após "status/" → https://twitter.com/dog_rates/status/889531135344209921
- p1 é a previsão número 1 do algoritmo para a imagem no tweet → golden retriever
- p1_conf é o quão confiante o algoritmo está nessa previsão número 1 → 95%
- p1_dog é se a previsão número 1 é uma raça de cachorro → TRUE
- p2 é a segunda previsão mais provável do algoritmo → Labrador retriever
- p2_conf é o quão confiante esse algoritmo está nessa previsão número 2 → 1%
- p2_dog é se a previsão número 2 é uma raça de cachorro → TRUE
- etc.

### Pontos principais

- Foram avaliadas somente classificações originais (não retweets) que têm imagens.
- Avaliado e limpo, problemas de qualidade foram tratados ou excluidos.
- A limpeza inclui a fusão de acordo com as regras de dados arrumados para facilitar a análise e visualização.

### Detalhes do projeto
Data wrangling, que consiste em:
- Coletar dados
- Avaliar dados
- Limpar dados
- Armazenar, analisar e visualizar dados wrangled
- Elaborar relatórios sobre 1) seus esforços de data wrangling 2) suas análises e visualizações de dados


