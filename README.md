# Python Gift Card Audit Workflows

Python-based solutions to three time-sensitive, large-scale audit requests 
involving multi-GB gift card transaction data that exceeded Excel's processing 
limits. Each request was escalated to Python after traditional tools failed — 
outputs were delivered directly to KPMG auditors, Treasury, and the CFO.

---

## Context

The Gift Card Accounting and Treasury teams regularly received audit requests 
requiring transaction-level reconciliation across datasets ranging from 5GB to 
60GB. Excel could not open these files. These notebooks were built under deadline 
pressure to unblock audit completion and deliver auditable outputs to external 
auditors and senior finance leadership.

---

## Audit Requests

### 1. INCOMM Running Sum

**Problem:** INCOMM transaction file too large for Excel; audit required a 
record-level running balance to support KPMG population subsampling across 
multiple auditor-defined dollar thresholds.

**Approach:**
- Loaded multi-GB CSV with selective column import (`usecols`) for memory efficiency
- Filtered zero-balance records
- Computed cumulative running sum (`cumsum`) at the transaction level
- Built a threshold-based breakout function that automatically generates 
  audit-ready CSV subsets for each KPMG sample threshold
- Iterated across all thresholds in a single loop, producing one output file per threshold

---

### 2. BHN Running Sum

**Problem:** Second gift card vendor (BHN) required identical reconciliation 
logic as INCOMM on a new transaction file.

**Approach:**
- Adapted the INCOMM framework to the BHN dataset structure
- Same column selection, zero-balance filtering, cumsum, and threshold breakout logic
- Adapted threshold breakout function to BHN-specific auditor parameters

**Outcome:** The approach was adopted as the **standard audit reconciliation 
process** for BHN within the audit department.

---

### 3. Givex Transaction Listing

**Problem:** Treasury received an urgent CFO and Internal Audit request for 
grouped transaction summaries from a Givex dataset that could not be processed 
in Excel due to volume.

**Approach:**
- Loaded transaction file with selective column import
- Normalized processor/channel classification using `np.select` with 
  conditional logic (OLO, Ziosk, Misc) — handling inconsistent username 
  casing across the dataset
- Constructed a `true_channel` composite field by concatenating channel 
  name and normalized processor type
- Grouped by `true_channel` and `source` to produce clean transaction counts
- Output saved directly to a named CSV for Treasury review

---

## Key Capabilities Demonstrated

- **Large-scale data processing** — files ranging from 5GB to 60GB processed 
  via pandas with memory-efficient column selection
- **Audit-ready output generation** — threshold-based subsampling logic 
  producing KPMG-formatted population subsets
- **Conditional normalization** — multi-condition channel classification 
  handling inconsistent source data
- **Rapid deployment** — all three notebooks built and delivered under 
  time-sensitive audit deadlines
- **Business translation** — Python used as a direct replacement for 
  infeasible Excel processes, with outputs consumed by external auditors 
  and the CFO

---

## Tools

- Python, pandas, NumPy
- Google Colab (large file processing via Google Drive mount)
- CSV pipelines with selective ingestion for memory efficiency
