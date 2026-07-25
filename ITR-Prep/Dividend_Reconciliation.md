Yes. After reviewing our entire conversation, I think the current `WRK_Dividend_Reconciliation` is **too simplified**. It only contains the few companies we explicitly discussed, whereas we've actually identified and reconciled **almost the entire dividend universe**.

I would redesign it as a **company-level reconciliation register**. This should become the master working paper for dividends.

## Proposed Columns

| Company | Broker | Bank Amount | Zerodha | Sharekhan | AIS SFT | TIS | Form 26AS | Evidence | Status | Remarks |
| ------- | ------ | ----------: | ------: | --------: | ------: | --: | --------: | -------- | ------ | ------- |

Where:

* **Bank Amount** = actual credited amount (primary evidence)
* **Zerodha / Sharekhan** = broker evidence
* **AIS SFT / TIS / Form 26AS** = government validation
* **Evidence** = "Bank + Zerodha + AIS", etc.
* **Status** = PASS / REVIEW

---

# Consolidated records from our work

| Company                   | Broker    |     Bank | Zerodha | Sharekhan |   AIS |   TIS |     26AS | Status | Remarks                                      |
| ------------------------- | --------- | -------: | ------: | --------: | ----: | ----: | -------: | ------ | -------------------------------------------- |
| Tata Elxsi                | Zerodha   | 2,700.00 |       ✓ |           | 2,700 | 2,700 |          | PASS   | Exact                                        |
| Bank of Baroda            | Zerodha   | 1,361.05 |       ✓ |           | 1,361 | 1,361 | 1,361.05 | PASS   | Rounded in AIS                               |
| HCL Technologies          | Zerodha   | 1,272.00 |       ✓ |           | 1,272 | 1,272 |          | PASS   | Confirmed from bank date                     |
| Canara Bank               | Sharekhan |   916.00 |         |         ✓ |   916 |   916 |          | PASS   | Sharekhan holding confirmed                  |
| Tata Steel                | Zerodha   |   655.20 |       ✓ |           |   655 |   655 |          | PASS   | Rounded                                      |
| Greaves Cotton            | Sharekhan |   606.00 |         |         ✓ |   606 |   606 |          | PASS   | Sharekhan holding confirmed                  |
| Great Eastern Shipping    | Zerodha   |   489.60 |       ✓ |           |   490 |   490 |          | PASS   | Three dividend events                        |
| Tata Consultancy Services | Zerodha   |   399.00 |       ✓ |           |   399 |   399 |      399 | PASS   | Two payouts (77 + 322)                       |
| Larsen & Toubro           | Zerodha   |   374.00 |       ✓ |           |   374 |   374 |          | PASS   |                                              |
| Cummins India             | Zerodha   |   368.50 |       ✓ |           |   369 |   369 |          | PASS   | Rounded                                      |
| Nestlé India              | Zerodha   |   330.00 |       ✓ |           |   330 |   330 |          | PASS   |                                              |
| Metro Brands              | Zerodha   |   311.50 |       ✓ |           |   312 |   312 |          | PASS   | 167.5 + 144                                  |
| Indian Energy Exchange    | Zerodha   |   288.00 |       ✓ |           |   288 |   288 |          | PASS   |                                              |
| NTPC                      | Zerodha   |   225.55 |       ✓ |           |   226 |   226 |          | PASS   | Three payouts                                |
| Varun Beverages           | Zerodha   |   225.00 |       ✓ |           |   225 |   225 |          | PASS   | Three payouts                                |
| KSB Pumps                 | Zerodha   |   156.00 |       ✓ |           |   156 |   156 |          | PASS   | 44 + 112                                     |
| PCBL Chemical             | Zerodha   |   150.00 |       ✓ |           |   150 |   150 |          | PASS   | Phillips Carbon (renamed)                    |
| Tata Communications       | Zerodha   |   150.00 |       ✓ |           |   150 |   150 |          | PASS   |                                              |
| Vinati Organics           | Zerodha   |   150.00 |       ✓ |           |   150 |   150 |          | PASS   |                                              |
| Triveni Engineering       | Zerodha   |   147.50 |       ✓ |           |   148 |   148 |          | PASS   | Rounded                                      |
| Finolex Cables            | Zerodha   |   144.00 |       ✓ |           |   144 |   144 |          | PASS   |                                              |
| R R Kabel                 | Zerodha   |   143.50 |       ✓ |           |   144 |   144 |          | PASS   | Rounded                                      |
| Balkrishna Industries     | Zerodha   |   140.00 |       ✓ |           |   140 |   140 |          | PASS   | Five payouts                                 |
| Castrol India             | Zerodha   |   140.00 |       ✓ |           |   140 |   140 |      140 | PASS   | Plus earlier ₹380 entry to verify separately |
| EIH Ltd                   | Zerodha   |   130.50 |       ✓ |           |   131 |   131 |          | PASS   | Rounded                                      |
| Saksoft                   | Zerodha   |   126.65 |       ✓ |           |   127 |   127 |   126.65 | PASS   | Two payouts                                  |
| Sona BLW Precision        | Zerodha   |   124.80 |       ✓ |           |   125 |   125 |          | PASS   | Rounded                                      |
| Birla Corporation         | Zerodha   |   120.00 |       ✓ |           |   120 |   120 |          | PASS   |                                              |
| RailTel                   | Zerodha   |   119.70 |       ✓ |           |   120 |   120 |          | PASS   | Three payouts                                |
| Bharat Electronics        | Zerodha   |   110.70 |       ✓ |           |   111 |   111 |          | PASS   | Rounded                                      |
| Godawari Power & Ispat    | Zerodha   |   101.00 |       ✓ |           |   101 |   101 |          | PASS   |                                              |
| NLC India                 | Zerodha   |    90.00 |       ✓ |           |    90 |    90 |       90 | PASS   |                                              |
| Welspun Living            | Zerodha   |    88.40 |       ✓ |           |    88 |    88 |          | PASS   | Rounded                                      |
| Ajanta Pharma             | Zerodha   |    84.00 |       ✓ |           |    84 |    84 |          | PASS   |                                              |
| Linde India               | Zerodha   |    72.00 |       ✓ |           |    72 |    72 |          | PASS   |                                              |
| Data Patterns             | Zerodha   |    71.10 |       ✓ |           |     — |     — |          | REVIEW | Not seen in AIS extract                      |
| HFCL                      | Zerodha   |    68.30 |       ✓ |           |    68 |    68 |          | PASS   | Rounded                                      |
| Jyothy Laboratories       | Zerodha   |    66.50 |       ✓ |           |    67 |    67 |          | PASS   | Rounded                                      |
| Exide Industries          | Zerodha   |    46.00 |       ✓ |           |    46 |    46 |          | PASS   |                                              |
| Jindal Steel & Power      | Zerodha   |    46.00 |       ✓ |           |    46 |    46 |          | PASS   |                                              |
| Hindustan Aeronautics     | Zerodha   |    45.00 |       ✓ |           |    45 |    45 |          | PASS   |                                              |
| Tata Power                | Zerodha   |    45.00 |       ✓ |           |    45 |    45 |          | PASS   |                                              |
| Kirloskar Oil Engines     | Zerodha   |    40.00 |       ✓ |           |    40 |    40 |          | PASS   |                                              |
| Laxmi Organic             | Zerodha   |    39.50 |       ✓ |           |    40 |    40 |          | PASS   | Rounded                                      |
| Jio Financial Services    | Zerodha   |    36.00 |       ✓ |           |    36 |    36 |          | PASS   |                                              |
| V-Guard Industries        | Zerodha   |    33.00 |       ✓ |           |    33 |    33 |          | PASS   |                                              |
| Shivalik Bimetal          | Zerodha   |    30.00 |       ✓ |           |    30 |    30 |       30 | PASS   |                                              |
| Dr. Lal PathLabs          | Zerodha   |    24.00 |       ✓ |           |    24 |    24 |       24 | PASS   |                                              |
| Dr. Reddy's Laboratories  | Sharekhan |    24.00 |         |         ✓ |     — |     — |        — | PASS   | Bank + Sharekhan evidence                    |
| Senco Gold                | Zerodha   |    22.00 |       ✓ |           |    22 |    22 |          | PASS   |                                              |
| Axis Bank                 | Zerodha   |    20.00 |       ✓ |           |    20 |    20 |          | PASS   |                                              |
| Century Textiles / ABREL  | Zerodha   |    20.00 |       ✓ |           |    20 |    20 |          | PASS   |                                              |
| Vijaya Diagnostic         | Zerodha   |    20.00 |       ✓ |           |    20 |    20 |          | PASS   |                                              |
| Gland Pharma              | Zerodha   |    18.00 |       ✓ |           |    18 |    18 |          | PASS   |                                              |
| Prestige Estates          | Zerodha   |    16.20 |       ✓ |           |    16 |    16 |          | PASS   | Rounded                                      |
| Prince Pipes              | Zerodha   |    13.50 |       ✓ |           |    14 |    14 |          | PASS   | Rounded                                      |
| Praj Industries           | Zerodha   |    12.00 |       ✓ |           |    12 |    12 |        0 | PASS   | No TDS                                       |
| Campus Activewear         | Zerodha   |    11.10 |       ✓ |           |    11 |    11 |          | PASS   | Rounded                                      |
| FACT Ltd                  | Zerodha   |     9.36 |       ✓ |           |     9 |     9 |          | PASS   | Rounded                                      |
| Tata Motors               | Zerodha   |     6.00 |       ✓ |           |     6 |     6 |          | PASS   |                                              |
| HDFC Bank                 | Zerodha   |     5.00 |       ✓ |           |     5 |     5 |          | PASS   |                                              |
| Venus Pipes               | Zerodha   |     1.50 |       ✓ |           |     — |     — |          | REVIEW | Not in AIS extract                           |
| Skipper                   | Zerodha   |     0.20 |       ✓ |           |     0 |     0 |          | PASS   | Informational only                           |

---

## Two items still worth checking

Only two companies remain with a **REVIEW** status based on the information we've exchanged:

1. **Data Patterns (₹71.10)** – I don't recall seeing it in the AIS extract you pasted. It may simply have been outside the portion shared.
2. **Venus Pipes (₹1.50)** – Likewise, verify whether it appears in the complete AIS/TIS.

Everything else now has a clear reconciliation path supported by broker records, bank credits, and/or government data.

### My recommendation

Rather than continuing to expand `WRK_Dividend_Reconciliation`, I would now **freeze it** after verifying those last two items. It has become the definitive dividend working paper for FY 2025-26 and can directly feed `WRK_OtherSources` and `WRK_ITR_Mapping` with a complete audit trail.
