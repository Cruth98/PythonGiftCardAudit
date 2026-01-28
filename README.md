# Python Gift Card Audit Requests

This repository contains Python-based workflows and notebooks developed to
support **time-sensitive, large-scale audit requests** involving multi-GB gift
card transaction data that could not be processed using Excel or traditional
manual methods.

The work focuses on **data validation, aggregation, and audit reconciliation**
under tight deadlines.

---

## Overview of Audit Requests

This repository includes solutions for three major audit requests:

1. **INCOMM Running Sum**
2. **Givex Transaction Listing**
3. **BHN Running Sum**

Each request required processing large transaction files (between 5GB & 60GB), performing
custom aggregation logic, and delivering clean, auditable outputs to finance,
treasury, and audit stakeholders.

---

## Audit Request Details

### 1. INCOMM Running Sum
- **Problem:**  
  The Gift Card Accounting team was unable to reconcile a large INCOMM
  transaction file due to file size limitations and the need for an
  **iterative running balance at the record level**.
- **Approach:**  
  Built a Python workflow to process the full dataset, calculate running
  subtotals programmatically, and aggregate results into a usable format.
- **Outcome:**  
  Delivered reconciled outputs that enabled audit completion and replaced
  an infeasible Excel-based process.

---

### 2. Givex Transaction Listing
- **Problem:**  
  Treasury received an urgent audit request from internal audit and the CFO
  requiring grouped transaction summaries that could not be generated in Excel
  due to data volume.
- **Approach:**  
  Parsed and transformed the dataset in Python, including processor-type
  normalization, then grouped and aggregated transactions by processor and date.
- **Outcome:**  
  Produced clean, readable CSV outputs used directly by Treasury for audit
  response and executive review.

---

### 3. BHN Running Sum
- **Problem:**  
  A second vendor (BHN) required the same reconciliation logic previously built
  for INCOMM.
- **Approach:**  
  Reused and adapted the existing Python running-sum framework to a new vendor
  dataset.
- **Outcome:**  
  The approach became the **standard audit reconciliation process** for this
  vendor within the audit department.

---

## Key Capabilities Demonstrated
- Large-scale data processing (>5GB files)
- Python-based aggregation and reconciliation logic
- Data validation and audit support
- Rapid delivery under time-sensitive conditions
- Translation of complex data into audit-ready outputs

---

## Tools & Technologies
- Python
- pandas
- CSV-based data pipelines
