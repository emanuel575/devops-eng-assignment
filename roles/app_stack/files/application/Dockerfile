FROM mcr.microsoft.com/dotnet/sdk:5.0
WORKDIR /app

# Clone the Git repository
RUN apt-get update && apt-get install -y git
RUN git clone https://github.com/jasonsturges/mysql-dotnet-core.git .

# Build and run the .NET Core project
RUN dotnet tool install --global dotnet-ef
RUN dotnet restore && dotnet build

# Run Entity Framework Core migrations
RUN dotnet ef database update

CMD ["dotnet", "run"]