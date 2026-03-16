#  Efficient Data Storage with Categorical Types in pandas

> A DataCamp project focused on optimizing DataFrame memory usage through smart data type conversion.

---

## Project Overview

This project was completed as part of the **DataCamp Data Scientist learning path**, covering the topic of **categorical data and memory-efficient storage in pandas**.

The goal was to transform a raw dataset (`customer_train.csv`) from Training Data Ltd. into a highly optimized DataFrame — `ds_jobs_transformed` — by applying the most appropriate data types to each column and filtering the data for a specific business use case.

---

## Objectives

- Reduce DataFrame memory usage significantly through smart type conversion
- Apply domain knowledge to distinguish between nominal and ordinal categorical data
- Filter data to match a specific recruiter business requirement

---

## Transformations Applied

| Column Type | Original dtype | Optimized dtype |
|---|---|---|
| Two-factor categories | `object` | `bool` |
| Integer-only columns | `int64` | `int32` |
| Float columns | `float64` | `float16` |
| Nominal categorical | `object` | `category` |
| Ordinal categorical | `object` | `CategoricalDtype` (ordered) |

### Ordinal Categories
Ordinal columns were converted to **ordered categorical types** with a natural ordering that reflects real-world hierarchy — for example, education levels (Primary < Secondary < Graduate < Masters < PhD) or company size and experience ranges.

---

## Data Filtering

The final DataFrame was filtered to include only:
- Candidates with **10 or more years of experience**
- Candidates from companies with **at least 1,000 employees**

This matches Training Data Ltd.'s recruiter base, which specializes in placing experienced professionals at enterprise-level companies.

---

## Memory Usage Results

Running `.info()` or `.memory_usage(deep=True)` on both DataFrames reveals a **substantial reduction** in memory consumption after transformation, demonstrating the real-world impact of choosing the right data types.

---

## Technologies Used

- **Python 3**
- **pandas**
- **Jupyter Notebook / DataCamp Workspace**

---

## Key Concepts Learned

- Difference between **nominal** and **ordinal** categorical data
- Using `pd.CategoricalDtype` with ordered categories
- Memory optimization with `int32`, `float16`, `bool`, and `category` dtypes
- Filtering DataFrames based on multiple business conditions

---

## How to Run

```python
import pandas as pd

# Load raw data
ds_jobs = pd.read_csv("customer_train.csv")

# Apply transformations
# ... (see notebook for full code)

# Verify memory reduction
print(ds_jobs.memory_usage(deep=True).sum())
print(ds_jobs_transformed.memory_usage(deep=True).sum())
```

---

## About This Project

This project is part of the [DataCamp](https://www.datacamp.com) Data Science curriculum. It is intended for learning purposes and to demonstrate practical pandas skills.

---

*Happy coding! 🐍*
