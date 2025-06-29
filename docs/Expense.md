# 💸 Expense

Non-inventory costs such as travel, rent, software, etc.

---

## Key Features
- Category tracking
- Recurring setup
- Document attachment
- Budget monitoring
- Approval workflow

---

## Example Scenario
An employee pays for business travel airfare and submits an expense report. The finance department enters this as an expense in the system. Expenses can include utilities, travel, office supplies, etc.

---

## Flow Diagram
```mermaid
graph TD
    A[Start] --> B[Create Expense]
    B --> C[Select Category]
    C --> D[Enter Amount]
    D --> E{Recurring?}
    E -->|Yes| F[Set Schedule]
    E -->|No| G[One-time Entry]
    F --> H[Attach Documents]
    G --> H
    H --> I[Get Approval]
    I --> J[End]
```
