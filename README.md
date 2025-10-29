# STAT Methods for Digital Twins — SIR Model for COVID-19 Analysis

## Project Overview
This repository contains a comprehensive analysis of the COVID-19 pandemic in the United States using the SIR (Susceptible-Infectious-Recovered) epidemiological model. The project demonstrates the application of statistical methods and numerical optimization techniques to fit real-world epidemiological data.

### What is SIR?
The SIR model is a fundamental epidemiological model that divides a population into three compartments:
- **S**usceptible: People who can become infected
- **I**nfectious: People who have the disease and can spread it
- **R**ecovered: People who have recovered and are assumed to be immune

The model is described by a system of differential equations:

$$
\begin{align*}
\frac{dS}{dt} &= -\beta SI \\
\frac{dI}{dt} &= \beta SI - \gamma I \\
\frac{dR}{dt} &= \gamma I
\end{align*}
$$

Where:
- β (beta) is the infection rate
- γ (gamma) is the recovery rate

## Project Structure

### Data Files
- `material/US_covid19_confirmed.csv`: Time series data of confirmed COVID-19 cases in the US
- `material/US_covid19_deaths.csv`: Time series data of COVID-19 deaths in the US

### Analysis Notebooks
1. `1_SIR_estimate.ipynb`: Initial implementation
   - Data loading and preprocessing
   - SIR model implementation
   - Basic parameter estimation
   - Initial visualizations

2. `2_SIR_estimate.ipynb`: Enhanced analysis
   - Advanced parameter tuning
   - Alternative optimization approaches
   - Extended diagnostics
   - Refined visualizations

## Technical Details

### Core Dependencies
- Python 3.10+
- NumPy: Numerical computations
- SciPy: Optimization and differential equation solving
- Pandas: Data manipulation
- Matplotlib: Data visualization
- JupyterLab: Interactive computing environment

### Key Components
1. **Data Processing**
   - Loading and cleaning time series data
   - Data normalization and preparation

2. **Model Implementation**
   - SIR differential equations
   - Numerical integration using `scipy.integrate.solve_ivp`

3. **Parameter Estimation**
   - Optimization using various SciPy solvers:
     - `least_squares`: For basic fitting
     - `differential_evolution`: For global optimization
     - `minimize`: For constrained optimization

4. **Visualization**
   - Time series plots
   - Model fit comparisons
   - Diagnostic visualizations

## Installation Guide

### Prerequisites
1. Install Python 3.10 or later
   - Windows: Download from [python.org](https://www.python.org/downloads/)
   - macOS: `brew install python@3.10`
   - Linux: `sudo apt-get install python3.10`

2. Install Git (optional, for cloning)
   - Windows: Download from [git-scm.com](https://git-scm.com/download/win)
   - macOS: `brew install git`
   - Linux: `sudo apt-get install git`

### Setup Instructions

1. **Get the Code**

   Option A - Using Git:
   ```bash
   git clone https://github.com/alejandrobarrecheruiz/STAT-Midterm-Alejandro-Barreche.git
   cd STAT-Midterm-Alejandro-Barreche
   ```

   Option B - Manual Download:
   - Download the ZIP from GitHub
   - Extract to your preferred location
   - Open terminal/command prompt in the extracted folder

2. **Set Up Python Environment**

   Option A - Using Conda (Recommended for beginners):
   ```bash
   # Install Miniconda if you haven't already
   # Create and activate environment
   conda create -n covid-sir python=3.10
   conda activate covid-sir
   
   # Install dependencies
   pip install -r requirements.txt
   ```

   Option B - Using venv (For Python purists):
   ```bash
   # Create virtual environment
   python -m venv .venv
   
   # Activate virtual environment
   # On macOS/Linux:
   source .venv/bin/activate
   # On Windows:
   .venv\Scripts\activate
   
   # Update pip and install dependencies
   pip install --upgrade pip
   pip install -r requirements.txt
   ```

3. **Verify Installation**
   ```bash
   python -c "import numpy; import pandas; import scipy; import matplotlib; print('All dependencies installed successfully!')"
   ```

4. **Launch Jupyter**
   ```bash
   jupyter lab
   ```
   This will open JupyterLab in your default web browser.

### Running the Analysis

1. In JupyterLab, navigate to `1_SIR_estimate.ipynb`
2. Execute cells sequentially (Shift + Enter)
3. Review outputs and visualizations
4. Proceed to `2_SIR_estimate.ipynb` for advanced analysis

### Troubleshooting

1. **Python Version Issues**
   - Run `python --version` to verify Python 3.10+
   - If using `python3`, replace `python` with `python3` in commands

2. **Package Installation Issues**
   ```bash
   # Upgrade pip
   pip install --upgrade pip
   
   # Force reinstall dependencies
   pip install --force-reinstall -r requirements.txt
   ```

3. **Jupyter Issues**
   ```bash
   # Clear Jupyter cache
   jupyter lab clean
   jupyter lab build
   ```

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## License
This project is available for academic and research purposes. Please cite appropriately if used in research work.