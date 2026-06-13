# Flaverso - Gamification System

## Purpose

The purpose of the Flaverso gamification system is to encourage reading consistency and long-term habit formation.

Gamification should never distract from reading.

It exists to reward meaningful reading behavior and celebrate reader growth.

---

# Core Principles

## Reading First

Reading is always the primary activity.

Rewards should appear after meaningful actions, not interrupt the reading experience.

---

## Consistency Over Volume

The system rewards consistency more than quantity.

Reading every day is more valuable than reading large amounts sporadically.

---

## Exploration Matters

Users should be encouraged to explore:

- New genres
- New authors
- New themes
- New literary worlds

---

## Positive Reinforcement

The system should celebrate achievements rather than punish inactivity.

There are no penalties for missing reading sessions.

---

# Progression System

## XP (Experience Points)

Users earn XP through reading-related activities.

XP contributes to:

- Levels
- Achievements
- Progress Tracking

---

# XP Sources

## Reading Time

| Action          |    XP |
| --------------- | ----: |
| Read 5 minutes  |  5 XP |
| Read 15 minutes | 15 XP |
| Read 30 minutes | 35 XP |
| Read 60 minutes | 80 XP |

---

## Reading Milestones

| Action                  |     XP |
| ----------------------- | -----: |
| First Reading Session   |  25 XP |
| First Chapter Completed |  20 XP |
| Book Completed          | 200 XP |
| Series Completed        | 500 XP |

---

## Engagement Actions

| Action                |       XP |
| --------------------- | -------: |
| Add Book to Library   |     5 XP |
| Complete Reading Goal |    50 XP |
| Unlock Achievement    | Variable |

---

# Level System

Levels represent the reader's journey.

---

## Reader Titles

| Level | Title              |
| ----- | ------------------ |
| 1     | Traveler           |
| 5     | Explorer           |
| 10    | Cartographer       |
| 20    | Guardian           |
| 35    | Architect          |
| 50    | Master of Flaverso |

---

## Level Formula

Initial implementation:

```text
Required XP = Level × 100
```

Example:

| Level | Total XP Required |
| ----- | ----------------: |
| 1     |                 0 |
| 2     |               100 |
| 3     |               300 |
| 4     |               600 |
| 5     |              1000 |

This formula may evolve in future releases.

---

# Reading Streaks

A streak represents consecutive days with reading activity.

---

## Rules

A streak increases when:

- User reads for at least 5 minutes

A streak does not increase when:

- No reading activity occurs

---

## Streak Milestones

| Days | Reward                |
| ---- | --------------------- |
| 7    | Achievement           |
| 30   | Rare Achievement      |
| 100  | Epic Achievement      |
| 365  | Legendary Achievement |

---

# Achievements

Achievements reward specific reader behaviors.

---

## First Steps

| Achievement      | Requirement                    |
| ---------------- | ------------------------------ |
| First Page       | Complete first reading session |
| First Book       | Complete first book            |
| First Collection | Add 10 books to library        |

---

## Consistency

| Achievement      | Requirement    |
| ---------------- | -------------- |
| One Week Strong  | 7-Day Streak   |
| Monthly Reader   | 30-Day Streak  |
| Reading Champion | 100-Day Streak |

---

## Exploration

| Achievement         | Requirement                |
| ------------------- | -------------------------- |
| Genre Explorer      | Read 5 genres              |
| World Traveler      | Read books from 10 authors |
| Literary Adventurer | Read 10 categories         |

---

## Collection

| Achievement   | Requirement        |
| ------------- | ------------------ |
| Collector I   | Complete 10 books  |
| Collector II  | Complete 50 books  |
| Collector III | Complete 100 books |

---

# Literary Worlds

Flaverso represents reading genres as discoverable worlds.

Users progress through worlds by reading books from those genres.

---

## Initial Worlds

| Genre            | World                |
| ---------------- | -------------------- |
| Fantasy          | Arcane Kingdom       |
| Science Fiction  | Orion Sector         |
| Mystery          | Shadow Archives      |
| Romance          | Garden of Emotions   |
| Classics         | Eternal Library      |
| Self Development | Academy of Knowledge |

---

# World Progress

Each completed book contributes progress to its world.

Example:

```text
Arcane Kingdom
██████████░░░░░░░░ 58%
```

Future releases may unlock:

- World achievements
- World titles
- World collections

---

# Reader Statistics

Users should be able to track:

- Books Completed
- Reading Sessions
- Total Reading Time
- Current Streak
- Longest Streak
- XP Earned
- Achievements Unlocked
- Favorite Genres

---

# Notifications

Notifications should encourage reading, not create pressure.

Examples:

- Reading streak reminders
- Achievement unlocked
- Goal completed
- New recommendation available

---

# Future Gamification Features

## Reading Goals

Examples:

- Read 15 minutes per day
- Finish 2 books per month

---

## Seasonal Events

Examples:

- Summer Reading Challenge
- Fantasy Month
- Mystery Week

---

## Community Challenges

Examples:

- Genre challenges
- Group reading goals
- Club achievements

---

# Design Guidelines

Gamification should feel:

- Motivating
- Rewarding
- Elegant
- Minimal

Gamification should never feel:

- Addictive
- Manipulative
- Distracting
- Competitive by default

---

# Guiding Principle

The goal is not to maximize screen time.

The goal is to help users read more, discover more, and grow as readers.
