## Jireh - Family Budget Tracker

**Project Description:**

A mobile and web budget app for tracking a family’s income and spending. The home screen shows income, expenses, and the remaining balance, and it accepts new transactions by amount, category, and date.

**GitHub Repository:** [Jireh](https://github.com/alexkimrow/Jireh)

---

### What it does

- Starts from a small set of sample transactions (food, utilities, and income)
- Adds a transaction after checking that the category is present and the amount is a non-zero number
- Deletes a transaction from the list
- Splits totals into income (positive amounts) and expenses (negative amounts), then shows balance as income minus expenses

Transaction state lives in the app session. The current build does not persist data to a server.

---

### Stack

- Expo SDK 57 and Expo Router
- React Native and TypeScript
- File-based tabs, with the budget screen in `src/app/index.tsx`
- Shared transaction types, a form component, and total helpers under `src/`
