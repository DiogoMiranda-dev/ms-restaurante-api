# Etapa de build
FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build
WORKDIR /app

# Copiar o arquivo .csproj e restaurar as depend�ncias
COPY *.csproj ./
RUN dotnet restore

# Copiar o c�digo da aplica��o
COPY . ./

# Publicar a aplica��o com as configura��es de Release
RUN dotnet publish -c Release -o out

# Etapa de runtime
FROM mcr.microsoft.com/dotnet/aspnet:6.0
WORKDIR /app

# Copiar os arquivos necess�rios da etapa de build
COPY --from=build /app/out .

# Copiar o arquivo de configura��o espec�fico de produ��o
COPY appsettings.Production.json ./appsettings.json

# Definir a vari�vel de ambiente para configurar o ambiente de produ��o
ENV ASPNETCORE_ENVIRONMENT=Production

# Definir o ponto de entrada para a aplica��o
ENTRYPOINT ["dotnet", "ItemService.dll"]