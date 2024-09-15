# NLW Pocket: Javascript <!-- omit in toc -->

## Sumário <!-- omit in toc -->

- [Back-end](#back-end)
  - [Banco de dados](#banco-de-dados)
  - [Collection (REST Client)](#collection-rest-client)
- [Front-end](#front-end)
- [Apêndice de comandos úteis](#apêndice-de-comandos-úteis)
  - [Docker](#docker)
  - [Drizzle (ORM)](#drizzle-orm)
- [Material complementar](#material-complementar)

## Back-end

O código-fonte do back-end se encontra na pasta [server](./server/).
Na primeira execução é necessário instalar as dependências dentro dessa pasta, com o comando:

  ```shell
  npm i
  ```

### Banco de dados
Na primeira execução precisamos criar o banco de dados postgres.

1. Apontando para o banco de dados

    Para subir esse banco localmente, podemos alterar a configuração do arquivo **.env** localizado na raiz da pasta [server](/server/) para:

    ```js
    DATABASE_URL='postgresql://docker:docker@localhost:5432/inorbit'
    ```

    E rodar o docker compose:

    ```shell
    docker compose up -d
    ```

    Como alternativa podemos criar um banco de dados novo em um servidor externo e alterar a constante para o padrão a seguir:

    ```js
    DATABASE_URL='postgresql://{usuario}:{senha}@{url}=require'
    ```

2. Criando as tabelas
    Para criar as tabelas precisamos efetuar as migrations com o drizzle

    ```shell
    npx drizzle-kit migrate
    ```

3. Seed
    Após ter as tabelas criadas, podemos populá-las rodando o script de seed configurado no arquivo [package.json](/server/package.json)

    ```shell
    npm run seed
    ```

    E também visualizá-las no navegador através do Drizzle, com o seguinte comando:

    ```shell
    npx drizzle-kit studio
    ```

    Acessando o endereço [https://local.drizzle.studio/](https://local.drizzle.studio/)

Nas próximas execuções, caso tenha sido utilizado docker compose, o mesmo deverá ser executado novamente, com o mesmo comando:

```shell
docker compose up -d
```

### Collection (REST Client)

[Aqui estão os endpoints](./server/src/http/collection.http) desta aplicação.

Após executar o seed, você poderá testá-los instalando [esta extensão](https://marketplace.visualstudio.com/items?itemName=humao.rest-client) no seu VsCode.


## Front-end

O código-fonte do back-end se encontra na pasta [web](./web/).
Na primeira execução é necessário instalar as dependências dentro dessa pasta, com o comando:

  ```shell
  npm i
  ```

Para iniciar a aplicação rode o comando a seguir:

```shell
npm run dev
```

## Apêndice de comandos úteis

### Docker
- Subir o docker
    ```shell
    docker compose up -d
    ```
- Verificar se o container está rodando
  ```shell
  docker ps
  ```
- Visualizar logs de um container
  ```shell
  docker logs {container id}
  ```

### Drizzle (ORM)
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

## Material complementar

[Aqui](https://docs-rocketseat.notion.site/FullStack-Intermedi-rio-Node-React-b2382e372d1f44f6bfb51a3d7b723dfd) você encontra o material em que me baseei para construir esse projeto.

Além disso, há alguns vídeos que nos ajudam a entender o que foi desenvolvido:
- [3 dicas para escalar apps React com TailwindCSS](https://www.youtube.com/watch?v=BhPyF0BQpF0&t=575s&ab_channel=Rocketseat)

E também sites utilitários:
- https://transform.tools/