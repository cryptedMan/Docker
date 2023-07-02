#Base image
FROM mcr.microsoft.com/dotnet/sdk:7.0 AS build
WORKDIR /source


#Copy csproj and restore dependencies
COPY *.csproj .
RUN dotnet restore


#Copy and publish application files
COPY . .
RUN dotnet publish -c release -o /app

#Final image
From mcr.microsoft.com/dotnet/aspnet:7.0
WORKDIR /app
COPY --from=build /app .

ENTRYPOINT [ "dotnet", "dockerDotnetApp.dll" ]