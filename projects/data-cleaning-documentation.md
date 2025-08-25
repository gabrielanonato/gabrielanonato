---
layout: page
title: Data Cleaning & ETL Documentation
permalink: /projects/data-cleaning-documentation
---

![Documentation](/assets/img/etl-doc.png){: .project-hero }

**Purpose:** Provide a clear, repeatable procedure for preparing raw data for analysis.  
**Audience:** Analysts, Engineers, and new joiners.

### Scope & Inputs
- Dataset name and source
- Ownership and access path
- Data dictionary

### Procedure
1. Raw data intake
2. Quality checks
3. Cleaning steps
4. Transformations
5. Validation
6. Outputs

### Examples
```sql
-- Null diagnostics
SELECT column_name, COUNT(*) AS nulls
FROM my_table
WHERE column_name IS NULL
GROUP BY 1
ORDER BY nulls DESC;
```

```python
# Basic data quality check
assert df.id.nunique() == len(df), "Duplicate IDs found"
```

**Links:** [PDF](/assets/etl-process.pdf) · [ERD](/assets/img/erd.png)
