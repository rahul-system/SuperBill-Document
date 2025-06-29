# 🧾 GST Tax Options – Input Tax Credit (ITC) & Reverse Charge Explained

This guide explains when you can claim **Input Tax Credit (ITC)** for GST paid on purchases, and how to handle Reverse Charge Mechanism (RCM) and edge cases. It’s designed for both developers and business users.

---

## 1. ITC Eligibility Types

### ✅ Eligible for ITC – Input
- **Purpose:** General business use (goods or services)
- **Claimable:** ✅ Yes
- **Use case:** Inventory, raw materials, or service inputs

### ✅ Eligible for ITC – Goods
- **Purpose:** Specifically for **goods** used in business
- **Claimable:** ✅ Yes
- **Use case:** Goods for resale, manufacturing, etc.

### ❌ Ineligible – Section 17(5)
- **Purpose:** Blocked credits under CGST Act
- **Claimable:** ❌ No
- **Examples:**
  - Motor vehicles (unless for transport business)
  - Food & beverages
  - Club memberships
  - Employee travel
  - Construction for immovable property (in many cases)

### ❌ Ineligible – Other
- **Purpose:** Non-claimable due to supplier type or use case
- **Claimable:** ❌ No
- **Use case:**
  - From a **composition dealer**
  - Non-business use
  - Charitable organization purchases

---

## 2. Quick Reference Table

| Tax Option                    | Can Claim ITC? | Typical Use Case                     |
|------------------------------|----------------|--------------------------------------|
| ✅ Eligible for ITC – Input   | Yes            | Business use (goods/services)        |
| ✅ Eligible for ITC – Goods   | Yes            | Business use (goods only)            |
| ❌ Ineligible – Section 17(5) | No             | Blocked items (vehicles, food, etc.) |
| ❌ Ineligible – Other         | No             | Non-business, exempt supply, etc.    |

---

## 3. ITC Calculation Example

| Item   | Price/Unit | Qty | GST % | GST Amt | Total With GST |
|--------|------------|-----|-------|---------|----------------|
| Laptop | ₹50,000    | 1   | 18%   | ₹9,000  | ₹59,000        |

- **Claimable ITC:** ₹9,000
- When filing GST return, deduct ₹9,000 from output GST liability.
- You only bear the base cost of ₹50,000 in your books.

---

## 4. Reverse Charge Mechanism (RCM)

**What is RCM?** Under GST, Reverse Charge means the **recipient** pays GST instead of the supplier. Applies to notified goods/services or unregistered vendors.

- **When does it apply?** E.g., legal services, import of goods/services, or from unregistered suppliers.
- **Accounting Impact:**
    - GST paid by buyer directly to government
    - ITC claimable only after payment
    - Special reporting & compliance
- **Workflow Impact:**
    - System should flag such invoices as RCM
    - Payment & ITC claim tracked separately
    - Additional validations for RCM

### RCM Example
- You hire a **Goods Transport Agency (GTA)**
- Invoice value = ₹10,000
- GST @ 5% under RCM = ₹500

| Step            | Who Pays? | GST Amt | Claim ITC? |
|-----------------|-----------|---------|------------|
| GST under RCM   | You       | ₹500    | ✅ Yes      |
| Input Tax Credit| You       | ₹500    | ✅ Claimed  |

- You pay ₹500 to govt as GST under RCM
- You can **claim ₹500 as ITC** to offset future tax

---

## 5. Edge Cases: ITC Reversal Scenarios

You **must reverse ITC** in certain cases (i.e., give it back partially or fully):

| Reason                                 | GST Action             | ITC Allowed? |
|----------------------------------------|------------------------|--------------|
| Non-payment to vendor in 180 days      | Reverse ITC + interest | ❌           |
| Goods/services partly for personal use | Proportionate reversal | 🔁 Partial   |
| Credit note issued by supplier         | Reduce ITC             | 🔁 Adjusted  |
| Switch to Composition Scheme           | Reverse full ITC       | ❌           |
| Exempt outward supply increases        | Reverse proportionally | 🔁 Partial   |

⚠️ If payment to vendor not made within 180 days, ITC must be reversed with interest (Rule 37).

---

## 6. Partial Credit (Apportionment)

When goods/services are used for **both business and non-business** or **taxable and exempt** supplies, ITC is claimed **partially**.

**Formula (Rule 42 & 43):**
Eligible ITC = Total ITC × (Taxable Turnover ÷ Total Turnover)

Example:
- Total ITC = ₹10,000
- Taxable Turnover = ₹80,000
- Total Turnover = ₹100,000
- ➡️ Eligible ITC = ₹10,000 × 80% = ₹8,000

💡 *UI Tooltip: Only ₹8,000 ITC allowed as proportionate credit based on taxable supply ratio (Rule 42).*

---

## 7. Inter-State Purchases (IGST)

When you buy from a different state, IGST is charged. IGST is **fully claimable** as ITC.

Example:
- Buy machinery from Gujarat, invoice shows IGST ₹18,000
- You’re in Karnataka, GSTIN: 29XXXXX...
- ✅ You can claim ₹18,000 as ITC in GSTR-3B under ITC on Import of Goods/Services (IGST)

💡 *UI Tooltip: Inter-state purchases attract IGST. Entire IGST is claimable under Input Tax Credit (IGST).*

---

## 8. Integration-Ready UI Labels & Hints

| Field Name        | Suggested Label           | Tooltip / Hint                                                                 |
|-------------------|--------------------------|-------------------------------------------------------------------------------|
| gst_type          | GST % & ITC Eligibility  | Select applicable GST and whether ITC can be claimed (e.g., 18%, Eligible ITC) |
| rcm_flag          | Reverse Charge (RCM)?    | Tick if GST is to be paid by buyer under RCM. ITC will still be allowed.       |
| partial_itc       | Partial ITC Eligible (%) | Enter % of invoice amount eligible for ITC (e.g., 70%) for partial use.        |
| reverse_itc_flag  | Reverse Claimed ITC?     | Toggle if ITC reversal needed due to vendor payment delay or tax scheme change.|
| inter_state_flag  | Inter-State Purchase     | Mark if vendor is from another state. IGST will apply.                         |

---

## 9. Final Pro Tips

- 🔄 Always reconcile GSTR-2B with Purchase Register before claiming ITC.
- ⚠️ Don't claim ITC on blocked goods/services (Section 17(5)).
- 📅 File on time: Delayed returns = lost ITC (Section 16(4) time limit).
