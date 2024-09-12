# NLW Pocket: Javascript <!-- omit in toc -->

## Sumário <!-- omit in toc -->

- [Back-end](#back-end)
  - [Aplicação](#aplicação)
  - [Docker](#docker)
  - [Drizzle (ORM)](#drizzle-orm)
  - [Seed](#seed)
  - [Collection (REST Client)](#collection-rest-client)
- [Front-end](#front-end)
  - [Aplicação](#aplicação-1)
- [Material complementar](#material-complementar)

## Back-end

### Aplicação

O código-fonte do back-end se encontra [nesta pasta](./server/)

Para iniciar a aplicação rode o comando a seguir:

```shell
npm run dev
```

### Docker

Para iniciar a aplicação rode o comando a seguir:

```shell
docker compose up -d
```

Caso ocorra algum erro, você pode investigar o que está ocorrendo com os seguintes comandos:

- Verificar se o container está rodando
  ```shell
  docker ps
  ```
- Visualizar logs de um container
  ```shell
  docker logs {container id}
  ```

### Drizzle (ORM)

Esses são os comandos básicos utilizados no projeto para criação de tabelas via migrations:

- Criar migração
  ```shell
  npx drizzle-kit generate
  ```
- Efetuar migração
  ```shell
  npx drizzle-kit migrate
  ```
- Lançar o Studio
  ```shell
  npx drizzle-kit studio
  ```

### Seed

Para popular o banco de dados na primeira execução do projeto, execute o seguinte comando:

```shell
npm run seed
```

### Collection (REST Client)

[Aqui estão os endpoints](./server/src/http/collection.http) desta aplicação.

Após executar o seed, você poderá testá-los instalando [esta extensão](https://marketplace.visualstudio.com/items?itemName=humao.rest-client) no seu VsCode.

## Front-end

### Aplicação

O código-fonte do back-end se encontra [nesta pasta](./web/)

Para iniciar a aplicação rode o comando a seguir:

```shell
npm run dev
```

## Material complementar

[Aqui](https://docs-rocketseat.notion.site/FullStack-Intermedi-rio-Node-React-b2382e372d1f44f6bfb51a3d7b723dfd) você encontra o material em que me baseei para construir esse projeto.
