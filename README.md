# AAN-Neuroscience-Research-Prize
Analytical code and data processing scripts for investigating regional tau pathology (AT8) and transcriptomic signatures associated with clinical resilience in Alzheimer's disease (AAN Neuroscience Research Prize submission).
# Project README: Alzheimer's Disease Donor Classification and Analysis

## Overview

This repository contains a Python-based Jupyter Notebook environment for analyzing donor information datasets (`DonorInformation-2.csv`) related to Alzheimer's disease pathology. The analysis groups donors based on neuropathological staging (such as **Braak stages** and **CERAD scores**), clinical dementia status (`act_demented`), and criteria for cognitive resilience or pathology-positive states.

---

## Dataset & File Sources

The datasets required for this project can be located at the following sources:

* **`DonorInformation-2.csv`**, **`ProteinAndPathologyQuantifications.csv`**, **`columns-samples.csv`**, and **`fpkm_table_unnormalized.csv`** can be found at the **Allen, Aging, Dementia and TBI study** under their respective file names.
* **`GSE104687_RIN_corrected_FPKM.csv`** can be found in the **GSE104687 dataset** of the Allen, Aging, Dementia and TBI Study.

---

## Dataset Features

The dataset includes neuropathological, clinical, and demographic metrics for **107 donors**:

* **Identifiers & Demographics:** `donor_id`, `name`, `age`, `sex`, `race`, `hispanic`, `education_years`.
* **Genetics & Medical History:** `apo_e4_allele`, `age_at_first_tbi`, `ever_tbi_w_loc`, `num_tbi_w_loc`, `longest_loc_duration`.
* **Clinical Diagnoses:** `act_demented`, `dsm_iv_clinical_diagnosis`, `nincds_arda_diagnosis`.
* **Neuropathological Staging:**
* **Braak Stage** (Neurofibrillary tangle pathology)
* **CERAD Score** (Neuritic plaque density frequency)
* **NIA-Reagan Criteria** (likelihood of Alzheimer's disease neuropathologic change)



---

## Analytical Groupings & Classifications

The script categorizes donors into distinct groups to evaluate cognitive resilience versus neuropathological burden:

1. **Primary Groups (`primary_group`):**
* **Low-pathology reference:** Low/no AD pathology (`nia_reagan` 0–1) and `No Dementia` ($n = 36$).
* **Pathology-positive dementia:** High/intermediate AD pathology (`nia_reagan` 2–3) and `Dementia` present ($n = 31$).
* **Resilience-like:** High/intermediate AD pathology (`nia_reagan` 2–3) but *no* clinical dementia (`No Dementia`) ($n = 21$).
* **Low-pathology dementia:** Low/no AD pathology (`nia_reagan` 0–1) despite clinical `Dementia` ($n = 19$).


2. **Strict Neuropathological Groups (`strict_group`):**
* Filters specifically for advanced neurodegeneration: Braak stages 5–6 and CERAD frequent/moderate scores (2–3).
* **Strict resilience-like:** Advanced pathology with `No Dementia` ($n = 6$).
* **Strict pathology-positive dementia:** Advanced pathology with clinical `Dementia` ($n = 22$).



---

## Generated Outputs & Visualizations

The execution pipeline processes data and exports key summaries and plots:

* **CSV/Excel Reports:**
* `Primary_Group_Summary_Table.csv`
* `Strict_Group_Summary_Table.csv`
* `Donor_Group_Classifications.csv` / `.xlsx` (Full dataset mappings)


* **Visualizations:**
* Primary Group Countplots
* Dementia Status by NIA-Reagan Likelihood breakdowns
* **CERAD vs. Braak Stage Heatmaps** for specific cohorts (e.g., Cognitive-Resilient and Pathology-Positive Dementia groups) exported as PDF figures.



---

## Requirements & Dependencies

To run the analysis code provided in the workflow, ensure the following Python libraries are installed:

* `numpy`
* `pandas`
* `matplotlib`
* `seaborn`
