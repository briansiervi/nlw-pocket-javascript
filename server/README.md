# NLW Pocket: Javascript (server)

## Aplicação
- Iniciar
  ```shell
  npm run dev
  ```

## Docker
- Iniciar compose
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

## Drizzle (ORM)
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

## Seed
- Executar
  ```shell
  npm run seed
  ```