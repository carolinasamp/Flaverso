# Flaverso - Information Architecture

## Purpose

This document defines the information architecture, navigation structure, and primary user flows for the Flaverso MVP.

Its purpose is to align Product, Design, Frontend, and Backend teams before wireframing and implementation.

---

# Navigation Structure

## Mobile Navigation

Primary navigation consists of five sections:

```text
Home
Library
Read
Explore
Profile
```

---

## Desktop Navigation

Primary navigation:

```text
Home
Library
Explore
Profile
```

Secondary actions:

```text
Search
Notifications
Settings
```

The Reader experience is launched from the Library or Book Details page.

---

# Sitemap

```text
Flaverso

├── Authentication
│   ├── Login
│   ├── Sign Up
│   ├── Forgot Password
│   └── Reset Password
│
├── Onboarding
│   ├── Welcome
│   ├── Reading Preferences
│   └── Favorite Genres
│
├── Home
│   ├── Continue Reading
│   ├── Daily Goal
│   ├── Recommendations
│   ├── New Releases
│   └── Categories
│
├── Explore
│   ├── Search
│   ├── Categories
│   ├── Authors
│   └── Book Details
│
├── Library
│   ├── All Books
│   ├── Want to Read
│   ├── Currently Reading
│   ├── Completed
│   └── Favorites
│
├── Reader
│   ├── Reading Session
│   ├── Bookmarks
│   ├── Highlights
│   └── Notes
│
├── Profile
│   ├── Statistics
│   ├── Achievements
│   ├── Reading Worlds
│   └── Subscription
│
└── Settings
    ├── Account
    ├── Appearance
    ├── Notifications
    └── Privacy
```

---

# Screen Definitions

## Authentication

### Login

Purpose:

Allow existing users to access the platform.

Actions:

- Login
- Navigate to Sign Up
- Forgot Password

---

### Sign Up

Purpose:

Create a new account.

Fields:

- Name
- Email
- Password

Actions:

- Create Account

---

# Onboarding

### Welcome

Purpose:

Introduce Flaverso.

Actions:

- Continue

---

### Reading Preferences

Purpose:

Personalize recommendations.

Examples:

- Fantasy
- Romance
- Mystery
- Science Fiction
- Classics

---

# Home

### Purpose

Provide a personalized dashboard.

---

### Sections

#### Continue Reading

Quick access to current books.

---

#### Daily Goal

Current progress toward reading goal.

---

#### Recommended For You

Personalized recommendations.

---

#### New Releases

Recently added books.

---

#### Categories

Genre shortcuts.

---

# Explore

### Purpose

Help users discover books.

---

### Search

Capabilities:

- Title
- Author
- Genre

---

### Categories

Examples:

- Fantasy
- Romance
- Mystery
- Science Fiction
- Classics

---

### Authors

Author discovery.

---

### Book Details

Displays:

- Cover
- Title
- Author
- Description
- Categories
- Reading Status
- Add to Library

---

# Library

### Purpose

Organize personal reading activity.

---

### Sections

#### All Books

Every book saved by the user.

---

#### Want to Read

Books planned for future reading.

---

#### Currently Reading

Active reading sessions.

---

#### Completed

Finished books.

---

#### Favorites

User-curated collection.

---

# Reader

### Purpose

Provide a distraction-free reading experience.

---

### Reader Layout

Content should occupy most of the screen.

Navigation controls should remain minimal.

---

### Reader Features

- Resume Reading
- Bookmark Page
- Highlight Text
- Create Notes
- Track Progress

---

# Profile

### Purpose

Track growth and progression.

---

### Sections

#### Reader Identity

Displays:

- Avatar
- Name
- Reader Title
- Current Level

---

#### Statistics

Displays:

- Books Completed
- Reading Time
- Current Streak
- Longest Streak

---

#### Achievements

Displays:

- Unlocked Achievements
- Progress Toward Next Achievement

---

#### Reading Worlds

Displays progress by literary genre.

Example:

```text
Arcane Kingdom .......... 58%
Orion Sector ............ 22%
Eternal Library ......... 41%
```

---

#### Subscription

Displays:

- Current Plan
- Renewal Date
- Billing Information

---

# Settings

### Account

- Update Profile
- Change Password

---

### Appearance

- Light Theme
- Dark Theme

---

### Notifications

- Reading Reminders
- Achievement Notifications

---

### Privacy

- Data Management
- Account Deletion

---

# Primary User Flow

## First-Time User

```text
Sign Up
    ↓
Onboarding
    ↓
Select Genres
    ↓
Home
    ↓
Explore Books
    ↓
Book Details
    ↓
Add to Library
    ↓
Start Reading
    ↓
Earn XP
```

---

# Returning User Flow

```text
Login
    ↓
Home
    ↓
Continue Reading
    ↓
Reader
    ↓
Progress Saved
    ↓
Achievement Unlocked
```

---

# Navigation Principles

## Reading First

The shortest path should always lead users back to reading.

---

## Minimal Friction

Users should be able to start reading within two taps.

---

## Consistent Structure

Navigation patterns should remain predictable throughout the platform.

---

## Progressive Discovery

Advanced features should be introduced gradually as users engage with the platform.

---

# MVP Rule

If a screen does not directly support:

- Reading
- Discovery
- Organization
- Progression

it should not be included in the MVP.

# Client Applications

## Web

Reader-facing application.

Features:

- Discovery
- Reading
- Progress Tracking
- Gamification

---

## Mobile

Reader-facing mobile application.

Features:

- Reading
- Offline Reading (Future)
- Progress Tracking

---

## Admin

Internal administration portal.

Features:

- Catalog Management
- Author Management
- User Management
- Subscription Monitoring
- Analytics
