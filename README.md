# Sales Backend (Node.js + TypeScript + Express + Prisma)

Resumen
-------
Backend ejemplo construido con Node.js (v24.x), TypeScript, Express y Prisma para PostgreSQL. Implementa Clean Architecture (capas: domain, application, infrastructure, presentation), patrón CQRS (separación comandos/queries), DTOs, validación, middlewares y buenas prácticas para CI/CD en GitHub Actions.

Tecnologías
-----------
- Node.js >= 24.15.0
- TypeScript
- Express
- Prisma + @prisma/client
- PostgreSQL (esquema: `sales`)
- tsyringe (DI), class-validator, class-transformer
- Helmet, cors, express-rate-limit, morgan
- Git + GitHub (Branching + Actions)

Estado
------
- Rama principal de desarrollo: `develop`
- Rama protegida de producción: `main`
- CI: GitHub Actions (jobs: `lint`, `prisma-generate`, `build`, `test`)

Estructura (resumen)
--------------------
- src/
  - domain/         (entidades, interfaces de repositorio)
  - application/    (casos de uso: commands / queries, DTOs)
  - infrastructure/ (Prisma client, implementaciones de repositorios)
  - presentation/   (controllers, routes)
  - middlewares/    (error handler, seguridad, validación)
  - shared/         (registro de dependencias)
  - server.ts, app.ts
- prisma/
  - schema.prisma
- .github/workflows/ci.yml

Requisitos previos
------------------
- Git instalado y acceso a tu repositorio en GitHub.
- Node.js v24.x (recomendado usar nvm o similar).
- PostgreSQL con la base de datos creada. Se usa el esquema `sales` (asegúrate de ajustar DATABASE_URL).
- Cuenta en GitHub para configurar secrets y protections.

Variables de entorno (ejemplo)
-----------------------------
Crea un archivo `.env` en local (NO subirlo al repo). Puedes usar `.env.example` como referencia.

Ejemplo `.env`: