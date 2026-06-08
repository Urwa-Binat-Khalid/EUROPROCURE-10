# EUROPROCURE-10

A large-scale, cleaned, enriched, and machine-learning-ready dataset of European public procurement notices derived from TED (Tenders Electronic Daily) covering the period 2016–2025.

## Overview

EUROPROCURE-10 is a structured procurement intelligence dataset built from public procurement notices published on TED (Tenders Electronic Daily), the official procurement platform of the European Union.

The dataset contains procurement opportunities, contract awards, supplier information, financial attributes, contract metadata, procurement procedures, and AI-enriched features extracted from more than a decade of procurement activity.

The final release contains:

* **1,500,356 procurement notices**
* **51 columns**
* **2016–2025 coverage**
* **190 countries and territories**
* **7 procurement domains**
* **36 languages**
* **132,849 unique buyers**
* **216,228 unique winning suppliers**

The dataset was designed to support procurement analytics, public-sector market intelligence, anomaly detection, fraud-risk research, supplier analysis, and machine learning applications.

---

## Procurement Domains

The dataset classifies procurement activity into seven high-level domains:

1. Healthcare
2. Digital Technology
3. Construction & Infrastructure
4. Automotive
5. Green Energy
6. Defense & Security
7. Aerospace

---

## Dataset Statistics

| Metric                   | Value     |
| ------------------------ | --------- |
| Records                  | 1,500,356 |
| Columns                  | 51        |
| Coverage Period          | 2016–2025 |
| Countries & Territories  | 190       |
| Languages                | 36        |
| Procurement Domains      | 7         |
| Unique Buyers            | 132,849   |
| Unique Winning Suppliers | 216,228   |
| Award Value Coverage     | 43.9%     |
| Estimated Value Coverage | 49.8%     |
| Contact Email Coverage   | 92.9%     |
| Contact Phone Coverage   | 82.5%     |

---

## Key Features

### Procurement Metadata

* Notice identifiers
* Publication dates
* Notice types
* Procurement stages
* Procurement procedures
* Contract types

### Classification Data

* CPV codes
* Primary CPV code
* Secondary CPV codes
* CPV descriptions
* Procurement domains

### Buyer and Supplier Information

* Contracting authority names
* Buyer locations
* Contact information
* Awarded suppliers

### Financial Attributes

* Estimated contract values
* Awarded contract values
* Currency codes
* Award-to-estimate ratios
* Contract value tiers

### AI-Enriched Features

* Extracted keywords
* AI-generated tags
* Procurement risk levels
* NLP-ready text samples

---

## Data Processing

The final release includes:

* Removal of redundant columns
* Country code standardization
* Language code standardization
* Notice type normalization
* CPV code cleanup
* Procurement-domain classification
* Keyword extraction
* AI-generated semantic tagging

Original TED procurement content is preserved wherever possible while improving analytical consistency.

---

## Important Financial Data Warning

The dataset contains procurement values reported in their original notice currencies.

EUROPROCURE-10 contains multiple currencies and values have **not** been converted into EUR.

Users should **not aggregate or directly compare award_value or estimated_value across currencies** without applying appropriate exchange-rate normalization.

In addition, some framework agreements may report maximum spending ceilings rather than realized expenditures.

---

## Missing Data

Missing values primarily reflect procurement-stage differences and reporting practices across contracting authorities and member states.

Examples include:

* Award values are only available for many award-stage notices.
* Supplier names are primarily available after contract award.
* Bid counts are not consistently reported across all jurisdictions.
* Eligibility requirements are frequently embedded in attached documents rather than structured XML fields.

These missing values generally reflect source reporting limitations rather than extraction failures.

---

## Typical Use Cases

* Procurement market intelligence
* Supplier analytics
* Public-sector spending analysis
* Competition analysis
* Procurement transparency research
* Fraud-risk detection
* Weak supervision research
* Anomaly detection
* Procurement NLP
* Large-scale procurement forecasting

---

## License

Raw data sourced from TED (Tenders Electronic Daily), European Union.

This dataset incorporates data made available under the Creative Commons Attribution 4.0 International (CC BY 4.0) licence.

License:
https://creativecommons.org/licenses/by/4.0/

---

## Attribution

Raw data sourced from TED (Tenders Electronic Daily), European Union.

Enriched and processed by Urwa Binat Khalid.

The dataset includes additional processing, normalization, classification, feature engineering, keyword extraction, AI-generated tags, and derived procurement intelligence attributes.

---

## Disclaimer

TED, the Publications Office of the European Union, and the European Union do not endorse this dataset, its derived attributes, analyses, conclusions, machine learning models, visualizations, or associated products.

All enrichments, classifications, derived fields, and analytical outputs were independently produced by the dataset author.

---

## Citation

If you use EUROPROCURE-10 in research, publications, or commercial applications, please cite:

Urwa Binat Khalid. EUROPROCURE-10: A Large-Scale European Public Procurement Dataset (2016–2025).

Raw data sourced from TED (Tenders Electronic Daily), European Union. Enriched and processed by Urwa Binat Khalid.
