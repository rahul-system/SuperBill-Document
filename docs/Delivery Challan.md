# 🚚 Delivery Challan

A non-monetary document issued during goods transportation.

---

## Key Features
- E-way bill integration
- Stock tracking
- Multiple destinations
- Invoice conversion
- Transport details

---

## Example Scenario
A warehouse sends a bulk order to a retail store. A delivery challan is generated listing the items and quantities dispatched. This document is used to record legal movement of goods even if no sale is finalized.

---

## Flow Diagram
```mermaid
graph TD
    A[Start] --> B[Create Delivery Challan]
    B --> C[Add Items]
    C --> D[Enter Transport Details]
    D --> E{E-way Bill Required?}
    E -->|Yes| F[Generate E-way Bill]
    E -->|No| G[Skip E-way Bill]
    F --> H[Update Stock]
    G --> H
    H --> I[Print Challan]
    I --> J[End]
```
