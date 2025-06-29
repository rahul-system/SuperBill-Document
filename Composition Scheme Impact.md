# 🧾 GST Composition Scheme – Impact on Transactions

The GST Composition Scheme is a simplified tax regime for small businesses. This guide explains how it affects sales, purchases, ITC, and your billing software workflows, with practical examples and UI tips.

---

## 1. What is the Composition Scheme?
- **Eligibility:** Small taxpayers (turnover up to ₹1.5 crore; varies by state)
- **Tax Rate:** Lower, fixed rates (e.g., 1% for traders, 5% for restaurants)
- **Returns:** Simple quarterly returns (**GSTR-4**)
- **Restrictions:**
    - Cannot collect GST from customers
    - Cannot claim Input Tax Credit (ITC)

---

## 2. Impact on Sale Transactions
- **No GST on Invoice:** Cannot show or collect GST from customers
- **Invoice Format:** Must state:
  `Composition taxable person, not eligible to collect tax on supplies`
- **No Tax Breakdown:** Invoice only shows total value, not GST
- **E-way Bill:**
    - Required only for taxable goods
    - Will mention: **"Bill of Supply"** (not "Tax Invoice")
    - GST amount is not shown on the document

---

## 3. Impact on Purchase Transactions
- **No ITC Claim:** Cannot claim Input Tax Credit on purchases
- **Expense Booking:** GST paid on purchases is added to cost (not claimable)
- **RCM:**
    - Must pay GST under Reverse Charge if applicable
    - Cannot claim ITC on RCM paid

---

## 4. UI/Workflow Hints
- **Customer Invoice:**
    - Hide GST fields and tax breakdown
    - Add composition declaration on invoice
- **Purchase Entry:**
    - Disable ITC eligibility fields
    - Show warning: *No ITC claim allowed under Composition Scheme*
- **RCM Handling:**
    - Allow RCM flag, but show: *RCM tax paid is not claimable as ITC*

---

## 5. Example: Sale Invoice under Composition
| Field         | Value                                         |
|---------------|-----------------------------------------------|
| Invoice Type  | Sale (Composition)                            |
| GST Shown?    | ❌ No                                         |
| Declaration   | Composition taxable person...                 |
| ITC Allowed?  | ❌ No                                         |

---

## 6. Example: Purchase Entry under Composition
| Field         | Value                                         |
|---------------|-----------------------------------------------|
| GST Paid      | Yes (added to cost, not claimable)            |
| ITC Allowed?  | ❌ No                                         |
| RCM Paid      | Yes (if applicable, not claimable)            |

---

## 7. Pro Tips
- ✅ Check eligibility before opting for the scheme
- ⚠️ Do **not** collect GST from customers
- 📢 Always display the composition declaration on invoices
- ❌ Do **not** claim ITC in returns or software

---

**Reference:** [GST Composition Scheme – CBIC](https://www.cbic.gov.in/htdocs-cbec/gst/composition-scheme)