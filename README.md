# Verial — Technical Case Study

## Project Overview
Verial is a New Zealand-focused two-sided services marketplace where customers discover, compare, and book local service providers. The platform is designed to improve trust and efficiency in local service transactions by combining provider verification, structured booking workflows, and marketplace-grade payment handling.

This repository presents a public technical case study of the product and engineering work. It is intended for employers, technical reviewers, and collaborators who want a clear view of system design and implementation approach without exposing production source code.

## Live Demo
The live platform is available at: **https://verial.co.nz**

## Technology Stack

### Frontend
- Next.js (App Router)
- React
- TypeScript
- Tailwind CSS

### Backend & Data
- Next.js server routes and server actions
- PostgreSQL (Neon)
- Drizzle ORM

### Platform & Integrations
- Clerk Authentication
- Stripe Connect (marketplace payments)
- Cloudflare R2 (file storage)
- Vercel (deployment)

### Tooling
- TypeScript-first development workflow
- Linting and quality checks
- Structured migrations for schema evolution

## Key Features
- Two-sided marketplace model for customers and providers
- Provider onboarding with profile and service setup
- Customer booking flow with discover → compare → request/book journey
- Region and suburb-based discovery tailored to New Zealand locations
- Provider dashboards for managing leads/bookings and service details
- Trust and verification systems to improve marketplace quality
- Admin dashboards for operational oversight
- Marketplace payment flows using Stripe Connect

## My Role
Damian is the founder and full-stack developer of Verial. Responsibilities include product architecture, feature design, frontend and backend implementation, database schema design, third-party integrations, and deployment operations.

## Architecture Overview
At a high level, Verial uses a modern full-stack web architecture:
- A Next.js frontend delivers responsive, server-rendered and client-interactive experiences.
- Backend logic is implemented through secure server-side APIs/actions.
- Persistent marketplace data is modeled in PostgreSQL via Drizzle ORM.
- Authentication and identity flows are handled through Clerk.
- Marketplace payouts and transaction flows are integrated through Stripe Connect.
- Media/file assets are stored in Cloudflare R2.
- Deployments are managed on Vercel with environment-specific configuration.

See [docs/architecture.md](docs/architecture.md) for a deeper architecture breakdown.

## Technical Challenges
Key engineering challenges included:
- Designing and operating a true two-sided marketplace model
- Implementing Stripe Connect payment and payout workflows
- Building secure and consistent authentication/authorization flows
- Designing a scalable schema for users, providers, bookings, and transactions
- Managing environment separation across development, staging, and production
- Maintaining product velocity while preserving reliability and trust

See [docs/challenges.md](docs/challenges.md) for detailed challenge write-ups.

## Screenshots
Product screenshots and visual walkthrough references are documented in [docs/screenshots](docs/screenshots/README.md).

## Source Code Privacy Note
The full production codebase is private because Verial is a live commercial platform. This repository is intentionally scoped as a technical case study to share architecture, engineering decisions, and product capabilities without exposing proprietary implementation details.
