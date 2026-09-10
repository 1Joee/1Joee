# Portfolio Full-Stack — Joel Galera

Desarrollador full-stack (Córdoba, Argentina). Segundo año de Ingeniería/Tecnicatura
en Software. Acá resumo los dos proyectos full-stack en los que vengo trabajando,
el stack de cada uno y las aptitudes que fui aprendiendo en el proceso.

| Proyecto | Rol | Estado | Stack | Repo |
|---|---|---|---|---|
| **VIZIO — App de Turnos** | Full-stack (solo) | En producción / deploy-ready | Angular 21 · Node/Express · PostgreSQL · Prisma | https://github.com/1Joee/VIZIO |
| **Sistema Administrativo CACC** | Backend + QA en equipo | En desarrollo | .NET 10 Web API · Angular 22 · SQL Server | https://github.com/Atzur1/Sistema-Administrativo---CACC |

---

## 1. VIZIO — App de reserva de turnos para una barbería

App real para la barbería VIZIO (Córdoba). El cliente reserva turno desde una
landing con un wizard de 5 pasos; el barbero entra con login y gestiona la
agenda del día y sus ganancias.

### Stack

- **Frontend:** Angular 21 — standalone components, **signals**, modo **zoneless**, routing con guards
- **Backend:** Node.js + **Express** + **TypeScript**, arquitectura por capas (routes → controllers → services)
- **Base de datos:** PostgreSQL en **Supabase**
- **ORM:** **Prisma** (schema, migraciones versionadas, seed)
- **Auth:** **JWT** (expiración 24 h), contraseñas con **bcrypt**
- **Emails transaccionales:** **Resend** (confirmación al cliente + aviso al barbero elegido con copia al dueño)
- **Hardening:** **Helmet**, **express-rate-limit**, **CORS** restringido por origen
- **Deploy:** Frontend en **Vercel**, backend en **Railway**, variables de entorno separadas por plataforma

### Funcionalidades

- Wizard de reserva: servicio → barbero → día y horario → datos → confirmación
- Disponibilidad por barbero (dos turnos a la misma hora son válidos si son de barberos distintos)
- Agenda del día con estados de turno (pendiente / confirmado / atendido / cancelado)
- Resumen de ganancias del día y selector por mes, con desglose por servicio
- Validación de teléfono, identidad del cliente por teléfono único
- Emails automáticos al reservar

### Aptitudes que aprendí acá

- Diseñar y construir una app **full-stack de punta a punta** yo solo, para un cliente real
- **Modelado de datos relacional** con Prisma: relaciones, enums, índices, `@unique`, y por qué un constraint faltante hace que una reserva termine a nombre de otra persona
- **Migraciones de base de datos** con datos existentes: columnas nullable, consolidar duplicados antes de aplicar un constraint
- Escribir un **backend en capas** en Express/TypeScript, con manejo centralizado de errores (`async-handler`) y helpers de entorno tipados
- Implementar **autenticación con JWT** desde cero: firma, middleware de verificación, expiración, guard en el frontend
- **Angular moderno**: signals, zoneless, componentes standalone, servicios HTTP, pipes y mappers API↔modelo
- Integrar **servicios externos** (Resend) de forma tolerante a fallos (si falta la API key, se omite el envío en vez de romper)
- **Seguridad práctica**: secretos fuera del código, CORS por origen, rate limiting, headers con Helmet
- **Deploy real** en Vercel + Railway y config del engine de Prisma para el runtime Linux musl

---

## 2. Sistema Administrativo CACC — Club Atlético Camioneros

Plataforma web de gestión integral para el Club Atlético Camioneros: administración
financiera, control de socios y gestión deportiva, con portales separados por rol
(Administrativo, Deportivo, Comunidad). Proyecto en equipo; trabajé en el backend
y como **QA**.

### Stack

- **Backend:** **.NET 10** Web API en C#, solución de 3 proyectos con cadena de dependencias `ApiGestion → DaoLibrary → EntityLibrary`
- **Acceso a datos:** **ADO.NET** crudo (`Microsoft.Data.SqlClient`) con queries parametrizadas — sin ORM, sin EF
- **Base de datos:** **SQL Server** (autenticación Windows)
- **Frontend:** **Angular 22** — componentes standalone, TypeScript 6
- **Auth:** JWT
- **Tests:** **Vitest** (frontend)
- **Calidad:** Prettier; documentación técnica y de producto versionada (`AGENTS.md`, `estructura-tecnica.md`)

### Mi aporte

- Endpoints del backend (patrón controller `api/[controller]`, DAOs con SQL parametrizado)
- **QA**: testeo de UI y revisión de seguridad, documentado en `QA-BUGS-Y-SEGURIDAD.md`
  - Bugs de UI corregidos: asset del logo, ícono nativo del navegador tapando el toggle de contraseña (z-index + ocultar pseudo-elementos), suite de tests rota por un import inexistente, tests de scaffold sin actualizar, checkbox "Recordarme" y link de recuperación muertos
  - Hallazgos de seguridad: contraseñas en texto plano, contraseña de admin y clave de firma JWT hardcodeadas en archivos versionados

### Aptitudes que aprendí acá

- Trabajar en un **repo de equipo** con ramas por feature/fix, commits enlazados a bugs y coordinación con otros roles
- **C# / .NET**: arquitectura en capas, inyección de dependencias, configuración por `appsettings`, Swagger, CORS
- **SQL directo** con ADO.NET: conexiones, comandos parametrizados (y por qué la parametrización previene inyección SQL)
- Rol de **QA**: reproducir bugs, aislar la causa raíz, documentar estado y fix, validar la corrección antes de cerrar
- **Revisión de seguridad**: identificar y clasificar hallazgos por severidad, entender que quitar un secreto del código no lo borra del historial de git (hay que rotarlo), y usar `dotnet user-secrets` para mantener secretos fuera del repo
- Distinguir el **alcance de una rama de QA**: qué se arregla y qué se deriva al equipo de backend
- Mapear **historias de usuario** (HU-001 Login, HU-002/003 registros, HU-004 pagos) a implementación y deuda técnica

---

## Stack general — resumen

**Lenguajes:** TypeScript · JavaScript · C# · SQL · HTML/CSS

**Frontend:** Angular (21 y 22) — standalone components, signals, zoneless, routing, guards, formularios reactivos

**Backend:** Node.js/Express · ASP.NET Core (.NET 10) · arquitectura en capas · REST

**Bases de datos:** PostgreSQL · SQL Server · Prisma ORM · ADO.NET · modelado relacional · migraciones

**Auth & seguridad:** JWT · bcrypt · Helmet · rate limiting · CORS por origen · gestión de secretos (env, user-secrets)

**Infra / deploy:** Vercel · Railway · Supabase · variables de entorno por entorno

**Servicios externos:** Resend (emails transaccionales)

**Herramientas & práctica:** Git/GitHub (ramas, PRs, commits atómicos) · Vitest · Prettier · Swagger · QA y revisión de seguridad · documentación técnica

---

## Aptitudes transversales

- Llevar un proyecto **de la idea al deploy** para un cliente real
- Pensar en **casos borde y consistencia de datos**, no solo el happy path
- **Seguridad por defecto**: nunca secretos en el código, mínimo privilegio en CORS, hashing de contraseñas
- Trabajar tanto **solo** (VIZIO) como **en equipo con roles definidos** (CACC)
- **Documentar** decisiones técnicas para que otro las entienda meses después
