FROM mcr.microsoft.com/dotnet/sdk:8.0 AS build

WORKDIR /src
ENV ASPNETCORE_URLS=http://*:5002

COPY ./ ./
RUN dotnet restore "/src/WebApplication/WebApplication.csproj"
RUN dotnet build "/src/WebApplication/WebApplication.csproj" -c Release -o /app/build
RUN dotnet publish "/src/WebApplication/WebApplication.csproj" -c Release -o /app

WORKDIR /app
CMD dotnet WebApplication.dll
