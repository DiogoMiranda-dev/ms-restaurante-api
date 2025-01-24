# ms-restaurante-api

**Uma aplica��o .NET Core 6.0 demonstrada com Docker, RabbitMQ e PHPMyAdmin.**

## Vis�o Geral

Este projeto implementa uma aplica��o de restaurante utilizando uma arquitetura de microservi�os. Os servi�os s�o containerizados com Docker e comunicam-se atrav�s do RabbitMQ.

* **Item-Service:** Gerencia informa��es sobre os itens do menu.
* **Restaurante-Service:** Gerencia informa��es sobre os restaurantes e pedidos.

## Pr�-requisitos

* **Docker:** https://www.docker.com/get-started
* **.NET Core SDK:** https://dotnet.microsoft.com/download
* **Git:** https://git-scm.com/downloads

## Instala��o e Execu��o

1. **Clone o reposit�rio:**
  ```bash
   git clone [https://github.com/DiogoMiranda-dev/ms-restaurante-api.git](https://github.com/DiogoMiranda-dev/ms-restaurante-api.git)
   cd ms-restaurante-api
```

### Instalando o Docker

1. Acesse o site oficial do Docker: [https://www.docker.com/get-started](https://www.docker.com/get-started)
2. Baixe a vers�o compat�vel com o seu sistema operacional.
3. Siga as instru��es de instala��o fornecidas pelo Docker.

Ap�s a instala��o, voc� pode verificar se o Docker foi instalado corretamente executando o seguinte comando no terminal:

```
docker --version
```

### Executando a Aplica��o com Docker Compose

Para iniciar a aplica��o, execute o seguinte comando:

```bash
docker-compose up --build
```
### Acessando os Servi�os

Ap�s o Docker Compose iniciar, voc� pode acessar os seguintes servi�os atrav�s do seu navegador:

- **PHPMyAdmin** (Interface para gerenciar o banco de dados):  
  Acesse: [http://localhost:8080/](http://localhost:8080/)

- **RabbitMQ** (Interface para gerenciamento das filas):  
  Acesse: [http://localhost:15672/#/](http://localhost:15672#/)

- **Item-Service** (Swagger - API do servi�o de itens):  
  Acesse: [http://localhost:8082/swagger/index.html](http://localhost:8082/swagger/index.html)

- **Restaurante-Service** (Swagger - API do servi�o de restaurante):  
  Acesse: [http://localhost:8081/swagger/index.html](http://localhost:8081/swagger/index.html)

### Parar os Containers
```bash
docker-compose down
````