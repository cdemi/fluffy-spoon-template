FROM mcr.microsoft.com/dotnet/core/aspnet:3.0.0 AS base
WORKDIR /app
EXPOSE 8080

FROM mcr.microsoft.com/dotnet/core/sdk:3.0.100 AS publish
WORKDIR /sln
COPY NuGet.Config .
COPY packages/ ./packages
COPY ["src/fluffyspoon.template/fluffyspoon.template.csproj", "src/fluffyspoon.template/"]
RUN dotnet restore "src/fluffyspoon.template/fluffyspoon.template.csproj"
COPY . .
WORKDIR "src/fluffyspoon.template"
ARG VERSION=1
RUN dotnet publish "fluffyspoon.template.csproj" /p:Version=$VERSION -c Release -o /app/publish

FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENTRYPOINT ["dotnet", "fluffyspoon.template.dll"]