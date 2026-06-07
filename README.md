# EUROPROCURE-10

**1.5 Million EU Public Procurement Records | 2016–2025 | ML-Ready**

---

## Overview

EUROPROCURE-10 is a cleaned, enriched, and machine-learning-ready dataset derived from EU public procurement notices published on TED (Tenders Electronic Daily). It covers a full decade of European public contracting activity — the largest open procurement dataset available in structured ML-ready format.

| Attribute | Value |
|---|---|
| Total Records | 1,500,356 |
| Columns | 54 |
| Year Coverage | 2016 – 2025 |
| Countries | 228 |
| Procurement Domains | 7 |
| Unique Buyers | 132,848 |
| Unique Suppliers | 216,227 |
| Total Awarded Value | €197 trillion |
| Overall Completeness | 84.7% |

---

## What Makes This Different from Raw TED Data

Raw TED XML/CSV downloads are messy, inconsistent, and not ready for ML. This dataset adds:

- **Domain classification** — 7 domains assigned per record (healthcare, digital tech, construction, automotive, green energy, defense, aerospace)
- **AI-generated semantic tags** — LLM-generated topic tags for text classification tasks
- **Procurement risk level** — Derived Low/Medium/High risk tier per record
- **award_estimate_ratio** — Award vs estimated value ratio (anomaly detection signal)
- **value_tier** — Contract size band (Micro/Small/Medium/Large/Mega)
- **is_single_bidder** — Binary flag for single-bid contracts (competition risk)
- **award_value_log** — Log-transformed award value (ML-ready, skew-reduced)
- **Cleaned dates, standardised currencies, extracted keywords**

---

## Domain Distribution

| Domain | Records | Share |
|---|---|---|
| Healthcare | 441,573 | 29.4% |
| Digital Technology | 433,042 | 28.9% |
| Construction & Infrastructure | 381,478 | 25.4% |
| Automotive | 133,291 | 8.9% |
| Green Energy | 55,718 | 3.7% |
| Defense & Security | 38,747 | 2.6% |
| Aerospace | 16,507 | 1.1% |

---

## Files Included

```
europrocure10_full.parquet     — Full 1.5M records (recommended for ML)
europrocure10_full.csv         — Full 1.5M records (CSV format)
europrocure10_awards_only.parquet  — ~620K award-stage records with financial data
data_dictionary.pdf            — Full column reference (54 columns)
README.md                      — This file
LICENSE.txt                    — Attribution and reuse terms
```

---

## Quick Start (Python)

```python
import pandas as pd

df = pd.read_parquet("europrocure10_full.parquet")
print(df.shape)          # (1500356, 54)
print(df.domain.value_counts())

# Filter to award records only
awards = df[df.notice_stage == "Contract Award Notice"].copy()

# Anomaly detection features
features = awards[["award_value_log", "number_of_bids", "award_estimate_ratio"]].dropna()
```

---

## Missing Value Notes

| Column | Completeness | Reason |
|---|---|---|
| award_value | 43.9% | Only award-stage notices contain this |
| winner_company | 41.3% | Same — award stage only |
| number_of_bids | 34.8% | Voluntary reporting in some member states |
| eu_fund_name | 5.5% | Only EU-funded contracts |
| nuts_region | 29.2% | Optional in pre-2019 TED XML schema |

---

## Recommended Use Cases

- **Anomaly detection** — award_estimate_ratio, number_of_bids, is_single_bidder
- **NLP / text classification** — raw_text_sample, keywords, ai_generated_tags
- **Market intelligence** — winner_company, buyer_country, domain, value_tier
- **Time-series forecasting** — publication_date, award_value by domain/country
- **Supplier discovery** — winner_company + cpv_codes + buyer_country
- **Risk scoring** — procurement_risk_level, is_single_bidder, award_estimate_ratio

---

## Licence & Attribution

Raw data sourced from **TED (Tenders Electronic Daily), European Union / Publications Office of the European Union**, used under **CC BY 4.0**.

Enriched and processed by **Urwa Binat Khalid**. Additional derived fields include domain classification, AI-generated tags, procurement risk level, and cleaned/standardised procurement attributes. Changes were made to the original data.

Full licence: https://creativecommons.org/licenses/by/4.0/

---
