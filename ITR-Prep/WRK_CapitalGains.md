Great. We're now moving from **Business Income** to **Capital Gains**, which is the second major tax working paper. By the time we finish this sheet, about **70% of your ITR computation** will be complete.

---

# Working Paper 3 — `WRK_CapitalGains`

## Objective

Answer one question:

> **What are the Capital Gains/Losses to report in Schedule CG?**

This sheet **must not** include:

* F&O
* Commodity
* Intraday
* Interest
* Dividends

Only **delivery-based Equity and Mutual Funds**.

---

# Sheet Structure

We'll build it in six sections.

---

# Section 1 – Header

| Field         | Value                    |
| ------------- | ------------------------ |
| Working Paper | WRK_CapitalGains         |
| FY            | FY 2025-26               |
| AY            | AY 2026-27               |
| Return        | ITR-3                    |
| Source        | Validated Broker Reports |

---

# Section 2 – Equity Capital Gains

### Sharekhan

| Ref   | Broker    | Gain Type |    Amount |
| ----- | --------- | --------- | --------: |
| CG001 | Sharekhan | STCG      | 18,591.61 |
| CG002 | Sharekhan | LTCG      | -6,067.96 |

*(Do not include Sharekhan "Speculation" here—it belongs to business/speculative income, not capital gains.)*

### Zerodha

| Ref   | Broker  | Gain Type |      Amount |
| ----- | ------- | --------- | ----------: |
| CG003 | Zerodha | STCG      |  -31,498.49 |
| CG004 | Zerodha | LTCG      | -422,953.32 |

---

# Section 3 – Mutual Funds

| Ref   | Broker       | Gain Type | Amount |
| ----- | ------------ | --------- | -----: |
| MF001 | Sharekhan    | STCG      |        |
| MF002 | Sharekhan    | LTCG      |        |
| MF003 | Zerodha Coin | STCG      |        |
| MF004 | Zerodha Coin | LTCG      |        |

If there are no mutual fund redemptions during the year, all values remain **0**.

---

# Section 4 – Consolidation

| Particular        |          Amount |
| ----------------- | --------------: |
| Total Equity STCG |  **-12,906.88** |
| Total Equity LTCG | **-429,021.28** |
| Total MF STCG     |            0.00 |
| Total MF LTCG     |            0.00 |

### Formulas

**Total STCG**

```excel
=SUM(STCG values)
```

**Total LTCG**

```excel
=SUM(LTCG values)
```

---

# Section 5 – Loss Analysis

This is a useful working section.

| Particular         |      Amount |
| ------------------ | ----------: |
| Net STCG           |  -12,906.88 |
| Net LTCG           | -429,021.28 |
| Total Capital Loss | -441,928.16 |

This helps when checking the schedules and understanding what may be eligible for carry-forward.

---

# Section 6 – Validation

| Validation              | Status |
| ----------------------- | ------ |
| Sharekhan reconciled    | ✅      |
| Zerodha reconciled      | ✅      |
| MF reconciled           | ✅      |
| Control Validation PASS | ✅      |
| Ready for Schedule CG   | ✅      |

---

# Important Note about "Speculation"

One thing I noticed in your Sharekhan report:

```
Speculation = 1,294.76
```

Do **not** put this in `WRK_CapitalGains`.

Create a note at the bottom:

| Note                         | Value                              |
| ---------------------------- | ---------------------------------- |
| Sharekhan Speculation Income | ₹1,294.76                          |
| Classification               | Review while preparing Schedule BP |

Whether this amount should be included in business income depends on what those transactions actually represent (e.g., intraday equity). We'll verify that when mapping to the ITR.

---

# ITR Mapping (Draft)

| Working Paper    | ITR Schedule |
| ---------------- | ------------ |
| WRK_BusinessPnL  | Schedule BP  |
| WRK_CapitalGains | Schedule CG  |
| WRK_Interest     | Schedule OS  |
| WRK_Dividends    | Schedule OS  |
| WRK_Form26AS     | Schedule TDS |

---

# What comes after this?

Once `WRK_CapitalGains` is complete, we'll build the remaining working papers in this order:

1. **WRK_Interest** – Bank interest (ICICI) and reconciliation with AIS.
2. **WRK_Dividends** – Consolidate broker dividend reports and reconcile with bank credits and AIS.
3. **WRK_AIS_Reconciliation** – Match broker, bank, and tax portal data.
4. **WRK_Form26AS** – Verify TDS and tax credits.
5. **Dashboard** – Executive summary of income, losses, deductions, and validation status.
6. **Final_ITR** – A clean mapping sheet with only the figures needed to populate ITR-3.

At that point, your workbook will be an **audit-ready, reusable tax working file** rather than just a collection of reports, and you'll be able to reuse the same structure in future years by replacing only the source data.
