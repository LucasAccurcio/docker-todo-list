### Trybe Todo-App 🖥️ 📝

Esse é o aplicativo de tarefas **Trybe Todo-App**!

Com ele, você pode se organizar de maneira simples, adicionando, marcando e/ou removendo suas tarefas.

Uma verdadeira *mão-na-roda* para acompanhar seu progresso!

![Alt Text](./intro.gif)

#### Requisitos

- [NodeJS LTS](https://github.com/nodesource/distributions/blob/master/README.md#debinstall) (14 ou mais).
  - O Sistema Operacional [deve suportar o NodeJS](https://github-com.translate.goog/nodejs/build/issues/2168?_x_tr_sl=en&_x_tr_tl=pt&_x_tr_hl=pt-BR&_x_tr_pto=nui).
  - Aplicações como o `create-react-app` [requerem essa versão mínima](https://pt-br.reactjs.org/docs/create-a-new-react-app.html#create-react-app) para funcionar corretamente


#### Instalação

Esse é um aplicativo em [NodeJS](https://nodejs.org/pt-br/about/), que possui **dois componentes principais** (`front` e `back`) e um **teste de saúde da aplicação**:
- `Front-end` Essa aplicação consome nossa API e nos retorna nossa lista;
- `Back-end` Onde a **mágica** acontece! Nosso back-end possui um banco de dados interno, onde são salvas nossas tarefas;
- `Testes` Onde validamos a comunicação entre `front` e `back-end`.


##### Com quem devo me preocupar primeiro?

- Como o `back-end` é o coração 💚 dessa aplicação, é possível utilizar ele sem um `Front-end`, nesse caso, é possível consumi-lo através de requisições REST, através de seu aplicativo de requisições favorito, como Postman, Insomnia, HTTPie, etc!
  - É recomendável roda-lo primeiro para garantir que o front-end tem da onde conseguir as informações de tarefas!

- O `front-end`, por outro lado, dá uma cara mais elegante 🌟 para nosso app, e é preferencialmente recomendado para consumo do nosso back-end!
  - É recomendável deixa-lo por segundo, já que ainda que o `front` funcione, ele precisa de uma API para consumir - papel do nosso back-end.

###### Instalando o back-end

- Acesse a pasta `./todo-app/back-end`;
- Instalar a aplicação utilizando o comando `npm install`;
- O processo não deve retornar erros. `Warns` *(Avisos)* não impedem seu funcionamento;
- Rodar a aplicação com `npm start`;
- Por padrão, essa aplicação funciona a partir da porta `3001`;

###### Instalando o front-end

- Acesse a pasta `./todo-app/front-end`;
- Instalar a aplicação utilizando o comando `npm install`;
- O processo não deve retornar erros. `Warns` *(Avisos)* não impedem seu funcionamento;
- Rodar a aplicação com `npm start`;
- Esse aplicativo requer, **excepcionalmente**, um arquivo `.env`, já contido em sua pasta no repositório;
- Por padrão, essa aplicação funciona a partir da porta `3000`;
- Essa aplicação pode receber variáveis de ambiente para mudar o acesso do `back-end`:
  - `REACT_APP_API_HOST`: padrão `localhost`;
    - *(Docker)* Aqui você deve indicar o nome do container do `back-end`;
  - `REACT_APP_API_PORT`: padrão `3001`.
    - *(Docker)* Aqui você deve indicar a porta que você definiu internamente no container do `back-end`;

###### Utilizando o aplicativo de testes

- ⚠️ Essa aplicação só funciona **se associada a uma rede Docker**;
- Acesse a pasta `./todo-app/front-end`;
- Instalar a aplicação utilizando o comando `npm install`;
- O processo não deve retornar erros. `Warns` *(Avisos)* não impedem seu funcionamento;
- Rodar a aplicação com `npm test`;
- Essa aplicação pode receber variáveis de ambiente para mudar o acesso ao front-end:
  - `FRONT_HOST`: padrão `localhost`;
    - *(Docker)* Aqui você deve indicar o nome do container do `front-end`;
  - `FRONT_PORT`: padrão `3000`.
    - *(Docker)* Aqui você deve indicar a porta que você definiu internamente no container do `front-end`;

###### Dicas sobre a conteinerização de aplicações NodeJS

⚠️ Aplicações `NodeJS`, necessitam de algumas coisas para funcionar:
- Um `package.json`, que provê informações e scripts de inicialização para a aplicação, **esse arquivo é obrigatório no funcionamento e deve estar no container do app referido**;
- Um `package-lock.json`, que provê um "cache" de pacotes, necessários a aplicação, **esse arquivo não precisa ser copiado para o container, mas ele precisa existir para a aplicação funcionar, ou seja, caso ele não exista no container, você precisará instalar a aplicação `NodeJS`, dentro do container, obrigatoriamente**;
- Uma pasta `node_modules`, **que é criada *(ou aproveitada, caso já exista)* durante a instalação - que é obrigatória - no container**;
- Aplicativos fonte (`source`, `src`) e complementares (por exemplo `public`, `.env*`), **esses arquivos são da aplicação propriamente dita e devem estar no container**, caso não estejamos trabalhando apenas com _builds_ ou _compilações_ desses aplicativos *(que podem ter funcionamento diferente)*.

###### Aproveitando os arquivos `node_modules.tar.gz`

Aplicações `NodeJS`, durante suas respectivas instalações, geram uma pasta nomeada como `node_modules`, que contém tudo o que a aplicação precisa pra funcionar.

Esse repositório já prove em cada serviço, um pacote compactado contendo essas dependências, chamado `node_modules.tar.gz`.

Dessa forma, em um `Dockerfile`, é possível aproveitar esse recurso para adicionar esse pacote à imagem, lembrando aqui, que o comando `ADD` do `Dockerfile`, além de adicionar arquivos, também faz a extração de pacotes, como nesse caso.

Caso você opte por utilizar esse recurso, o *build* de suas imagens levará menos tempo, já que, nesse caso, **a instalação será mais rápida, aproveitando esses recursos**.
