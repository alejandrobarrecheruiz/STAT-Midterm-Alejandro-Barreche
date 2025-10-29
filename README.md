# STAT Methods for Digital Twins — Midterm Project

This repository contains my midterm submission for STAT Methods for Digital Twins.  
The deliverable focuses on fitting and evaluating an epidemiological SIR model against
United States COVID-19 case and mortality data. Two Jupyter notebooks walk through data
preparation, parameter estimation with SciPy optimizers, and visualization of the model
fit.

## Repository structure
- `1_SIR_estimate.ipynb` – First pass at the SIR calibration workflow: data loading,
  helper functions for the SIR differential equations, parameter estimation, and plots.
- `2_SIR_estimate.ipynb` – Follow-up exploration with alternative tuning and diagnostics
  while keeping the same core workflow; use this as the latest iteration of the analysis.
- `material/US_covid19_confirmed.csv` – Johns Hopkins style cumulative confirmed case counts.
- `material/US_covid19_deaths.csv` – Johns Hopkins style cumulative mortality counts.
- `requirements.txt` – Minimal Python dependencies needed to execute the notebooks.

All notebooks assume the data remain in the `material/` directory relative to the
repository root.

## Getting started
These instructions assume Python 3.10+ is available on your machine. Replace `python`
with `python3` if your operating system requires it.

### 1. Copy the repository
```bash
git clone <repository-url>
cd STAT-Midterm-Alejandro-Barreche
```
If you received the project as a `.zip`, unzip it and `cd` into the uncompressed folder
instead of cloning.

### 2. Create and configure an environment
Pick one of the options below to isolate the project dependencies.

**Option A – Conda environment**
```bash
conda create -n stat-midterm python=3.10
conda activate stat-midterm
pip install -r requirements.txt
```

**Option B – Python virtual environment (venv)**
```bash
python -m venv .venv
source .venv/bin/activate            # On Windows use: .venv\Scripts\activate
pip install --upgrade pip
pip install -r requirements.txt
```

**Option C – Global interpreter (not recommended)**
```bash
pip install --user --upgrade pip
pip install --user -r requirements.txt
```
Installing globally can affect other projects, so prefer Conda or `venv` whenever
possible.

### 3. Run the notebooks
Launch your preferred notebook interface once the dependencies are installed.
```bash
jupyter lab
# or
jupyter notebook
```
Open `1_SIR_estimate.ipynb` or `2_SIR_estimate.ipynb` and run the cells top to bottom.
The notebooks expect the CSV files in `material/` to remain untouched.

## Notes
- The notebooks rely on SciPy’s optimizers (`least_squares`, `differential_evolution`,
  `minimize`) and on `scipy.integrate.solve_ivp` for solving the SIR model.
- Feel free to duplicate a notebook if you want to experiment; keep the `material/`
  directory path unchanged so the data loads correctly.
