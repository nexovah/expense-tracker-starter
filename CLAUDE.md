# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
npm install      # install dependencies
npm run dev      # start dev server at http://localhost:5173
npm run build    # production build
npm run lint     # run ESLint
npm run preview  # preview production build
```

## Architecture

This is a single-file React app — all logic lives in `src/App.jsx`. There are no subcomponents, no routing, and no state management library.

**Known issues (intentional for the course):**
- `amount` is stored as a string, so `totalIncome` and `totalExpenses` use string concatenation instead of numeric addition — balance is wrong.
- "Freelance Work" is seeded as `type: "expense"` but categorized under `"salary"`, which is inconsistent.
- UI styling is minimal/poor by design.

**State in `App`:**
- `transactions` — array of `{ id, description, amount, type, category, date }`
- Form fields: `description`, `amount`, `type`, `category`
- Filter state: `filterType`, `filterCategory`

**Categories:** `food`, `housing`, `utilities`, `transport`, `entertainment`, `salary`, `other`
