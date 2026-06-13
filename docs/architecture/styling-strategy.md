# Flaverso - Styling Strategy

## CSS Architecture

Flaverso adopts a hybrid styling approach.

---

## Tailwind CSS

Used for:

- shadcn/ui components
- Layout utilities
- Responsive utilities
- Flex/Grid composition
- Utility-first styling

---

## Sass (SCSS)

Used for:

- Global styles
- Theme definitions
- Brand identity
- Complex styling
- Animations
- Layout exceptions

---

## Design Tokens

All visual decisions must be centralized through design tokens.

### Categories

- Colors
- Typography
- Spacing
- Radius
- Shadows
- Motion
- Breakpoints

### Location

```txt
packages/design-tokens/
```

---

## Theme System

Supported Themes:

- Light Theme
- Dark Theme

Future Themes:

- Seasonal Themes
- Premium Themes

---

## Styling Priority

1. Design Tokens
2. Tailwind Utilities
3. Component Variants
4. Sass Modules
5. Global Styles

---

## Component Strategy

### Base Components

Built with:

- shadcn/ui
- Radix UI

Examples:

- Button
- Input
- Select
- Dialog
- Tabs
- Dropdown

---

### Business Components

Built by Flaverso.

Examples:

- BookCard
- ReadingProgress
- AchievementCard
- LibraryShelf
- ReadingStats
- XPProgress
- StreakCounter

---

## Documentation

All reusable components must be documented in Storybook.
