#See https://aka.ms/containerfastmode to understand how Visual Studio uses this Dockerfile to build your images for faster debugging.

FROM mcr.microsoft.com/dotnet/core/aspnet:3.1-buster-slim AS base
WORKDIR /app
EXPOSE 80
EXPOSE 443

FROM mcr.microsoft.com/dotnet/core/sdk:3.1-buster AS build
WORKDIR /src
COPY ["Authentication.Project/Authentication.Project.csproj", "Authentication.Project/"]
RUN dotnet restore "Authentication.Project/Authentication.Project.csproj"
COPY . .
WORKDIR "/src/Authentication.Project"
RUN dotnet build "Authentication.Project.csproj" -c Release -o /app/build

FROM build AS publish
RUN dotnet publish "Authentication.Project.csproj" -c Release -o /app/publish

FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENTRYPOINT ["dotnet", "Authentication.Project.dll"]