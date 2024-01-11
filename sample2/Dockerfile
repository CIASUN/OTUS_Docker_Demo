FROM mcr.microsoft.com/dotnet/aspnet:8.0

ARG workdir=/app 
WORKDIR $workdir
#WORKDIR /app
LABEL app_label=my1
ENV ASPNETCORE_URLS=http://*:5002
#ENV ASPNETCORE_ENVIRONMENT=DEVELOPMENT
#EXPOSE 5002

COPY ../WebApplication/bin/Release/net8.0/publish ./
CMD dotnet WebApplication.dll --urls $ASPNETCORE_URLS

#ENTRYPOINT ["dotnet", "WebApplication.dll"]
#CMD ["--urls", "http://*:5002"]
