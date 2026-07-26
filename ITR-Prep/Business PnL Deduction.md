```python
equity_ocd = 7618.5706
fno_ocd = 177.0
comm_ocd = 118.0
total_dp = equity_ocd + fno_ocd + comm_ocd

print(f"Equity DP/Charges: {equity_ocd:.2f}")
print(f"FnO DP/Charges: {fno_ocd:.2f}")
print(f"Commodity DP/Charges: {comm_ocd:.2f}")
print(f"Total DP/Charges: {total_dp:.2f}")


```

```text
Equity DP/Charges: 7618.57
FnO DP/Charges: 177.00
Commodity DP/Charges: 118.00
Total DP/Charges: 7913.57


```

```python
import pandas as pd

data = [
    # Item, Equity, FnO, Commodity, Deductible_Pnl
    ("Brokerage", 1961.1478, 38240.0, 7884.1335, "Yes (Sec 37(1))"),
    ("STT / CTT", 6306.0, 19533.0, 2452.0, "Yes (Sec 36(1)(xv))"),
    ("Exchange Transaction Charges", 431.2623, 8533.1303, 2303.36, "Yes (Sec 37(1))"),
    ("GST (CGST + SGST + IGST)", 435.3009, 8475.2012, 1839.9603, "Yes (if ITC not claimed)"),
    ("SEBI Turnover Fees", 14.0054, 120.0879, 34.508, "Yes (Sec 37(1))"),
    ("Stamp Duty", 413.0, 1303.0, 368.88, "Yes (Sec 37(1))"),
    ("IPFT Charges", 11.9927, 191.2328, 0.0, "Yes (Sec 37(1))"),
    ("DP Charges", 7618.5706, 177.0, 118.0, "Yes (Sec 37(1))")
]

df = pd.DataFrame(data, columns=["Expense Head", "Equity", "FnO", "Commodity", "Deductible in P&L"])
df["Total"] = df["Equity"] + df["FnO"] + df["Commodity"]

# Format floats to 2 decimal places
formatted_df = df.copy()
for col in ["Equity", "FnO", "Commodity", "Total"]:
    formatted_df[col] = formatted_df[col].apply(lambda x: f"₹{x:,.2f}")

print(formatted_df.to_string(index=False))

total_eq = df["Equity"].sum()
total_fno = df["FnO"].sum()
total_comm = df["Commodity"].sum()
grand_total = df["Total"].sum()

print(f"\nTotals:")
print(f"Equity Total: ₹{total_eq:,.2f}")
print(f"FnO Total: ₹{total_fno:,.2f}")
print(f"Commodity Total: ₹{total_comm:,.2f}")
print(f"Grand Total: ₹{grand_total:,.2f}")


```

```text
                Expense Head    Equity        FnO Commodity        Deductible in P&L      Total
                   Brokerage ₹1,961.15 ₹38,240.00 ₹7,884.13          Yes (Sec 37(1)) ₹48,085.28
                   STT / CTT ₹6,306.00 ₹19,533.00 ₹2,452.00      Yes (Sec 36(1)(xv)) ₹28,291.00
Exchange Transaction Charges   ₹431.26  ₹8,533.13 ₹2,303.36          Yes (Sec 37(1)) ₹11,267.75
    GST (CGST + SGST + IGST)   ₹435.30  ₹8,475.20 ₹1,839.96 Yes (if ITC not claimed) ₹10,750.46
          SEBI Turnover Fees    ₹14.01    ₹120.09    ₹34.51          Yes (Sec 37(1))    ₹168.60
                  Stamp Duty   ₹413.00  ₹1,303.00   ₹368.88          Yes (Sec 37(1))  ₹2,084.88
                IPFT Charges    ₹11.99    ₹191.23     ₹0.00          Yes (Sec 37(1))    ₹203.23
                  DP Charges ₹7,618.57    ₹177.00   ₹118.00          Yes (Sec 37(1))  ₹7,913.57

Totals:
Equity Total: ₹17,191.28
FnO Total: ₹76,572.65
Commodity Total: ₹15,000.84
Grand Total: ₹108,764.77


```

Here is the updated consolidation with DP charges reallocated to Equity (₹7,618.57), F&O (₹177.00), and Commodities (₹118.00), along with statutory deductibility rules for Income Tax filing.

---

### 1. Updated Consolidated Summary Table

| Charge / Expense Head | Equity (₹) | FnO (₹) | Commodity (₹) | Total Amount (₹) | Applicable for Deduction? |
| --- | --- | --- | --- | --- | --- |
| **Brokerage** | 1,961.15 | 38,240.00 | 7,884.13 | **48,085.28** | **Yes** (Sec 37(1)) |
| **STT / CTT** | 6,306.00 | 19,533.00 | 2,452.00 | **28,291.00** | **Yes** (Sec 36(1)(xv)) |
| **Exchange Transaction Charges** | 431.26 | 8,533.13 | 2,303.36 | **11,267.75** | **Yes** (Sec 37(1)) |
| **GST (CGST + SGST + IGST)** | 435.30 | 8,475.20 | 1,839.96 | **10,750.46** | **Yes** (if ITC not claimed) |
| **DP Charges** *(re-classified)* | 7,618.57 | 177.00 | 118.00 | **7,913.57** | **Yes** (Sec 37(1)) |
| **Stamp Duty** | 413.00 | 1,303.00 | 368.88 | **2,084.88** | **Yes** (Sec 37(1)) |
| **IPFT Charges** | 11.99 | 191.23 | 0.00 | **203.23** | **Yes** (Sec 37(1)) |
| **SEBI Turnover Fees** | 14.01 | 120.09 | 34.51 | **168.60** | **Yes** (Sec 37(1)) |
| **Clearing Charges** | 0.00 | 0.00 | 0.00 | **0.00** | N/A |
| **Total Segment Expenses** | **17,191.28** | **76,572.65** | **15,000.84** | **108,764.77** | **100% Deductible** |

---

### 2. Standalone Business P&L Expense Statement (For ITR-3 / Schedule BP Entry)

Use these consolidated figures directly on the debit side of your Trading / Business Profit & Loss statement:

```text
================================================================================
BUSINESS PROFIT & LOSS STATEMENT - DIRECT TRADING EXPENSES
================================================================================
Expense Head                                                 Amount (in INR)
--------------------------------------------------------------------------------
1. Brokerage Charges                                              48,085.28
2. Securities & Commodities Transaction Tax (STT / CTT)            28,291.00
3. Exchange Transaction Charges                                   11,267.75
4. Goods and Services Tax (GST Paid)                              10,750.46
5. Depository Participant (DP) Charges                             7,913.57
6. Stamp Duty                                                      2,084.88
7. Investor Protection Fund Trust (IPFT) Charges                     203.23
8. SEBI Turnover Charges                                             168.60
--------------------------------------------------------------------------------
TOTAL DIRECT EXPENSES CLAIMABLE IN P&L                            ₹1,08,764.77
================================================================================

```

---

### Important Tax Compliance Notes for ITR Filing

* **STT / CTT Deductibility:** Under **Section 36(1)(xv)** of the Income Tax Act, STT/CTT is allowed as a business deduction when trading profits/losses are declared under **Business Income (P&L)**.
* **DP Charges:** Reclassified from "Other Credits & Debits", these are allowed under **Section 37(1)** as direct business expenses incurred for holding and transferring securities.
* **GST Treatment:** If you do not hold a GST registration to claim Input Tax Credit (ITC), the entire ₹10,750.46 is deductible as a direct expense.
