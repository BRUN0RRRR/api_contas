# API Contas

API desenvolvida em ASP.NET Core para gerenciamento de contas.

## Pré-requisitos

Antes de iniciar o projeto, certifique-se de possuir instalado:

* .NET SDK 8.0 (ou versão utilizada pelo projeto)
* SQL Server (caso utilize banco de dados)
* Visual Studio 2022 ou VS Code
* Git

## Clonando o Projeto

```bash
git clone https://seu-repositorio/api_contas.git
cd api_contas
```

## Restaurando Dependências

Execute o comando abaixo na raiz do projeto:

```bash
dotnet restore
```

## Configuração do Banco de Dados

Verifique o arquivo:

```json
appsettings.json
```

Configure a string de conexão:

```json
{
  "ConnectionStrings": {
    "DefaultConnection": "Server=SERVIDOR;Database=api_contas;User Id=usuario;Password=senha;TrustServerCertificate=True;"
  }
}
```

## Executando as Migrations

Caso utilize Entity Framework:

```bash
dotnet ef database update
```

## Executando o Projeto

```bash
dotnet run
```

Ou através do Visual Studio:

1. Abra a solução (`.sln`)
2. Defina o projeto API como Startup Project
3. Pressione F5

---

# Swagger

## Habilitando o Swagger

Verifique se o pacote está instalado:

```bash
dotnet add package Swashbuckle.AspNetCore
```

No arquivo `Program.cs`, adicione:

```csharp
builder.Services.AddEndpointsApiExplorer();
builder.Services.AddSwaggerGen();
```

Após a criação da aplicação:

```csharp
if (app.Environment.IsDevelopment())
{
    app.UseSwagger();
    app.UseSwaggerUI();
}
```

Para deixar o Swagger disponível em qualquer ambiente:

```csharp
app.UseSwagger();
app.UseSwaggerUI();
```

## Acessando o Swagger

Após iniciar a aplicação, acesse:

```text
https://localhost:5001/swagger
```

ou

```text
http://localhost:5000/swagger
```

A porta pode variar conforme a configuração do projeto.

---

# Estrutura do Projeto

```text
api_contas
│
├── Controllers
├── Models
├── DTOs
├── Services
├── Repositories
├── Data
├── Migrations
├── Program.cs
├── appsettings.json
└── README.md
```

---

# Comandos Úteis

### Restaurar dependências

```bash
dotnet restore
```

### Compilar

```bash
dotnet build
```

### Executar

```bash
dotnet run
```

### Criar Migration

```bash
dotnet ef migrations add NomeDaMigration
```

### Atualizar Banco

```bash
dotnet ef database update
```

### Limpar Build

```bash
dotnet clean
```
