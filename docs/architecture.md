# Architecture

This document provides a high-level technical architecture overview of Verial.

## 1) Frontend Architecture
Verial uses **Next.js (App Router)** with **React** and **TypeScript** to deliver the web application.

Core frontend characteristics:
- Server-rendered and client-interactive UI where appropriate
- Route-based application structure for public marketplace, authenticated user areas, and admin surfaces
- Reusable component patterns and utility-first styling with Tailwind CSS
- Type-safe data handling from API boundaries to UI rendering

The frontend is optimized for:
- Fast initial load for marketplace discovery pages
- Clear UX for complex booking and onboarding journeys
- Maintainable feature iteration across customer, provider, and admin interfaces

## 2) Backend APIs and Business Logic
Backend functionality is implemented through server-side APIs and business logic layers within the Next.js application.

Backend responsibilities include:
- Request validation and authorization checks
- Booking lifecycle orchestration
- Provider profile and onboarding management
- Administrative workflows and moderation operations
- Integration with external services (authentication, payments, file storage)

Design principles:
- Keep domain logic centralized and type-safe
- Separate external integration concerns from core marketplace logic
- Preserve clear boundaries between public actions and privileged operations

## 3) Database Structure
Verial uses **PostgreSQL (Neon)** with **Drizzle ORM**.

The data model supports a two-sided marketplace with entities such as:
- User identities and account roles
- Provider profiles and service offerings
- Customer booking requests and booking states
- Payment and transaction records
- Trust and verification metadata
- Geographic lookup data (region/suburb)

Schema design goals:
- Strong relational integrity for marketplace transactions
- Query efficiency for discovery and dashboard experiences
- Safe schema evolution through migration workflows

## 4) Authentication and Authorization
Authentication is handled through **Clerk**.

Security model highlights:
- Managed sign-in and account identity flows
- Session-based access to protected application areas
- Role-aware authorization for customer, provider, and admin capabilities
- Server-side checks for privileged operations

This approach reduces auth implementation risk while maintaining product-specific permission control.

## 5) Payment Integration
Verial uses **Stripe Connect** to support marketplace payments.

Payment architecture supports:
- Platform-level transaction orchestration
- Provider payout-compatible account flows
- Payment state alignment with booking states
- Transaction traceability for operational support

Implementation focus areas:
- Reliable reconciliation between booking and payment events
- Clear handling of payment success/failure edge cases
- Safe operational workflows for marketplace transactions

## 6) Deployment Architecture
Verial is deployed on **Vercel**.

Deployment characteristics:
- Environment-specific configurations for development/staging/production
- Secure handling of integration credentials through platform environment management
- Scalable hosting model for web and server-side workloads
- Production release workflows oriented toward reliability and quick rollback capability

## Summary
Verial combines a modern web stack with marketplace-specific architecture decisions:
- Next.js + React + TypeScript for product velocity and maintainability
- PostgreSQL + Drizzle for robust relational modeling
- Clerk for secure identity workflows
- Stripe Connect for marketplace payments
- Vercel for streamlined deployment and operations

The result is an architecture optimized for a trust-oriented, transaction-heavy marketplace domain.
