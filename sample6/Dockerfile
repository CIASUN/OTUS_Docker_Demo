FROM mcr.microsoft.com/dotnet/aspnet:8.0 AS base
WORKDIR /app
ENV ASPNETCORE_URLS=http://*:5002

FROM mcr.microsoft.com/dotnet/sdk:8.0 AS build
WORKDIR /src
COPY ["WebApplication/WebApplication.csproj", "WebApplication/"]
RUN dotnet restore "WebApplication/WebApplication.csproj"
COPY ./ ./
RUN dotnet build "WebApplication/WebApplication.csproj" -c Release --no-restore
RUN dotnet publish "WebApplication/WebApplication.csproj" -c Release -o /app/publish --no-restore --no-build

FROM base AS final
COPY --from=build /app/publish ./
CMD dotnet WebApplication.dll
