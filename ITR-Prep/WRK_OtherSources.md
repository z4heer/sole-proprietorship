# Next Working Paper

I recommend we **do not** jump to AIS immediately.

Instead build:

> **WRK_OtherSources**

Why?

Because the Income Tax Portal (AIS/TIS) is only for **verification**.

First we should compute **our own numbers**, then compare them with AIS.

Professional audit workflow is:

```
Books / Broker / Bank
        ↓
Working Papers
        ↓
Computed Income
        ↓
AIS / 26AS Reconciliation
```

Not the other way around.

---

# WRK_OtherSources

This sheet computes everything taxable under **Income from Other Sources**.

---

## Section 1 – Header

| Field         | Value                     |
| ------------- | ------------------------- |
| Working Paper | WRK_OtherSources          |
| FY            | FY 2025-26                |
| AY            | AY 2026-27                |
| Purpose       | Income from Other Sources |

---

## Section 2 – Savings Interest

Source:

ICICI Interest Certificate

| Ref   | Bank        | Type             | Amount |
| ----- | ----------- | ---------------- | -----: |
| OS001 | ICICI       | Savings Interest |        |
| OS002 | ICICI       | FD Interest      |        |
| OS003 | Other Banks | Interest         |        |

---

Total

```excel
=SUM(D2:D4)
```

---

## Section 3 – Dividend

Don't enter individual companies.

You already have broker summaries.

Use them.

| Ref   | Broker       | Amount |
| ----- | ------------ | -----: |
| DV001 | Zerodha      |        |
| DV002 | Sharekhan    |        |
| DV003 | Mutual Funds |        |

---

Total Dividend

```excel
=SUM(D8:D10)
```

---

## Section 4 – Other Income

| Income Type                   | Amount |
| ----------------------------- | -----: |
| Interest on Income Tax Refund |        |
| Other Income                  |        |

Leave blank if none.

---

## Section 5 – Total Other Sources

| Particular              | Amount |
| ----------------------- | -----: |
| Interest                |        |
| Dividend                |        |
| Other Income            |        |
| **Total Other Sources** |        |

---

## Section 6 – Validation

| Validation                 | Status |
| -------------------------- | ------ |
| Bank Certificate Available | ✅      |
| Dividend Report Available  | ✅      |
| Ready for AIS Comparison   | ✅      |

---

# Why build this?

Later, the AIS reconciliation becomes extremely simple.

```
WRK_OtherSources

vs

AIS

Difference
```

---

# After this

We'll build:

```
WRK_AIS_Reconciliation
```

This becomes one of the most important sheets.

---

# Proposed Layout

| Income Head      | Working Papers | AIS | Difference | Status |
| ---------------- | -------------: | --: | ---------: | ------ |
| Savings Interest |                |     |            |        |
| FD Interest      |                |     |            |        |
| Dividend         |                |     |            |        |
| STCG             |                |     |            |        |
| LTCG             |                |     |            |        |
| F&O              |                |     |            |        |
| Commodity        |                |     |            |        |

---

Difference

```excel
=Working-AIS
```

Status

```excel
=IF(ABS(Difference)<=1,"PASS","REVIEW")
```

---

# Then

We'll build

```
WRK_26AS
```

---

It will contain

| TDS Type     | Working | 26AS | Difference |
| ------------ | ------: | ---: | ---------: |
| Bank TDS     |         |      |            |
| Dividend TDS |         |      |            |
| Other TDS    |         |      |            |

---

# Finally

Everything rolls into

```
Dashboard
```

---

# Dashboard

Think of this as your CA's executive summary.

| Section            | Amount |
| ------------------ | -----: |
| Business Income    |        |
| STCG               |        |
| LTCG               |        |
| Other Sources      |        |
| Gross Total Income |        |
| Deductions         |        |
| Taxable Income     |        |
| Tax Paid           |        |
| Refund / Payable   |        |

Below that:

```
Validation Status

✔ Source Documents

✔ Broker Reconciliation

✔ AIS Match

✔ Form26AS Match

✔ Ready for Filing
```

---

# My recommendation before we proceed

The workbook is now at a stage where I would **freeze all completed sheets** (protect them or at least avoid editing them further). From this point on:

* **Source (`SRC_*`) sheets** should never change unless you replace the underlying report.
* **Working (`WRK_*`) sheets** should contain only formulas and documented manual inputs (like bank interest).
* **Output sheets** (`Dashboard`, `Final_ITR`) should never be edited directly; they should derive everything from the working papers.

That discipline will make this workbook reusable every year and make any future review or correction much easier. We're now very close to having a complete, professional-grade tax working file.
