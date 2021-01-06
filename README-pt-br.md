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

       ```
        Table Manga as M {
            id int [pk, increment, not null] // auto-increment
            name varchar [not null]
            description varchar [not null]
            volume int 
            price float [not null]
            author varchar [not null]
            category varchar [not null]
            publisher varchar [not null]
        }
       ```
    
    1.2. Foi selecionado os dados que não precisam de uma única tabela, ou seja, dados que podem ser adicionados mais informações relacionados a essa entidade.

       ```
        Table Author as A {
            id int [pk, increment, not null] // auto-increment
            name varchar [not null]
        }

        Table Publisher as P {
            id int [pk, increment, not null] // auto-increment
            name varchar [not null]
        }

        Table Category as C {
            id int [pk, increment, not null] // auto-increment
            name varchar [not null]
        }
       ```
            
    1.3. Foi verificado as relações entre as tabelas e as variáveis.

       + **Relação da tabela Mangá e Autor:** Um mangá pode possuir vários autores e um autor pode possuir vários mangás. Essa relação vai ser necessário criar uma tabela auxiliar, pois a relação entre esses dados é de N (muitos) para N (muitos).
       + **Relação da tabela Mangá e Editora:** Um mangá possui apenas uma editora e uma editora pode possuir vários mángas. Essa relação vai ser de 1 para N (muitos).
       + **Relação da tabela Mangá e Categoria:** Um mangá pode possuir várias categorias e uma categoria pode possuir vários mángas. Essa relação vai ser necessário criar uma tabela auxiliar, pois a relação entre esses dados é de N (muitos) para N (muitos).

       Com o mapeamento feito, foi removido as variáveis da tabela Manga e criado as tabelas auxiliares e por fim desenhado a relação entre elas:
        
       ```
        Table Manga as M {
            id int [pk, increment, not null] // auto-increment
            name varchar [not null]
            description varchar [not null]
            volume int 
            price float [not null]
            publisher int [not null]
        }

        Table Manga_Author as MA_AUX {
            id_author int [not null]
            id_manga int [not null]
        }

        Table Manga_Category as MC_AUX {
            id_category int [not null]
            id_manga int [not null]
        }

        Ref: M."publisher" > P."id"
        Ref: MA_AUX."id_author" - A."id"
        Ref: MA_AUX."id_manga" - M."id"
        Ref: MC_AUX."id_category" - C."id"
        Ref: MC_AUX."id_manga" - M."id"
       ``` 

O resultado final desse desenho:

![imagem com o desenho da tabela mangá e suas relações](https://github.com/hi-hi-ray/ecommerce-structuration/blob/main/src/images/manga-table-rdbms.PNG)

2.  Criação da tabela Quantity



__Dica: A [Quick DBD](https://www.quickdatabasediagrams.com/) é uma plataforma que utiliza o mesmo modelo de criação de diagrama do banco de dados e você pode conseguir a conta PRO apenas divulgando eles nas suas rede sociais.__



---
### Apoie este projeto (´｡• ᵕ •｡`) ♡
Você pode usar as [discussions](https://github.com/hi-hi-ray/ecommerce-structuration/discussions) para perguntar algo ou dar seu feedback.
