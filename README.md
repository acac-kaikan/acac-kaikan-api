# ACAC Kaikan - API

API do sistema de gestão da associação. Veja a visão geral do projeto no [README da organização](https://github.com/acac-kaikan).

## Stack

- Java 21
- Spring Boot 4.1.1
- Spring Data JPA
- PostgreSQL
- Docker Compose
- Springdoc OpenAPI (`springdoc-openapi-starter-webmvc-ui`)
- Spring Boot Actuator
- Lombok

## Como rodar

### Pré-requisitos

- Java 21+
- Docker e Docker Compose

### 1. Configurar variáveis de ambiente

```bash
cp .env.exemplo .env
```

### 2. Subir o banco (PostgreSQL)

```bash
docker compose up -d
```

Confirme que `src/main/resources/application-dev.properties` aponta para o mesmo banco configurado no `.env`:

```properties
spring.datasource.url=jdbc:postgresql://localhost:5432/kaikan
spring.datasource.username=kaikan
spring.datasource.password=kaikan
```

### 3. Rodar a aplicação

```bash
./mvnw spring-boot:run
```

A API sobe em `http://localhost:8080`, com o Swagger em `http://localhost:8080/swagger-ui.html`.

## Padrões

Este repo segue os padrões de commit, branching e API definidos em [`acac-kaikan-docs`](https://github.com/acac-kaikan/acac-kaikan-docs):

- Commits: `docs/PADRONIZACAO_COMMITS.md`
- Branches: `docs/FLUXO_DE_DESENVOLVIMENTO.md` (`feat/nome-da-feature → dev → main`)
- Contrato de API: `docs/ENDPOINTS.md`

Detalhes completos em `acac-kaikan-docs/ENDPOINTS.md`.