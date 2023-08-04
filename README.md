# Docker To-Do List 🐳

Neste projeto desenvolvido no módulo de Backend da Trybe, foi criado as configurações dos conteineres de uma aplicação Fullstack já pronta, integrando Backend e Frontend.

#### Instalação

Esse é um aplicativo em [NodeJS](https://nodejs.org/pt-br/about/), que possui **dois componentes principais** (`front` e `back`) e um **teste de saúde da aplicação**:
- `Front-end` Essa aplicação consome nossa API e nos retorna nossa lista;
- `Back-end` Onde a **mágica** acontece! Nosso back-end possui um banco de dados interno, onde são salvas nossas tarefas;
- `Testes` Onde validamos a comunicação entre `front` e `back-end`.

##### Estrutura do aplicativo

```bash
todo-app/
├── README.md # este arquivo
├── intro.gif # demonstração
├── back-end # responsável por processar nossos dados através de requisições
│   ├── node_modules.tar.gz # pacote opcional, para facilitar a criação de imagens no Docker
│   ├── package.json # principal componente da aplicação
│   ├── package-lock.json # arquivo responsável por otimizar a instalação em outros ambientes
│   └── src
│       ├── api
│       │   ├── routes.js
│       │   └── server.js
│       ├── controllers
│       │   └── Tasks.js
│       ├── database
│       │   ├── tasks.bkp.json
│       │   └── tasks.json
│       ├── models
│       │   └── Tasks.js
│       └── utils
│           └── fileHandler.js
├── front-end # responsável por ser uma interface amigável para nosso back-end
│   ├── node_modules.tar.gz # pacote opcional, para facilitar a criação de imagens no Docker
│   ├── package.json # principal componente da aplicação
│   ├── package-lock.json # arquivo responsável por otimizar a instalação em outros ambientes
│   ├── public
│   │   ├── favicon.ico
│   │   ├── index.html
│   │   ├── logo192.png
│   │   ├── logo512.png
│   │   ├── manifest.json
│   │   └── robots.txt
│   ├── README.md
│   └── src
│       ├── App.css
│       ├── App.js
│       ├── App.test.js
│       ├── components
│       │   ├── ItemAdd
│       │   │   ├── index.jsx
│       │   │   └── styles.css
│       │   ├── ItemList
│       │   │   ├── index.jsx
│       │   │   └── styles.css
│       │   ├── ItemRow
│       │   │   ├── index.jsx
│       │   │   └── styles.css
│       │   └── TaskReset
│       │       └── index.jsx
│       ├── context
│       │   └── taskContext.js
│       ├── index.css
│       ├── index.js
│       ├── logo.png
│       ├── reportWebVitals.js
│       ├── setupTests.js
│       └── utils
│           └── fetch.js
└── tests # responsável por validar essa comunicação
    ├── e2e
    │   └── health_status.test.js
    ├── jest.config.js
    ├── node_modules.tar.gz # pacote opcional, para facilitar a criação de imagens no Docker
    ├── package.json # principal componente da aplicação
    └── package-lock.json # arquivo responsável por otimizar a instalação em outros ambientes
```
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


## Pastas/arquivos desenvolvidos por mim

```bash
    docker/docker-commands
    docker/docker-compose.yml
    docker/todo-app/back-end/Dockerfile
    docker/todo-app/front-end/Dockerfile
    docker/todo-app/tests/Dockerfile
```
