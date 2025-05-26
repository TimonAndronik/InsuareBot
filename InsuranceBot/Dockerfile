
FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build
WORKDIR /app

COPY . .
RUN dotnet restore ./InsuranceBot/InsuranceBot.csproj
RUN dotnet publish ./InsuranceBot/InsuranceBot.csproj -c Release -o /app/out

FROM mcr.microsoft.com/dotnet/runtime:6.0 AS runtime
WORKDIR /app
COPY --from=build /app/out ./
ENTRYPOINT ["dotnet", "InsuranceBot.dll"]
