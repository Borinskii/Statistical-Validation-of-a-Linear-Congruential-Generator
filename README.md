# Linear Congruential Generator - Statistical Validation

A Python implementation and statistical analysis of Linear Congruential Generators (LCG) for pseudorandom number generation.

**Author:** Boris Arutinov

## Overview

This project implements and validates a Linear Congruential Generator using the recurrence relation:

```
r(i+1) = (a × r(i)) mod m
x(i) = r(i) / m
```

The study compares three different generator configurations with varying parameters and analyzes their statistical properties through multiple metrics and visualizations.

## Features

- Dynamic LCG implementation with parameter validation
- Statistical analysis (mean, median, variance, standard deviation, autocorrelation)
- Period length detection
- Distribution visualizations
- Comparison of three generator configurations

## Installation

```bash
# Clone the repository
git clone https://github.com/Borinskii/Statistical-Validation-of-a-Linear-Congruential-Generator.git
cd Statistical-Validation-of-a-Linear-Congruential-Generator

# Install dependencies
pip install -r requirements.txt

# Launch Jupyter Notebook
jupyter notebook notebooks/LCG.ipynb
```

## Requirements

- Python 3.8+
- NumPy
- Pandas
- Matplotlib
- Jupyter Notebook

See `requirements.txt` for specific versions.

## Usage

```python
# Generate pseudorandom numbers
numbers = generate_random_numbers(r0=2, m=109, a=30, n=1000)

# Calculate statistical measures
stats = statistical_measures(numbers)
```

## Generator Configurations Tested

| Generator | r₀ | m | a | Period | Description |
|-----------|-----|-----|------|---------|-------------|
| Gen 1 | 2 | 5 | 3 | 4 | Simple example |
| Gen 2 | 2 | 109 | 30 | 108 | Custom config |
| Gen 3 | 3 | 2³¹-1 | 16807 | ~2×10⁹ | Arena standard (MINSTD) |

## Key Results

Generator 3 (MINSTD) shows the best statistical properties:
- Mean: 0.481 (close to ideal 0.5)
- Standard deviation: 0.287 (close to ideal 0.289)
- Low autocorrelation: -0.002
- Very long period suitable for practical applications

Full analysis and visualizations available in the Jupyter notebook.

## Project Structure

```
.
├── notebooks/
│   └── LCG.ipynb          # Main analysis notebook
├── LICENSE
├── README.md
└── requirements.txt
```



## License

Educational project developed as part of academic coursework.

---

*For detailed implementation, statistical analysis, and visualizations, see `notebooks/LCG.ipynb`*
