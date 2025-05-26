FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build
WORKDIR /app
COPY . .
RUN dotnet restore ./InsuranceBot/InsuranceBot.csproj

FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build

WORKDIR /app
COPY --from=build /app/out .
ENTRYPOINT ["dotnet", "InsuranceBot.dll"]
