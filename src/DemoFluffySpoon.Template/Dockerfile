FROM mcr.microsoft.com/dotnet/core/aspnet:3.1.3 AS base
WORKDIR /app
EXPOSE 8080

FROM mcr.microsoft.com/dotnet/core/sdk:3.1.201 AS publish
WORKDIR /sln
COPY NuGet.Config .
COPY packages/ ./packages
COPY ["src/DemoFluffySpoon.Template/DemoFluffySpoon.Template.csproj", "src/DemoFluffySpoon.Template/"]
RUN dotnet restore "src/DemoFluffySpoon.Template/DemoFluffySpoon.Template.csproj"
COPY . .
WORKDIR "src/DemoFluffySpoon.Template"
ARG VERSION=1
RUN dotnet publish "DemoFluffySpoon.Template.csproj" /p:Version=$VERSION -c Release -o /app/publish

FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENTRYPOINT ["dotnet", "DemoFluffySpoon.Template.dll"]