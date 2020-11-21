FROM mcr.microsoft.com/dotnet/sdk:5.0

WORKDIR /src
COPY src/ .

USER ContainerAdministrator
RUN dotnet restore && dotnet build
CMD ["dotnet", "run"]