# Flaverso - Backend Architecture

## Architecture Style

Backend For Frontend (BFF)

### Implementation

- NestJS
- Modular Monolith
- Prisma
- PostgreSQL

---

# Purpose

The BFF layer exists to provide frontend-optimized endpoints.

Instead of exposing internal domain structures directly, the BFF aggregates data into client-specific responses.

---

# Architecture Diagram

```text
Web
Mobile
Admin
    │
    ▼
    BFF
    │
    ▼
Domain Modules
    │
    ▼
 Prisma
    │
    ▼
PostgreSQL
```

---

# API Structure

```text
apps/api/src/

├── bff/
│   ├── home/
│   ├── library/
│   ├── profile/
│   ├── reader/
│   ├── explore/
│   └── admin/
│
├── modules/
│   ├── auth/
│   ├── users/
│   ├── books/
│   ├── reading/
│   ├── gamification/
│   ├── subscriptions/
│   └── settings/
│
├── shared/
│
└── main.ts
```

---

# Domain Modules

## Auth

### Responsibilities

- Authentication
- Authorization
- Session Management

---

## Users

### Responsibilities

- User Profiles
- User Preferences

---

## Books

### Responsibilities

- Catalog
- Categories
- Authors
- Ebook Assets

---

## Reading

### Responsibilities

- Reading Progress
- Reading Sessions
- Bookmarks
- Highlights
- Notes

---

## Gamification

### Responsibilities

- XP
- Levels
- Achievements
- Streaks
- Literary Worlds

---

## Subscriptions

### Responsibilities

- Billing
- Subscription Validation
- Access Control

---

## Settings

### Responsibilities

- Theme Preferences
- Notification Preferences
- Reading Preferences

---

# BFF Endpoints

## Home

```http
GET /bff/home
```

### Returns

- Continue Reading
- Daily Goal
- Recommendations
- Current Streak
- Current Level

---

## Library

```http
GET /bff/library
```

### Returns

- User Library
- Reading Statuses
- Reading Progress

---

## Profile

```http
GET /bff/profile
```

### Returns

- User Information
- Statistics
- Achievements
- Literary Worlds
- Subscription Status

---

## Reader

```http
GET /bff/reader/:bookId
```

### Returns

- Book Information
- Reading Progress
- Bookmarks
- Highlights
- Notes

---

## Explore

```http
GET /bff/explore
```

### Returns

- Featured Books
- Categories
- Recommendations
- New Releases

---

## Admin

```http
GET /bff/admin/*
```

### Returns

Administrative data required by the Admin Portal.

---

# Request Flow

```text
Frontend Request
        │
        ▼
BFF Controller
        │
        ▼
BFF Service
        │
        ▼
Domain Modules
        │
        ▼
Prisma
        │
        ▼
PostgreSQL
```

---

# Architectural Principles

## Frontend Isolation

Frontend applications must never communicate directly with domain modules.

---

## Domain Independence

Modules should remain independent and focused on a single business domain.

---

## Aggregated Responses

The BFF is responsible for aggregating and transforming data into frontend-friendly payloads.

---

## Single Source of Business Logic

Business rules must live inside domain modules.

The BFF must not contain business logic.

---

## Data Access

Database access is only allowed through Prisma repositories and services.

---

# Future Scalability

The architecture should support future extraction of modules into independent services without changing frontend APIs.

Example:

```text
Current

Web
Mobile
Admin
    │
    ▼
BFF
    │
    ▼
Modular Monolith

Future

Web
Mobile
Admin
    │
    ▼
BFF
    │
    ├── User Service
    ├── Book Service
    ├── Reading Service
    ├── Gamification Service
    └── Subscription Service
```

The BFF remains the public API surface regardless of internal implementation changes.

---

# Guiding Principle

The frontend should only know what data it needs.

The backend should decide how that data is composed.
