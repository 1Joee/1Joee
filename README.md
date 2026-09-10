# Hi there, I'm Joel Galera!

## About Me

I am a **Full Stack Developer** and this whole field is what I'm passionate about —
especially **server and infrastructure** work. I love building products that bring
real value to society, taking them from the idea all the way to production for a
real client, and doing it **without ever cutting corners on security**, which I
consider the most important part. I care as much about data consistency,
infrastructure and edge cases as I do about shipping features.

- **Currently:** Technical Support at **Encode S.A.**, while building **VIZIO**, a booking app now in production for a barbershop in Córdoba, Argentina (Angular + Node/Express + PostgreSQL).
- **Education:** Studying a *Software Development Technical Degree* — **100% merit-based scholarship** covering the full year.
- **Previously:** Shadowing internship at **Encode S.A.** — spent time alongside developers, Product Owner and Scrum roles, seeing how they work day to day.
- **Also:** Backend + QA on **Sistema Administrativo CACC**, a management platform for a sports club, built with a team (.NET 10 + Angular).

## Technical Stack

| Category | Tools & Technologies |
|---|---|
| **Frontend** | Angular (signals, zoneless, standalone components), TypeScript, JavaScript, HTML, CSS |
| **Backend & DB** | Node.js, Express, .NET 10 (C# / ASP.NET Core), PostgreSQL, SQL Server, Prisma, ADO.NET |
| **Infrastructure** | Vercel, Railway, Supabase, environment-based configuration |
| **Auth & Security** | JWT, bcrypt, Helmet, express-rate-limit, origin-restricted CORS, dotnet user-secrets |
| **Services & Tools** | Resend (transactional email), Git & GitHub, Swagger |
| **Quality & QA** | Vitest, manual QA, security review & vulnerability triage |

## Featured Project: VIZIO — Barbershop Booking App

Appointment booking app **in production** for the VIZIO barbershop (Córdoba, Argentina).
Clients book from a landing page; each barber logs in to manage their day and earnings.

- **The Stack:** Angular 21 (signals, zoneless, standalone components), Node.js, Express, TypeScript, PostgreSQL (Supabase), Prisma, JWT, Resend.
- **The Solution:** Per-barber availability — two appointments at the same time are valid as long as they belong to different barbers. Client identity is resolved by a **unique phone number**: without that constraint, two rows with the same phone made a booking resolve to whichever row Postgres picked, so the appointment showed up under the wrong person — fixed with a unique constraint plus a migration that consolidated the existing duplicates. Layered Express backend (routes → controllers → services) with centralized async error handling and typed environment helpers.
- **Extras:** 5-step booking wizard (service → barber → day & time → details → confirmation), barber dashboard with JWT-protected login, daily agenda with appointment states, earnings summary broken down by service and month, transactional emails to the client and to the chosen barber (with a copy to the owner). Frontend deployed on **Vercel**, backend on **Railway**.

## Featured Project: Sistema Administrativo CACC — Sports Club Management

Web platform for the Club Atlético Camioneros: financial administration, member
control and sports management, with role-separated portals (Administrative, Sports,
Community). Team project — I work on the **backend** and as **QA**.

- **The Stack:** .NET 10 Web API (C#), 3-project layered solution (`ApiGestion → DaoLibrary → EntityLibrary`), raw ADO.NET (`Microsoft.Data.SqlClient`) with parameterized queries — no ORM, no EF. SQL Server, Angular 22, Vitest, JWT.
- **My Role:** Backend endpoints (controller pattern `api/[controller]`, DAOs with parameterized SQL) and QA. QA work is documented in `QA-BUGS-Y-SEGURIDAD.md`: fixed UI bugs — a browser's native password icon overlapping the app's custom show/hide toggle (fixed with z-index + hiding the native pseudo-elements), a broken test suite caused by an import of a class that didn't exist, and a dead "remember me" checkbox now wired to `localStorage`.
- **Security Review:** Identified and classified findings by severity — plaintext passwords, a hardcoded admin password and a hardcoded JWT signing key committed in versioned files. Documented that removing a secret from the code does **not** remove it from git history (the key has to be treated as compromised and rotated), generated a new key and moved it to `dotnet user-secrets`, outside the repo.

## What I've Learned

- Building a **full-stack app end to end**, solo, for a real paying client
- **Relational data modeling** with Prisma — relations, enums, indexes, unique constraints, and why a missing one corrupts a booking
- **Database migrations over existing data** — nullable columns, consolidating duplicates before applying a constraint
- **JWT authentication from scratch** — signing, verification middleware, expiration, route guards on the frontend
- **Modern Angular** — signals, zoneless change detection, standalone components, HTTP services, API↔model mappers
- **Layered backends** in both Express/TypeScript and ASP.NET Core / C#
- **Parameterized raw SQL** with ADO.NET, and why parameterization prevents SQL injection
- **Practical security** — secrets out of code, least-privilege CORS, rate limiting, Helmet, password hashing
- **QA & security review** — reproducing bugs, isolating root cause, classifying findings by severity, validating the fix before closing
- **Real deployment** on Vercel + Railway, including Prisma engine config for the Linux musl runtime
- Working both **solo** and **on a team with defined roles**, using branches, PRs and atomic commits

## Let's Connect!

- **Email:** yoelgalera77@gmail.com
- **LinkedIn:** [joelgaleras](https://www.linkedin.com/in/joelgaleras/)
- **GitHub:** [1Joee](https://github.com/1Joee)
