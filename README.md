# Projeto Docker To Do List :whale2:

## Contexto :bookmark_tabs:

Neste projeto, o objetivo era "conteinerizar" as aplicações de frontend, backend e testes, criar uma conexão entre elas e orquestrar seu funcionamento.

## O que foi desenvolvido? 🤔

Criação das imagens Dockerfile das aplicações e configuração do docker-compose.


## Técnologias usadas :technologist:

Projeto desenvolvido em React, utilizando _Context API_ para gerenciamento de estados da aplicação.

## Habilidades

Neste projeto, você será capaz de:

  * Usar comandos dockers no CLI - Interface de linha de comando;

  * Criar um contêiner Docker para uma aplicação de front-end;

  * Criar um contêiner Docker para uma aplicação de back-end;

  * Criar um contêiner Docker para uma aplicação de testes;

  * Orquestrar os três contêineres utilizando o Docker compose.

## Requisitos
  * Docker e Docker-compose

## Executando aplicação

1. Clone o repositório
  * `git clone git@github.com:LucasAccurcio/docker-todo-list.git`.
  * Entre na pasta do repositório que você acabou de clonar:
    * `cd docker-todo-list`

## Executando a aplicação

* Para rodar a aplicação:
  - Acesse a pasta todo-app:
  `cd todo-app`

  - Acesse a pasta back-end e rode o comando npm install:
  `cd back-end && npm install`

  - Acesse a pasta front-end e rode o comando npm install:
  `cd front-end && npm install`

  - Acesse a pasta todo-app e execute o comando
  `docker-compose up`


  As imagens serão criadas e se tudo correr bem, os 3 serviços (front-end, back-end e tests) estão funcionando.

  O docker compose ficará rodando os testes e requisições para o back-end.

  Para visualizar a aplicação, basta acessar no seu navegador o endereço:
  - [localhost:3000](http://localhost:3000) 