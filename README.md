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

- **The Stack:** Angular 21 (signals, zoneless, standalone components), Node.js, Express, TypeScript, PostgreSQL (Supabase), Prisma, JWT, Resend, deployed on Vercel + Railway.
- **The Solution:** Replaces phone-and-paper booking with a self-service flow that works 24/7. Clients book in a 5-step wizard (service → barber → day & time → details → confirmation), each barber has their own agenda and availability, and everyone gets an automatic confirmation email — the client and the chosen barber, with a copy to the owner. Barbers log in to see the day ordered by time and a per-service earnings breakdown by day and month. The result: fewer no-shows, no double-booking, and the owner has real numbers on the business instead of guesswork.

## Featured Project: Sistema Administrativo CACC — Sports Club Management

Web platform for the Club Atlético Camioneros: financial administration, member
control and sports management, with role-separated portals (Administrative, Sports,
Community). Team project — I work on the **backend** and as **QA**.

- **The Stack:** .NET 10 Web API (C#), layered solution (`ApiGestion → DaoLibrary → EntityLibrary`), raw ADO.NET with parameterized queries, SQL Server, Angular 22, JWT, Vitest.
- **The Solution:** Centralizes the club's administration, finances and sports management in one platform, with role-separated portals so administrative staff, coaches and members each see only what's relevant to them. Replaces spreadsheets with dues and payment tracking, member and staff records, and executive dashboards that give the board real KPIs (dues collected, overdue payments, active players) to make decisions.

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
