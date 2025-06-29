# 🔄 Purchase Return

Returning goods back to the supplier due to quality or excess.

---

## Key Features
- Original bill linking
- Quality documentation
- ITC reversal
- Vendor communication
- Stock adjustment

---

## Example Scenario
A bookstore receives a batch of books, but 10 copies are damaged. The bookstore returns these to the supplier. A purchase return transaction notes the returned items and typically generates a credit note from the supplier.

---

## Flow Diagram
```mermaid
graph TD
    A[Start] --> B[Select Purchase Invoice]
    B --> C[Choose Return Items]
    C --> D[Quality Report]
    D --> E[Generate Debit Note]
    E --> F[Update Stock]
    F --> G[Adjust ITC]
    G --> H[End]
```
