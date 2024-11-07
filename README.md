
# A/B/n Testing Statistics Calculator 📊✨

In this repository, you will find scripts to calculate the minimum sample size required when allocation ratios are not equal, and if observed changes in your experiments are statistically significant.

You can find the presentation on: https://docs.google.com/presentation/d/1EezSoGVJwg7zhUDMpNpNCpgVKQF4MPzBt2UVPte203Y/edit?usp=sharing

## 1. **A/B/n Test Statistical Calculator for Discrete Variables** 🖱️📈

This script is useful for tests involving discrete outcomes such as:
- **UI change**: Evaluating layouts for engagement (e.g., ad-to-cart click-through rates).
- **Email marketing**: Determining which email subject maximizes opening rates. 📧
- **Feature rollout**: Measuring impulsive purchases triggered by design changes.
- **Pricing changes**: Assessing the impact of new pricing structures on conversions.

**Note**: Ensure normal distribution; otherwise, use another method.

### 🚀 Function Overview
Calculates the statistical significance between control and test groups. Outputs include:
- Conversion rates.
- z-statistic and p-values.
- Performance improvement percentages.

### 🔧 How to Use
```python
# Calculate minimum sample size
from scipy.stats import norm

def calculate_sample_size_abn_test_discrete(baseline_rate, minimum_effect, allocation_ratios, alpha=0.05, power=0.8):
    # Example usage
    baseline_rate=0.1,
    minimum_effect=0.02,
    allocation_ratios=[0.7, 0.20, 0.10]
    calculate_sample_size_abn_test_discrete(baseline_rate, minimum_effect, allocation_ratios, alpha, power)

# Calculate statistical significance
import numpy as np
from statsmodels.stats.proportion import proportions_ztest

def analyze_abn_test_discrete(data):
    # Example usage:
    data = {
        'Control': [387, 4113], 
        'Test 1': [30, 216],
        'Test 2': [90, 500],
        'Test 3': [60, 300]
    }
    analyze_abn_test_discrete(data)
```

## 2. **A/B/n Test Statistical Calculator for Continuous Variables** 📊📏

Best suited for continuous outcomes like:
- **UI change**: Average time spent on a page.
- **Email marketing**: Reading duration for emails.
- **Feature rollout**: Session durations.
- **Pricing changes**: Time spent on checkout pages.

**Note**: Ensure normal distribution; otherwise, use another method.

### 🚀 Function Overview
Uses two-tailed t-tests to compare control and variation means:
- t-statistic and p-values.
- Mean improvements.

### 🔧 How to Use
```python
# Calculate minimum sample size
import numpy as np
from statsmodels.stats.power import TTestIndPower

def calculate_sample_size_abn_test_continuous(minimum_effect, std_control, allocation_ratios, alpha=0.05, power=0.8):
    # Example usage:
    minimum_effect=5
    std_control=15
    allocation_ratios=[0.75, 0.10, 0.15]
    calculate_sample_size_abn_test_continuous(minimum_effect, std_control, allocation_ratios, alpha, power)



# Calculate statistical significance
import math
from scipy import stats

def analyze_abn_test_continous(control_mean, control_std, control_n, variations_data):
    # Example usage:
    control_mean = 50
    control_std = 10
    control_n = 1000
    variations_data = [(52, 10, 800), (60, 50, 1000), (48, 50, 600)]
    analyze_abn_test_continous(control_mean, control_std, control_n, variations_data)
```

## 🏁 Summary
With these tools, you can effectively analyze A/B/n tests for discrete and continuous data, identify significant improvements, and choose the best-performing variations. 🚀✨
