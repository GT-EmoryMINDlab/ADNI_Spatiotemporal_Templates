# **QPP Templates for ADNI Dataset**
This folder contains **precomputed Quasi-Periodic Pattern (QPP) templates** derived from the **Alzheimer’s Disease Neuroimaging Initiative (ADNI)** dataset.

These templates represent **spatiotemporal patterns** extracted from **functional MRI (fMRI) data** across different **diagnostic groups**.

---

## **📌 Available QPP Templates**
Each `.mat` file in this directory contains a **QPP template matrix** for a specific group.

| **Filename**               | **Description** |
|----------------------------|----------------|
| `ADNI_sNC_QPP.mat`         | **Stable Normal Control (sNC)** – Individuals who remained cognitively normal. |
| `ADNI_sMCI_QPP.mat`        | **Stable Mild Cognitive Impairment (sMCI)** – Individuals who were diagnosed with MCI and did not progress to dementia. |
| `ADNI_sDAT_QPP.mat`        | **Stable Dementia/Alzheimer’s (sDAT)** – Individuals diagnosed with dementia without change over time. |
| `ADNI_uNC_pre_QPP.mat`     | **Unstable Normal Control (uNC-PRE)** – Subjects who were initially normal but later transitioned to MCI. |
| `ADNI_uNC_post_QPP.mat`    | **Unstable Normal Control (uNC-POST)** – Same subjects after their diagnosis changed to MCI. |
| `ADNI_pMCI_pre_QPP.mat`    | **Progressive MCI (pMCI-PRE)** – Subjects who were diagnosed with MCI but later progressed to dementia. |
| `ADNI_pMCI_post_QPP.mat`   | **Progressive MCI (pMCI-POST)** – Same subjects after their diagnosis changed to dementia. |

---

## **📌 File Structure & Data Format**
Each `.mat` file contains a **matrix representation** of a **QPP template**:

- **Rows (105 total)**: Correspond to **Intrinsic Connectivity Networks (ICNs)** based on the **NeuroMark v2.2 atlas**.
- **Columns (Variable length)**: Represent the **temporal dynamics** of the QPP within each group.
- **Data Type**: The matrix contains **normalized fMRI signal values** reflecting the spatiotemporal pattern of the QPP.

---

## **📌 How to Use These Templates**
These **QPP templates** can be used for:
✔ **Spatiotemporal pattern projection** on new fMRI data.  
✔ **Comparing network dynamics** across different diagnostic groups.  
✔ **Computing network correlation matrices** to examine connectivity differences.  

Example MATLAB code to **load and visualize** a QPP template:
```matlab
% Load QPP template
data = load('ADNI_sNC_QPP.mat');

% Extract the QPP matrix (assuming the filename variable is inside the struct)
qpp_template = data.ADNI_sNC_QPP;

% Plot the QPP waveform for an example ICN (e.g., ICN 50)
figure;
plot(qpp_template(50, :));
xlabel('Time (TRs)');
ylabel('Signal Intensity');
title('QPP Waveform for ICN 50 (sNC Group)');
grid on;

