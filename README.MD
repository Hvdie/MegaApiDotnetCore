# Megaman Boss API

<p align="center">
  <img src="https://i.pinimg.com/736x/3f/62/78/3f6278755db54b96e50ee7a00290bc43.jpg" alt="Megaman Logo">
</p>

## 📌 Sobre o Projeto

Este projeto é uma API desenvolvida em **.NET Core 3.1**, que fornece informações sobre os chefes da franquia **Megaman**. Seu principal objetivo é servir como backend para fornecer JSONs com informações detalhadas dos personagens, conforme o formato abaixo:

```json
{
  "Id": 1,
  "Code": "DLN/DRN-003",
  "Name": "Cutman",
  "HP": 150,
  "Picture": "https://vignette.wikia.nocookie.net/megaman/images/2/22/Cutman.png"
}
```

## ⚙️ Tecnologias e Dependências

A API foi desenvolvida utilizando **.NET Core 3.1** e faz uso das seguintes bibliotecas:

| Dependência                                                                                                             | Descrição                                      |
| ----------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------- |
| [Microsoft.EntityFrameworkCore](https://www.nuget.org/packages/Microsoft.EntityFrameworkCore/3.1.8)                     | ORM para interação com banco de dados          |
| [Microsoft.EntityFrameworkCore.Design](https://www.nuget.org/packages/Microsoft.EntityFrameworkCore.Design/3.1.8)       | Ferramentas para design e migrações do EF Core |
| [Microsoft.EntityFrameworkCore.SqlServer](https://www.nuget.org/packages/Microsoft.EntityFrameworkCore.SqlServer/3.1.8) | Provedor do EF Core para SQL Server            |
| [Newtonsoft.Json](https://www.nuget.org/packages/Newtonsoft.Json/12.0.2)                                                | Biblioteca para manipulação de JSON            |

## 📂 Estrutura do Projeto

A estrutura do projeto segue a seguinte organização:

```
.vs
.vscode
bin
Controllers         # Controladores da API
Database           # Configuração e contexto do banco de dados
middlewares        # Middlewares personalizados
Models            # Modelos de dados
obj
Properties
Services          # Serviços de regras de negócio
appsettings.Development.json  # Configurações de ambiente de desenvolvimento
appsettings.json  # Configurações globais da aplicação
global.json       # Configurações do SDK global
MegamanApi.csproj  # Arquivo de configuração do projeto
MegamanApi.sln    # Solução do projeto
Program.cs        # Arquivo principal da aplicação
Startup.cs        # Configuração de serviços e pipeline da aplicação
```

## 🚀 Endpoints da API

A API possui os seguintes endpoints:

### 🔹 Listar todos os chefes

**GET** `api/v1/robots`

**Resposta de Exemplo:**

```json
[
  {
    "Id": 1,
    "Code": "DLN/DRN-003",
    "Name": "Cutman",
    "HP": 150,
    "Picture": "https://vignette.wikia.nocookie.net/megaman/images/2/22/Cutman.png"
  }
]
```

---

### 🔹 Buscar chefe por ID

**GET** `api/v1/robots/{id}`

**Resposta de Exemplo (Sucesso):**

```json
{
  "Id": 1,
  "Code": "DLN/DRN-003",
  "Name": "Cutman",
  "HP": 150,
  "Picture": "https://vignette.wikia.nocookie.net/megaman/images/2/22/Cutman.png"
}
```

**Resposta de Exemplo (Erro):**

```json
{
  "message": "Nenhum robo encontrado"
}
```

---

### 🔹 Criar um novo chefe

**POST** `api/v1/robots`

**Resposta:**

```json
{
  "message": "Operação concluída com sucesso"
}
```

## 📌 Técnicas Utilizadas

- **Arquitetura MVC** (Model-View-Controller)
- **Entity Framework Core** para interação com banco de dados
- **Dependency Injection (DI)** para injeção de serviços
- **Tratamento de exceções** com retornos apropriados para a API
- **Serialização de JSON** com `Newtonsoft.Json`

## 🛠️ Como Executar o Projeto

### 🔹 Pré-requisitos

- [.NET Core 3.1 SDK](https://dotnet.microsoft.com/en-us/download/dotnet/3.1)
- [SQL Server](https://www.microsoft.com/pt-br/sql-server/sql-server-downloads)

### 🔹 Passos

1. Clone o repositório:
   ```sh
   git clone https://github.com/seuusuario/megaman-api.git
   ```
2. Acesse a pasta do projeto:
   ```sh
   cd megaman-api
   ```
3. Restaure as dependências:
   ```sh
   dotnet restore
   ```
4. Configure o banco de dados e aplique as migrações:
   ```sh
   dotnet ef database update
   ```
5. Inicie a API:
   ```sh
   dotnet run
   ```
6. A API estará disponível em `http://localhost:5000/api/v1/robots`

## 🤝 Guia de Contribuição

Se você deseja contribuir com este projeto, siga estas diretrizes:

1. **Fork o repositório** e clone-o localmente.
2. **Crie uma branch** para suas alterações:
   ```sh
   git checkout -b minha-feature
   ```
3. **Faça suas modificações** e siga boas práticas de código.
4. **Teste suas alterações** antes de enviar.
5. **Faça um commit e um push**:
   ```sh
   git commit -m "Adiciona minha nova feature"
   git push origin minha-feature
   ```
6. **Abra um Pull Request (PR)** e descreva suas mudanças.

A equipe revisará sua contribuição o mais rápido possível. Obrigado por ajudar a melhorar este projeto! 🚀

## 📜 Licença

Este projeto está licenciado sob a **MIT License** - veja o arquivo [LICENSE](LICENSE) para mais detalhes.

