# AI Ethics Assignment: Designing Responsible and Fair AI Systems 🌍⚖️

[![Python Version](https://img.shields.io/badge/python-3.8%2B-blue)](https://www.python.org/downloads/)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)
[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)
[![Fairness](https://img.shields.io/badge/AI-Fairness%20360-orange)](https://aif360.mybluemix.net/)

> A comprehensive analysis of algorithmic bias in the COMPAS recidivism prediction system, demonstrating practical applications of AI ethics principles and fairness auditing techniques.

---

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Quick Start](#quick-start)
- [Usage](#usage)
- [Results](#results)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgments](#acknowledgments)
- [Contact](#contact)

---

## 🎯 Overview

This project evaluates ethical considerations in AI systems through a multi-faceted approach:

1. **Theoretical Understanding**: Exploration of algorithmic bias, transparency, explainability, and regulatory frameworks
2. **Case Study Analysis**: In-depth examination of real-world AI bias incidents (Amazon hiring tool, facial recognition)
3. **Technical Audit**: Hands-on fairness analysis of the COMPAS recidivism dataset using AI Fairness 360
4. **Policy Development**: Creation of ethical guidelines for AI deployment in sensitive domains (healthcare)

### Why This Matters

- **Societal Impact**: Biased AI systems perpetuate discrimination and harm vulnerable populations
- **Legal Compliance**: Regulations like GDPR and emerging AI laws require fairness by design
- **Professional Development**: Ethical AI competency is increasingly demanded by employers
- **Technical Excellence**: Fair AI performs better across diverse populations

---

## ✨ Features

### 🔍 Comprehensive Bias Analysis
- Statistical analysis of racial disparities in risk assessments
- Confusion matrix comparison across demographic groups
- Industry-standard fairness metrics (disparate impact, statistical parity)

### 📊 Professional Visualizations
- Risk score distribution by race
- False positive rate comparisons
- Recidivism prediction accuracy analysis
- Decile score box plots

### 🛠️ Bias Mitigation Techniques
- Implementation of reweighing algorithm
- Before/after fairness metric comparisons
- Practical remediation recommendations

### 📝 Production-Ready Documentation
- Complete written analyses for all theoretical components
- Detailed case study solutions
- 300-word technical audit report
- Healthcare AI ethics policy proposal

---

## 📁 Project Structure

```
ai-ethics-assignment/
│
├── README.md                          # This file
├── requirements.txt                   # Python dependencies
├── LICENSE                            # MIT License
│
├── notebooks/
│   ├── fairness_audit.ipynb          # Main Jupyter notebook
│   └── exploratory_analysis.ipynb    # Additional analysis (optional)
│
├── data/
│   ├── compas-scores-two-years.csv   # COMPAS dataset
│   └── data_dictionary.md            # Dataset documentation
│
├── reports/
│   ├── case_study_analysis.pdf       # Written case studies
│   ├── audit_report.pdf              # Technical audit findings
│   └── fairness_audit_report.txt     # Generated text report
│
├── visualizations/
│   └── compas_bias_analysis.png      # Generated charts
│
├── bonus/
│   └── healthcare_ai_policy.pdf      # Healthcare ethics guideline
│
├── src/
│   ├── __init__.py
│   ├── data_preprocessing.py         # Data cleaning functions
│   ├── fairness_metrics.py           # Custom metric calculations
│   └── visualization.py              # Plotting functions
│
└── tests/
    └── test_fairness_metrics.py      # Unit tests
```

---

## 🚀 Installation

### Prerequisites

- Python 3.8 or higher
- pip package manager
- Git (for cloning repository)
- Jupyter Notebook or JupyterLab

### Step 1: Clone Repository

```bash
git clone https://github.com/yourusername/ai-ethics-assignment.git
cd ai-ethics-assignment
```

### Step 2: Create Virtual Environment (Recommended)

```bash
# Using venv
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Or using conda
conda create -n ai-ethics python=3.8
conda activate ai-ethics
```

### Step 3: Install Dependencies

```bash
pip install -r requirements.txt
```

**Required packages:**
- `aif360==0.5.0` - AI Fairness 360 toolkit
- `pandas>=1.5.0` - Data manipulation
- `numpy>=1.24.0` - Numerical computing
- `matplotlib>=3.6.0` - Visualization
- `seaborn>=0.12.0` - Statistical visualizations
- `scikit-learn>=1.2.0` - Machine learning utilities
- `jupyter>=1.0.0` - Notebook environment

### Step 4: Download Dataset

```bash
# Method 1: Using wget
wget https://raw.githubusercontent.com/propublica/compas-analysis/master/compas-scores-two-years.csv -P data/

# Method 2: Using curl
curl -o data/compas-scores-two-years.csv https://raw.githubusercontent.com/propublica/compas-analysis/master/compas-scores-two-years.csv

# Method 3: Manual download
# Visit: https://github.com/propublica/compas-analysis
# Download compas-scores-two-years.csv to data/ folder
```

### Step 5: Verify Installation

```bash
python -c "import aif360; import pandas; import matplotlib; print('✅ All packages installed successfully!')"
```

---

## ⚡ Quick Start

### Run the Complete Analysis (5 minutes)

```bash
# Launch Jupyter Notebook
jupyter notebook notebooks/fairness_audit.ipynb

# Or using JupyterLab
jupyter lab notebooks/fairness_audit.ipynb
```

**Then:**
1. Click "Cell" → "Run All" to execute entire analysis
2. Wait 2-3 minutes for completion
3. Review generated visualizations and report
4. Export notebook as PDF: "File" → "Export Notebook As" → "PDF"

### Expected Output

```
✅ All libraries imported successfully!
Dataset shape: (7214, 52)
Cleaned dataset shape: (5,278, 15)

KEY FINDINGS:
- African-Americans labeled high risk: 58.3%
- Caucasians labeled high risk: 37.7%
- False Positive Rate Disparity: 44.8% vs 23.5%
- Disparate Impact Ratio: 0.65 (BIAS DETECTED)

✅ Visualizations saved as 'compas_bias_analysis.png'
✅ Full report saved as 'fairness_audit_report.txt'
AUDIT COMPLETE!
```

---

## 📖 Usage

### Running Individual Components

#### 1. Data Preprocessing Only

```python
from src.data_preprocessing import load_and_clean_compas_data

df_clean = load_and_clean_compas_data('data/compas-scores-two-years.csv')
print(f"Cleaned data shape: {df_clean.shape}")
```

#### 2. Calculate Fairness Metrics

```python
from src.fairness_metrics import calculate_disparate_impact

di_ratio = calculate_disparate_impact(
    df_clean, 
    protected_attr='race',
    outcome='high_risk'
)
print(f"Disparate Impact Ratio: {di_ratio:.4f}")
```

#### 3. Generate Visualizations

```python
from src.visualization import plot_bias_analysis

plot_bias_analysis(df_clean, save_path='visualizations/')
```

### Advanced Usage

#### Custom Bias Analysis

```python
# Analyze intersectional bias (race + gender)
from aif360.datasets import BinaryLabelDataset

dataset = BinaryLabelDataset(
    df=df_clean,
    label_names=['two_year_recid'],
    protected_attribute_names=['race_binary', 'sex']
)

# Calculate metrics for specific groups
privileged_groups = [{'race_binary': 0, 'sex': 1}]  # White males
unprivileged_groups = [{'race_binary': 1, 'sex': 0}]  # Black females

# ... continue analysis
```

#### Apply Different Mitigation Techniques

```python
from aif360.algorithms.preprocessing import DisparateImpactRemover

DIR = DisparateImpactRemover(repair_level=1.0)
dataset_transformed = DIR.fit_transform(dataset)
```

---

## 📊 Results

### Key Findings

| Metric | African-American | Caucasian | Disparity |
|--------|-----------------|-----------|-----------|
| **High Risk Rate** | 58.3% | 37.7% | +20.6 pp |
| **False Positive Rate** | 44.8% | 23.5% | +21.3 pp |
| **False Negative Rate** | 28.0% | 47.7% | -19.7 pp |
| **Accuracy** | 63.2% | 67.8% | -4.6 pp |

**Disparate Impact Ratio: 0.65** ⚠️  
(Fair range: 0.8 - 1.2; indicates significant bias)

**Statistical Parity Difference: -0.206**  
(Optimal: 0.0; negative value shows unfairness against African-Americans)

### Visualization Samples

![COMPAS Bias Analysis](visualizations/compas_bias_analysis.png)

*Four-panel analysis showing: (1) Risk score distribution by race, (2) False positive rate comparison, (3) Recidivism vs prediction accuracy, (4) Decile score distributions*

### Impact

- **21.3%** higher false positive rate for African-Americans
  - ≈ **1,183 people** incorrectly labeled high risk
  - Real-world consequences: denied bail, longer sentences, limited opportunities

---

## 🤝 Contributing

Contributions are welcome! This project is designed for educational purposes, and improvements are encouraged.

### How to Contribute

1. **Fork the repository**
2. **Create a feature branch**
   ```bash
   git checkout -b feature/amazing-improvement
   ```
3. **Make your changes**
   - Add new fairness metrics
   - Improve visualizations
   - Enhance documentation
   - Fix bugs
4. **Run tests**
   ```bash
   pytest tests/
   ```
5. **Commit your changes**
   ```bash
   git commit -m "Add amazing improvement"
   ```
6. **Push to your fork**
   ```bash
   git push origin feature/amazing-improvement
   ```
7. **Open a Pull Request**

### Contribution Ideas

- [ ] Add more fairness metrics (equalized odds, predictive parity)
- [ ] Implement additional bias mitigation algorithms
- [ ] Create interactive dashboard (Streamlit/Dash)
- [ ] Expand to other datasets (FICO scores, hiring data)
- [ ] Add unit tests for all functions
- [ ] Translate documentation to other languages
- [ ] Create video tutorials

### Code Style

- Follow PEP 8 guidelines
- Use type hints where applicable
- Write docstrings for all functions
- Add comments for complex logic
- Keep functions under 50 lines when possible

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

```
MIT License

Copyright (c) 2025 [Your Name/Organization]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction...
```

---

## 🙏 Acknowledgments

### Data Sources
- **ProPublica**: For the COMPAS analysis and dataset
  - [Machine Bias Article](https://www.propublica.org/article/machine-bias-risk-assessments-in-criminal-sentencing)
  - [GitHub Repository](https://github.com/propublica/compas-analysis)

### Tools & Frameworks
- **IBM AI Fairness 360**: Comprehensive toolkit for bias detection and mitigation
- **Pandas**: Data manipulation and analysis
- **Matplotlib/Seaborn**: Data visualization
- **Scikit-learn**: Machine learning utilities

### Research & Guidelines
- **EU Ethics Guidelines for Trustworthy AI**: Framework for ethical AI development
- **NIST AI Risk Management Framework**: Standards for AI governance
- **ACM Code of Ethics**: Professional computing ethics guidelines

### Inspiration
- ProPublica's investigative journalism on algorithmic accountability
- Research by Cynthia Dwork, Moritz Hardt, and Timnit Gebru on fairness in ML
- The AI Now Institute's work on social implications of AI

---

## 📞 Contact

### Project Maintainer
- **Name**: [Your Name]
- **Email**: your.email@example.com
- **GitHub**: [@yourusername](https://github.com/yourusername)
- **LinkedIn**: [Your Profile](https://linkedin.com/in/yourprofile)

### Support
- **Issues**: [GitHub Issues](https://github.com/yourusername/ai-ethics-assignment/issues)
- **Discussions**: [GitHub Discussions](https://github.com/yourusername/ai-ethics-assignment/discussions)
- **PLP Community**: #AIEthicsAssignment

---

## 📚 Additional Resources

### Recommended Reading
- **Books**:
  - "Weapons of Math Destruction" by Cathy O'Neil
  - "Algorithms of Oppression" by Safiya Noble
  - "Race After Technology" by Ruha Benjamin

- **Papers**:
  - [Fairness Definitions Explained](https://arxiv.org/abs/1710.03184)
  - [A Survey on Bias and Fairness in ML](https://arxiv.org/abs/1908.09635)
  - [Fairness Through Awareness](https://arxiv.org/abs/1104.3913)

### Online Courses
- [Fairness in Machine Learning (MOOC)](https://fairmlclass.github.io/)
- [Ethics of AI (MIT OpenCourseWare)](https://ocw.mit.edu/)
- [AI Ethics (University of Helsinki)](https://ethics-of-ai.mooc.fi/)

### Tools & Libraries
- [Fairlearn](https://fairlearn.org/) - Microsoft's fairness toolkit
- [What-If Tool](https://pair-code.github.io/what-if-tool/) - Visual ML fairness tool
- [FairML](https://github.com/adebayoj/fairml) - Auditing predictive models

---

## 🔖 Citation

If you use this project in your research or work, please cite:

```bibtex
@misc{ai_ethics_assignment_2025,
  title={AI Ethics Assignment: COMPAS Fairness Audit},
  author={[Your Name]},
  year={2025},
  publisher={GitHub},
  url={https://github.com/yourusername/ai-ethics-assignment}
}
```

---

## 📈 Project Stats

![GitHub stars](https://img.shields.io/github/stars/yourusername/ai-ethics-assignment?style=social)
![GitHub forks](https://img.shields.io/github/forks/yourusername/ai-ethics-assignment?style=social)
![GitHub watchers](https://img.shields.io/github/watchers/yourusername/ai-ethics-assignment?style=social)

**Last Updated**: December 2025  
**Status**: ✅ Active & Maintained  
**Version**: 1.0.0

---

## ⭐ Star History

If you find this project useful, please consider giving it a star! ⭐

Your support helps others discover this educational resource and encourages continued development.

---

<div align="center">

**Built with ❤️ for ethical AI**

[Report Bug](https://github.com/yourusername/ai-ethics-assignment/issues) • 
[Request Feature](https://github.com/yourusername/ai-ethics-assignment/issues) • 
[Documentation](https://github.com/yourusername/ai-ethics-assignment/wiki)

</div>
