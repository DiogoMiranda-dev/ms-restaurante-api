# ms-restaurante-api

**Uma aplicação .NET Core 6.0 demonstrada com Docker, RabbitMQ e PHPMyAdmin.**

## Visão Geral

Este projeto implementa uma aplicação de restaurante utilizando uma arquitetura de microserviços. Os serviços são containerizados com Docker e comunicam-se através do RabbitMQ.

* **Item-Service:** Gerencia informações sobre os itens do menu.
* **Restaurante-Service:** Gerencia informações sobre os restaurantes e pedidos.

## Pré-requisitos

* **Docker:** https://www.docker.com/get-started
* **.NET Core SDK:** https://dotnet.microsoft.com/download
* **Git:** https://git-scm.com/downloads

## Instalação e Execução

1. **Clone o repositório:**
  ```bash
   git clone [https://github.com/DiogoMiranda-dev/ms-restaurante-api.git](https://github.com/DiogoMiranda-dev/ms-restaurante-api.git)
   cd ms-restaurante-api
```

### Instalando o Docker

1. Acesse o site oficial do Docker: [https://www.docker.com/get-started](https://www.docker.com/get-started)
2. Baixe a versão compatível com o seu sistema operacional.
3. Siga as instruções de instalação fornecidas pelo Docker.

Após a instalação, você pode verificar se o Docker foi instalado corretamente executando o seguinte comando no terminal:

```
docker --version
```

### Executando a Aplicação com Docker Compose

Para iniciar a aplicação, execute o seguinte comando:

```bash
docker-compose up --build
```
### Acessando os Serviços

Após o Docker Compose iniciar, você pode acessar os seguintes serviços através do seu navegador:

- **PHPMyAdmin** (Interface para gerenciar o banco de dados):  
  Acesse: [http://localhost:8080/](http://localhost:8080/)

- **RabbitMQ** (Interface para gerenciamento das filas):  
  Acesse: [http://localhost:15672/#/](http://localhost:15672#/)

- **Item-Service** (Swagger - API do serviço de itens):  
  Acesse: [http://localhost:8082/swagger/index.html](http://localhost:8082/swagger/index.html)

- **Restaurante-Service** (Swagger - API do serviço de restaurante):  
  Acesse: [http://localhost:8081/swagger/index.html](http://localhost:8081/swagger/index.html)

### Parar os Containers
```bash
docker-compose down
````