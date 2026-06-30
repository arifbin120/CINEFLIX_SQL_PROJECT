# 🎬 CineFlix SQL Analytics Project

**End-to-End Business Intelligence Case Study**  
**Database:** MySQL (Sakila-derived schema)  
**Author:** Arif Bin Mushtaq (MSC Statistics, UOD)  
**Version:** 1.0 | June 2025

---

## Overview

CineFlix is a multi-store DVD rental business operating across several cities. This project presents a comprehensive SQL analytics case study covering the complete database schema, all entity relationships, and ten targeted business queries that extract actionable insights from the CineFlix data warehouse.

---

## Business Objectives

- Identify top-performing film genres by rental volume to guide inventory procurement.
- Segment customers by rental activity and spending to prioritize marketing spend.
- Optimize inventory allocation by matching supply to demand at the store level.
- Monitor staff performance and detect revenue leakage via unprocessed returns.
- Benchmark film pricing against the portfolio average to enable dynamic pricing.

---

## Schema Summary

| Metric        | Value |
|---------------|-------|
| Tables        | 15    |
| Domains       | 3     |
| SQL Queries   | 10    |
| Total Columns | 68+   |

### Domains

| Domain              | Tables                                                                 |
|---------------------|------------------------------------------------------------------------|
| Customer Domain     | city, country, address, customer                                       |
| Business Domain     | staff, store, payment, rental                                          |
| Inventory Domain    | film, actor, category, language, inventory, film_actor, film_category, film_text |

---

## Queries Included

| #  | Query Title                                      | Business Team       |
|----|--------------------------------------------------|---------------------|
| 1  | Most Popular Film Genre by Total Rentals         | Procurement         |
| 2  | Customers Who Rented More Than the Average       | Loyalty Programme   |
| 3  | Total Spend per Customer (Including Zero-Spend)  | Finance             |
| 4  | Film Count per Category (Including Empty)        | Content Catalogue   |
| 5  | Films with Above-Average Rental Rates            | Pricing             |
| 6  | Revenue Generated per Store                      | Operations          |
| 7  | Top 10 Actors by Film Appearances                | Marketing           |
| 8  | Currently Unreturned Rentals (Open Returns)      | Operations          |
| 9  | Inventory Utilisation Rate per Film per Store    | Store Managers      |
| 10 | Monthly Revenue Trend                            | Finance             |

---

## SQL Best Practices Applied

- **JOIN vs Subquery:** JOINs preferred for set-based filtering; correlated subqueries used only in HAVING/WHERE for scalar comparisons.
- **LEFT JOIN for completeness:** Used wherever business questions require rows with no matches (e.g. customers with no rentals, categories with no films).
- **COALESCE for NULL safety:** All SUM/AVG expressions from LEFT JOINs wrapped in COALESCE to return 0 or 0.00.
- **NULLIF for division safety:** Division operations use `NULLIF(denominator, 0)` to prevent divide-by-zero errors.
- **Aliases for readability:** All derived columns and tables use meaningful aliases for BI tool legibility.
- **Deterministic ORDER BY:** All paginated/ranked queries include a deterministic secondary sort (e.g. title) for stable ordering.

---

## File Structure

```
cineflix-sql-analytics/
├── README.md           # Project overview and documentation
├── input.txt           # All 10 SQL input queries
└── output.txt          # Sample output results for all 10 queries
```

---

## How to Use

1. Load the Sakila-derived CineFlix schema into a MySQL instance.
2. Open `input.txt` to find any of the 10 SQL queries.
3. Run the desired query against your database.
4. Compare your results with the sample outputs in `output.txt`.

---

*CineFlix SQL Analytics Project | Confidential | June 2025*
