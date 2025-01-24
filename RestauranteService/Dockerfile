# Etapa de build
FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build
WORKDIR /app

# Copiar o arquivo .csproj e restaurar as dependências
COPY *.csproj ./
RUN dotnet restore

# Copiar o código da aplicação
COPY . ./

# Publicar a aplicação com as configurações de Release
RUN dotnet publish -c Release -o out

# Etapa de runtime
FROM mcr.microsoft.com/dotnet/aspnet:6.0
WORKDIR /app

# Copiar os arquivos necessários da etapa de build
COPY --from=build /app/out .

# Copiar o arquivo de configuração específico de produção
COPY appsettings.Production.json ./appsettings.json

# Definir a variável de ambiente para configurar o ambiente de produção
ENV ASPNETCORE_ENVIRONMENT=Production

# Definir o ponto de entrada para a aplicação
ENTRYPOINT ["dotnet", "RestauranteService.dll"]
