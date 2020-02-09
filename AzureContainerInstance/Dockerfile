#See https://aka.ms/containerfastmode to understand how Visual Studio uses this Dockerfile to build your images for faster debugging.

#FROM mcr.microsoft.com/dotnet/core/sdk:3.1 AS installer-env

#COPY . /src/dotnet-function-app
#RUN cd /src/dotnet-function-app 
#RUN mkdir -p /home/site/wwwroot 
#RUN dotnet --list-sdks
#WORKDIR /src/dotnet-function-app
#RUN ls -lrt
#RUN pwd
#RUN dotnet publish FunctionApp1.csproj --output /home/site/wwwroot
#RUN pwd

FROM mcr.microsoft.com/azure-functions/dotnet:latest AS base
WORKDIR /app
EXPOSE 80

FROM mcr.microsoft.com/dotnet/core/sdk:3.1 AS build
WORKDIR /src
COPY ["FunctionApp1.csproj", ""]
RUN dotnet restore "FunctionApp1.csproj"
COPY . .
WORKDIR "/src/."
RUN dotnet build "FunctionApp1.csproj" -c Release -o /app/build

FROM build AS publish
RUN dotnet publish "FunctionApp1.csproj" -c Release -o /app/publish

FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENV AzureWebJobsScriptRoot=/app