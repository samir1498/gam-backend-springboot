# Green Algeria Map — Spring Boot API

Standalone Spring Boot 4 / Java 25 implementation of the GAM API. One of four
implementations (`NestJS` in `green-algeria-map`, `Go` in `gam-backend-go`,
`Laravel` in `gam-laravel`) that all obey `gam-contract`.

This is a real repo, not a benchmark fixture: own CI, own Dockerfile, own image.

## Run the full app

```bash
git submodule update --init --recursive
docker compose up --build
# UI   http://localhost:3000
# API  http://localhost:8081
```

The `frontend/` submodule is the single copy of the GAM UI from `gam-frontend`.
Do not edit it here; change it there and bump the pointer.

## Run the API only

```bash
./mvnw spring-boot:run          # port 8081
./mvnw test -Ptest-unit
./mvnw test -Ptest-it
```

## Scope

Implements the contract surface: auth, zones, damage reports, storage. It does
not chase every NestJS feature — pin a contract version, pass conformance, ship.

## Image

Tag `v*` builds and pushes `ghcr.io/samir1498/gam-backend-springboot`.
