FROM mcr.microsoft.com/dotnet/sdk:9.0 AS build
WORKDIR /src

# Копирует csproj и восстанавливает nuget пакеты
COPY ArtSupplyStore.csproj .
RUN dotnet restore

# Копирование кода в контейнер и компиляция
COPY . .
RUN dotnet publish ArtSupplyStore.csproj -c Release -o /app/publish --no-restore

# Запуск приложения
FROM mcr.microsoft.com/dotnet/aspnet:9.0 AS runtime
WORKDIR /app
EXPOSE 8080
ENV ASPNETCORE_URLS=http://+:8080
COPY --from=build /app/publish .
ENTRYPOINT ["dotnet", "ArtSupplyStore.dll"]