# Gelonezi ExplorerIO API

[![GitHub Repo](https://img.shields.io/badge/github-gelonezi%2Fexplorerio--api-blue)](https://github.com/gelonezi/explorerio-api)
[![.NET](https://img.shields.io/badge/.NET-9-blue)](https://dotnet.microsoft.com/)

The **Gelonezi ExplorerIO API** is a .NET 9 ASP.NET Core Web API that exposes ExplorerIO’s core functionality — access control, caching, file-listing and URL generation — via versioned RESTful endpoints. It delegates all storage operations to the ExplorerIO SDK, making it easy to swap in new providers.

---

## Features (coming soon)

- 🔐 **Access Control** Validate and enforce credentials via configurable authorization providers.
- ⚡ **Caching** In-memory and distributed caching for faster, more reliable responses.
- 🔌 **Service Integration** Plug-and-play storage backends (AWS S3, GCS, Dropbox, etc.) via the SDK.
- 📄 **Swagger & OpenAPI** Interactive API docs auto-generated at `/swagger`.

---

## Prerequisites

- [.NET 9 SDK](https://dotnet.microsoft.com/download)
- [Docker & Docker Compose](https://www.docker.com/) *(optional, for integration tests)*
- [Postman](https://postman.com/) *(optional, for running samples)*

---

## Development Setup

1. **Clone the repository**

    ```bash
    git clone https://github.com/gelonezi/explorerio-api.git
    cd explorerio-api
    ````

2. **Start dependent services**

    ```bash
    docker compose -f docker-compose/development.yaml up -d
    ```

3. **Run the API**

    ```bash
    cd src/Gelonezi.ExplorerIO.Api.WebApi
    dotnet run
    ```

    The API listens on `https://localhost:5001` and serves Swagger UI at `https://localhost:5001/swagger`.

4. **Load and run Postman collection**

    Import `samples/explorerio-api__postman.json` into Postman to try out the endpoints.

---

## Project Structure

```text
/src
  └─ Gelonezi.ExplorerIO.Api.Services # SDK wiring, options & DI registrations
  ├─ Gelonezi.ExplorerIO.Api.WebApi   # ASP.NET Core Web API project
/tests
  ├─ unit                             # Unit tests (no external dependencies)
  └─ integration                      # Integration tests (uses Docker Compose)
/samples
  └─ explorerio-api__postman.json     # Postman collection for manual testing
```

---

## Documentation & Contributions

Full documentation at [exploreriodocs.gelonezi.com](https://exploreriodocs.gelonezi.com).

Guidelines for Contributions is available in the full documentation.

---

*This README will evolve as the API grows, adding deep-dive guides, sample calls, and advanced configuration.*
