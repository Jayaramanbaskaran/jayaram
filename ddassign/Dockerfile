FROM mcr.microsoft.com/dotnet/aspnet:3.1 AS base

WORKDIR /app

EXPOSE 80

EXPOSE 443



FROM mcr.microsoft.com/dotnet/sdk:3.1 AS build

WORKDIR /src

#COPY ["MyFirstDotNetApp/MyFirstDotNetApp.csproj", "MyFirstDotNetApp/"]

#RUN dotnet restore "MyFirstDotNetApp/MyFirstDotNetApp.csproj"

COPY *.csproj ./

#RUN dotnet restore MyFirstDotNetApp/MyFirstDotNetApp.csproj

RUN dotnet restore *.csproj

COPY . .

WORKDIR /src/.



RUN dotnet build "ddassign.csproj" -c Release -o /app/build



FROM build AS publish

RUN dotnet publish "ddassign.csproj" -c Release -o /app/publish
