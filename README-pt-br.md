# Estruturação de E-Commerce

![imagem com animação e estrela no fundo e um texto dizendo database e-commerce structuration](https://github.com/hi-hi-ray/ecommerce-structuration/blob/main/src/images/Cover%20Database%20Animated.gif)

## Sobre o projeto.
Este é um projeto que contém a estrutura de um banco de dados de uma pequena loja fictícia de mangás online. O objetivo do banco de dados é criar a possíbilidade de ter um controle do estoque e de vendas.

## Dados a serem usados na tabela.
✩ Nome do mangá.

✩ Categoria do mangá.

✩ Descrição do mangá.

✩ Volume do mangá.

✩ Preço.

✩ Quantidade.

✩ Data do pedido.

✩ Nome do comprador.

✩ Nome do Autor.

✩ Endereço do Comprador.

✩ Editora.

✩ Quantidade de mangá.

## Índice
✩ [Banco de dados relacional RDBMS](#banco-de-dados-relacional-rdbms)

✩ Banco de dados não relacional

### Banco de dados relacional RDBMS
Esse tipo de banco possui estrutura organizacional disposta em tabelas onde as mesmas podem se relacionar entre si. Os bancos mais conhecidos dessa arquitetura são o Oracle, MySQL, PostgreSQL, Microsoft SQL Server e SQLite.

#### Banco Utilizado:
- SQLite
- Motivação da escolha: O SQLite é um banco muito bom para quando se tem um projeto pequeno e local. Como o objetivo é ser um exemplo de estruturação de banco, o SQLite vai ser perfeito nesse cenário.

#### Itens que foram levados em consideração para construção do banco:
♡ Desenhar o mapa do banco e suas possíveis relações.

♡ Evitar dados duplicados e redundantes.

♡ Precisão ao identificar os diferentes tipos de tabelas que podem ser construídas com os dados recebidos. 

♡ Identificando os padrões dos dados e aplicando na sua coluna o seu tipo e tamanho.

♡ Identificar as chaves primárias e estrangeiras.

♡ Ver as relações e se há necessidade de tabelas auxiliares para melhorar a performance de consultas. 

#### Mapa de variáveis e relações.

Utilizando o [DBDiagram](https://dbdiagram.io/) que é uma plataforma gratuita e que gera a tabela e suas relações do diagrama de acordo com o que você digita, foi realizado os passos a seguir:

1.  Criação da tabela Manga

    1.1. Foi agrupado todos os dados que são relacionados à mangá.
    
    1.2. Foi selecionado os dados que não precisam de uma única tabela, ou seja, dados que podem ser adicionados mais informações relacionados a essa entidade.




** Dica: A [Quick DBD](https://www.quickdatabasediagrams.com/) é uma plataforma que utiliza o mesmo modelo de criação de diagrama do banco de dados e você pode conseguir a conta PRO apenas divulgando eles nas suas rede sociais. **



---
### Apoie este projeto (´｡• ᵕ •｡`) ♡
Você pode usar as [discussions](https://github.com/hi-hi-ray/ecommerce-structuration/discussions) para perguntar algo ou dar seu feedback.
