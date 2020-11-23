# escape=`
FROM mcr.microsoft.com/dotnet/sdk:5.0 as builder

WORKDIR C:\src
COPY src .

USER ContainerAdministrator
RUN dotnet restore && dotnet publish

# app image
FROM mcr.microsoft.com/dotnet/aspnet:5.0
EXPOSE 80
WORKDIR C:\dotnetapp
RUN mkdir app-state

CMD ["dotnet", "HitCountWebApp.dll"]
COPY --from=builder C:\src\bin\Debug\net5.0\publish .