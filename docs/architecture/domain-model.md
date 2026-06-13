# Flaverso - Domain Model

## Purpose

This document defines the core business entities, relationships, and domain rules of the Flaverso platform.

It serves as the source of truth for:

- Product
- Backend
- Frontend
- Database Design
- API Design

---

# Domain Overview

Flaverso is built around four core domains:

```text
Users
Books
Reading
Gamification
```

Supporting domains:

```text
Subscriptions
Catalog
Settings
```

---

# Domain Diagram

```text
User
 │
 ├── Subscription
 │
 ├── LibraryBook
 │       │
 │       └── Book
 │
 ├── ReadingSession
 │
 ├── ReadingProgress
 │
 ├── AchievementUnlock
 │
 ├── UserLevel
 │
 └── UserWorldProgress
```

---

# User Domain

Represents a platform user.

## User

### Properties

```typescript
id;
name;
email;
passwordHash;
avatarUrl;
level;
xp;
currentStreak;
longestStreak;
createdAt;
updatedAt;
```

### Rules

- Email must be unique.
- XP cannot be negative.
- Level is calculated from XP.
- Users must have an active subscription to access books.

---

# Architectural Context

The domain model is consumed through a Backend For Frontend (BFF) layer.

The BFF is responsible for:

- Aggregating data from multiple domains
- Optimizing payloads for frontend clients
- Reducing frontend requests
- Isolating frontend applications from domain implementation details

Clients:

- Web Application
- Mobile Application
- Admin Portal

# Subscription Domain

Represents user access to the platform.

## Subscription

### Properties

```typescript
id;
userId;
plan;
status;
startedAt;
expiresAt;
createdAt;
updatedAt;
```

### Plans

```text
MONTHLY
YEARLY
```

### Status

```text
ACTIVE
CANCELED
EXPIRED
PAST_DUE
```

### Rules

- Only one active subscription per user.
- Subscription controls access to premium content.

---

# Catalog Domain

Represents the available book collection.

## Author

### Properties

```typescript
id;
name;
bio;
photoUrl;
createdAt;
updatedAt;
```

---

## Category

### Properties

```typescript
id;
name;
slug;
description;
```

### Examples

```text
Fantasy
Romance
Mystery
Science Fiction
Classics
Self Development
```

---

## Book

### Properties

```typescript
id;
title;
description;
coverUrl;
language;
pageCount;
publishedAt;
authorId;
createdAt;
updatedAt;
```

### Relationships

```text
Book
 ├── Author
 ├── Categories
 └── EbookAsset
```

---

## EbookAsset

Represents a digital file.

### Properties

```typescript
id;
bookId;
format;
fileUrl;
fileSize;
createdAt;
```

### Formats

```text
EPUB
PDF
```

---

# Library Domain

Represents a user's personal collection.

## LibraryBook

### Properties

```typescript
id;
userId;
bookId;
status;
addedAt;
updatedAt;
```

### Status

```text
WANT_TO_READ
READING
COMPLETED
FAVORITE
```

### Rules

- A user can only have one library entry per book.
- Status can change over time.

---

# Reading Domain

Tracks reading activity.

## ReadingProgress

### Properties

```typescript
id;
userId;
bookId;
currentPage;
progressPercentage;
lastReadAt;
createdAt;
updatedAt;
```

### Rules

- Progress is automatically updated.
- Progress cannot exceed 100%.

---

## Bookmark

### Properties

```typescript
id;
userId;
bookId;
page;
createdAt;
```

---

## Highlight

### Properties

```typescript
id;
userId;
bookId;
content;
location;
createdAt;
```

---

## Note

### Properties

```typescript
id;
userId;
bookId;
content;
location;
createdAt;
updatedAt;
```

---

## ReadingSession

Tracks active reading behavior.

### Properties

```typescript
id;
userId;
bookId;
startedAt;
endedAt;
duration;
pagesRead;
xpEarned;
```

### Rules

- Session duration generates XP.
- Sessions contribute to streaks.

---

# Gamification Domain

Tracks progression and rewards.

## Achievement

### Properties

```typescript
id;
name;
description;
icon;
xpReward;
category;
```

### Categories

```text
FIRST_STEPS
CONSISTENCY
EXPLORATION
COLLECTION
SPECIAL
```

---

## AchievementUnlock

Represents unlocked achievements.

### Properties

```typescript
id;
userId;
achievementId;
unlockedAt;
```

### Rules

- A user can unlock an achievement only once.

---

## XPEvent

Tracks all XP sources.

### Properties

```typescript
id;
userId;
source;
amount;
createdAt;
```

### Sources

```text
READING_SESSION
BOOK_COMPLETION
ACHIEVEMENT
GOAL_COMPLETION
SPECIAL_EVENT
```

---

## UserLevel

Represents level progression.

### Properties

```typescript
level;
requiredXp;
title;
```

### Initial Titles

```text
1  Traveler
5  Explorer
10 Cartographer
20 Guardian
35 Architect
50 Master of Flaverso
```

---

# Literary Worlds Domain

Represents genre exploration.

## World

### Properties

```typescript
id;
name;
description;
icon;
categoryId;
```

### Examples

```text
Arcane Kingdom
Orion Sector
Shadow Archives
Garden of Emotions
Eternal Library
Academy of Knowledge
```

---

## UserWorldProgress

### Properties

```typescript
id;
userId;
worldId;
progress;
updatedAt;
```

### Rules

- Reading books contributes to world progress.
- Progress ranges from 0 to 100.

---

# Settings Domain

Stores user preferences.

## UserSettings

### Properties

```typescript
id;
userId;
theme;
notificationsEnabled;
dailyReminderEnabled;
readingGoalMinutes;
updatedAt;
```

### Theme

```text
LIGHT
DARK
SYSTEM
```

---

# Domain Events

These events may trigger side effects.

## Reading Events

```text
BOOK_STARTED
BOOK_COMPLETED
SESSION_STARTED
SESSION_ENDED
PAGE_REACHED
```

---

## Gamification Events

```text
XP_EARNED
LEVEL_UP
ACHIEVEMENT_UNLOCKED
STREAK_UPDATED
```

---

## Subscription Events

```text
SUBSCRIPTION_CREATED
SUBSCRIPTION_RENEWED
SUBSCRIPTION_EXPIRED
```

---

# Business Rules

## Reading

- Users must have access to read books.
- Progress is saved automatically.
- Reading sessions generate XP.

---

## Progression

- XP determines level.
- Levels unlock titles.
- Achievements provide rewards.

---

## Library

- Books can exist only once per user library.
- Status transitions are allowed.

---

## Subscription

- Active subscription required for content access.
- Expired subscriptions lose reading access.

---

# MVP Entities

The following entities are required for MVP implementation:

```text
User
Subscription

Author
Category
Book
EbookAsset

LibraryBook
ReadingProgress
ReadingSession

Achievement
AchievementUnlock
XPEvent

UserSettings
```

---

# Future Entities

Planned for future releases:

```text
Review
Rating
ReadingClub
Comment
Challenge
Audiobook
AuthorPortal
RecommendationEngine
NotificationCenter
```
