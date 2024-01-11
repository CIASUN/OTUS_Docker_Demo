#https://soya.tealeaf.su/tasks/831.html
FROM ubuntu:22.04

WORKDIR /app
ENV ASPNETCORE_URLS http://*:5002

RUN apt update; apt install wget -y;
RUN wget https://packages.microsoft.com/config/ubuntu/22.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb; \
    dpkg -i packages-microsoft-prod.deb
RUN apt-get update; \
    apt-get install -y apt-transport-https && \
    apt-get update && \
    apt-get install -y aspnetcore-runtime-8.0

COPY ../WebApplication/bin/Release/net8.0/publish ./
CMD dotnet WebApplication.dll

