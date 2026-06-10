# 💰 Budget Tracker

A lightweight, single-file personal budget tracker built with vanilla HTML, CSS, and JavaScript. No frameworks, no dependencies, no server required — just open the file in any browser and start tracking.

---

## 📐 Budgeting Method

This app uses the **50 / 15 / 25 / 10 budgeting method**:

| Category   | Target % | Purpose                                      |
|------------|----------|----------------------------------------------|
| Essentials | 50%      | Housing, utilities, groceries, transportation, insurance |
| Growth     | 15%      | Investing, emergency fund, courses           |
| Lifestyle  | 25%      | Dining out, entertainment, shopping, travel  |
| Savings    | 10%      | Short-term savings, sinking funds            |

> The percentages are **not static**. As you assign subcategory budgets, the live % updates automatically based on your actual allocations.

---

## ✨ Features

- **Apply Budget Targets** — enter your monthly net income and click the button to set a recommended pool for each category (50/15/25/10). Subcategories start at $0 so you decide how to distribute the money yourself.
- **Live % tracking** — category badges and the sidebar overview update in real time as you assign subcategory budgets.
- **Unallocated income tracker** — the sidebar shows exactly how much of your monthly income has not been assigned yet, with a suggestion to direct leftover funds toward Emergency Fund or Investing.
- **Hard income cap** — subcategory budgets are capped at your net monthly income. The app will alert you and auto-correct if you try to assign more than what's available.
- **Category pool bar** — each category card shows a progress bar of how much of the recommended pool has been assigned to subcategories, with a "left to assign" counter.
- **Editable subcategory names** — click any subcategory name to rename it. The expense dropdown updates automatically.
- **Expense logging** — add expenses by name, category, subcategory, amount, and date.
- **Transaction management** — all logged transactions appear in a table. Delete any transaction with the ✕ button; the app confirms before deleting and restores the balance.
- **Spent progress bar** — each category shows a bar of how much of the budget has been spent. Turns orange when over 100%.
- **Responsive layout** — sidebar collapses on mobile screens.

---

## 🚀 Getting Started

### Option 1 — Open directly
1. Download `budget-tracker.html`
2. Double-click the file to open it in your browser
3. No installation, no server, no dependencies needed

### Option 2 — VS Code + Live Server
1. Open the project folder in VS Code
2. Install the [Live Server extension](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)
3. Right-click `budget-tracker.html` → **Open with Live Server**
4. Edit the file and see changes reload instantly

---

## 🗂️ Project Structure

```
budget-tracker/
├── budget-tracker.html   # Complete app — HTML, CSS, and JS in one file
└── README.md             # Project documentation
```

Everything is intentionally bundled into a single HTML file so it works by double-clicking without a local server.

---

## 📖 How to Use

### Step 1 — Set your income
Enter your **monthly net income** in the Income Setup panel on the left sidebar.

### Step 2 — Apply Budget Targets
Click **Apply Budget Targets**. Each category receives its recommended pool:
- Essentials → 50% of income
- Growth → 15% of income
- Lifestyle → 25% of income
- Savings → 10% of income

Subcategories are reset to **$0** — you assign them yourself.

### Step 3 — Assign subcategory budgets
Type a dollar amount into each subcategory budget field. The category pool bar shows how much of the pool you've used. The sidebar shows how much income is still unallocated.

### Step 4 — Log expenses
Use the **Add Expense** form to record spending. Select the category and subcategory, enter a name, amount, and date, then click **Add Expense**.

### Step 5 — Track and adjust
- The **Overview** sidebar shows each bucket's live %, amount spent, and remaining balance.
- The **Unallocated Income** box shows how much is still unassigned.
- Delete transactions with the **✕** button. The balance restores automatically.

---

## ⚙️ Customization

All data lives in the `BD` array at the top of the `<script>` block inside `budget-tracker.html`. You can:

- **Rename categories** — change the `name` field in `BD`
- **Add or remove subcategories** — add/remove objects in the `subs` array
- **Change target percentages** — edit the `pct` value for each category (make sure all `pct` values add up to `1.0`)

Example:
```javascript
{name:"Essentials", pct:0.50, pool:0, subs:[
  {name:"Rent",           budget:0, spent:0},
  {name:"Utilities",      budget:0, spent:0},
  {name:"Groceries",      budget:0, spent:0}
]}
```

---

## 🛠️ Tech Stack

| Layer      | Technology                  |
|------------|-----------------------------|
| Markup     | HTML5                       |
| Styling    | CSS3 (custom properties, grid, flexbox) |
| Logic      | Vanilla JavaScript (ES5 compatible) |
| Fonts      | Inter (system fallback)     |
| Charts     | Native CSS progress bars    |

No npm, no build step, no external libraries.

---

## 📌 Notes

- Data is **not persisted** between page refreshes. All data resets when you close or refresh the browser tab.
- To save your data, consider adding `localStorage` in a future update.
- The app is fully functional offline once downloaded.

---

## 📄 License

MIT — free to use, modify, and distribute.
