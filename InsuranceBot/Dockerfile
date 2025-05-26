FROM mcr.microsoft.com/dotnet/sdk:8.0 AS build
WORKDIR /app


COPY InsuranceBot.csproj ./
RUN dotnet restore InsuranceBot.csproj

COPY . ./

RUN dotnet publish InsuranceBot.csproj -c Release -o out

FROM mcr.microsoft.com/dotnet/runtime:8.0
WORKDIR /app
COPY --from=build /app/out .
ENTRYPOINT ["dotnet", "InsuranceBot.dll"]
