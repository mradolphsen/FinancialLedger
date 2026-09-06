# Financial Ledger & Net Worth Tracker

A lightweight, single-file web application designed for tracking net worth, managing recurring expenses, and planning bill payments around paydays. All data is saved locally in your browser by default, with optional continuous sync to your private GitHub repository via the GitHub REST API.

---

## Key Features

* **Net Worth Tracking**
  * Tracks bank balances (assets) and credit card balances (liabilities) across custom monthly entries.
  * Displays automatic calculations for net worth and month-over-month financial changes.
  * Includes a high-level hero dashboard displaying current net worth and debt summaries.
* **Recurring Expense Directory**
  * Logs predictable monthly expenses, estimated due dates, and projected amounts.
* **Bill Payment Planner**
  * Interactive table to align bill due dates with target pay dates.
  * Drag-and-drop row reordering (`⠿`) to resequence payments around paycheck cycles.
  * Real-time "Paid" status toggles and custom notes.
* **Private GitHub Syncing**
  * Directly syncs state as a formatted JSON document to a designated repository path.
  * Uses fine-grained GitHub Personal Access Tokens (PAT) stored exclusively in `localStorage`.
* **Zero Dependencies & Single-File**
  * Built entirely using modern vanilla JavaScript, standard CSS custom properties, and HTML5.
  * Works fully offline without requiring a build step, server, or database backend.

---

## File Structure & Storage Architecture

Because the application runs completely client-side, state management is split between local storage and remote persistence:

```text
├── index.html                  # Everything: UI Markup, Styles, and Vanilla JS Logic
└── data/
    └── networth-data.json      # Target sync location on GitHub
