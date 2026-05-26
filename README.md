# CONSTRUCT Edge Backend

Spring Boot backend for the CONSTRUCT Edge frontend, based on the app's ER schema.

## Features
- Spring Boot REST API
- JPA entities for `Admin`, `Role`, `Employee`, `Manager`, `Project`, `Customer`, `Inventory`, and `Material`
- In-memory H2 database for quick local testing
- Cross-origin support for frontend integration

## Run
Requires Java 21 and a Gradle installation.

By default the project is configured to connect to a local MySQL server. Example credentials used for development:

- host: `localhost`
- port: `3306`
- database: `constructedge` (auto-created if missing)
- username: `root`
- password: `root`

Start the app with Gradle:

```bash
cd backend
./gradlew bootRun
```

If you do not have Gradle installed, the included Gradle wrapper will download what it needs.

The default local profile uses an embedded H2 database. To use MySQL, run with the `mysql` profile:

```bash
./gradlew bootRun --args='--spring.profiles.active=mysql'
```

If you prefer Maven, add a `pom.xml` or install Maven and use the generated build file with your own setup.

## API Endpoints
- `GET /api/employees`
- `GET /api/projects`
- `GET /api/customers`
- `GET /api/inventory`
- `GET /api/materials`
- `GET /api/admins`
- `GET /api/roles`
- `GET /api/managers`

The H2 console is available at `/h2-console` while the app is running.
