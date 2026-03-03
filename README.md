# Kyoya DB

Este projeto utiliza o MongoDB em um container Docker para facilitar o desenvolvimento e testes.

## Pré-requisitos

- [Docker](https://www.docker.com/) instalado na sua máquina.

## Configuração

1. **Crie o arquivo de variáveis de ambiente**

   Antes de iniciar o container, é necessário criar o arquivo `mongod.env` na raiz do projeto. Você pode usar o arquivo de exemplo `mongod.env.example` como base:

   ```sh
   cp mongod.env.example mongod.env
   ```

   Edite o arquivo `mongod.env` e preencha os valores necessários:

   ```
   MONGO_INITDB_DATABASE=nome_do_banco
   MONGO_INITDB_ROOT_USERNAME=usuario_admin
   MONGO_INITDB_ROOT_PASSWORD=senha_admin
   ```

2. **Suba o container com Docker Compose**

   Execute o comando abaixo para iniciar o MongoDB:

   ```sh
   docker-compose up -d
   ```

   O MongoDB estará disponível na porta `27017`.

3. **Persistência de dados**

   Os dados do MongoDB serão armazenados no diretório `./mongodb/data` do seu projeto.

## URI de conexão

Após subir o container, você pode se conectar ao banco usando a seguinte URI:

```
mongodb://usuario_admin:senha_admin@localhost:27017/nome_do_banco
```

Substitua `usuario_admin`, `senha_admin` e `nome_do_banco` pelos valores definidos no seu arquivo `mongod.env`.

## Parar o container

Para parar o serviço, utilize:

```sh
docker-compose down
```

---
