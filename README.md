<a id="readme-top"></a>

<div align="center">
  <h1 align="center">Bias Detection and Mitigation in Large Language Models</h1>
  <p align="center">
    A systematic approach to identify, quantify, and mitigate biases in Large Language Models
    <br />
    <a href="research_paper.pdf"><strong>Read the research paper »</strong></a>
  </p>
</div>

## Table of Contents
- [Overview](#overview)
- [Installation](#installation)
- [Folder Structure](#folder-structure)
- [Usage](#usage)
- [Technologies Used](#technologies-used)
- [Methodology](#methodology)
- [Results](#results)
- [Conclusion](#conclusion)

## Overview
Large language models (LLMs) have revolutionized natural language processing with remarkable capabilities in text generation, question answering, and language understanding. However, these models can unintentionally learn and perpetuate societal biases from their training data, leading to unfair or discriminatory outputs.

This project systematically addresses bias in LLMs through three key phases:
1. **Detection** - Identifying bias using carefully crafted prompts
2. **Quantification** - Measuring bias using stereotype scores and toxicity metrics
3. **Mitigation** - Implementing strategies like Counterfactual Data Augmentation and AI Fairness 360

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Installation

### Prerequisites
- Python 3.8 or higher
- pip package manager
- CUDA-compatible GPU (optional, for faster processing)

### Setup

1. Clone the repository:
```bash
git clone https://github.com/yourusername/Bias_Detection_And_Mitigation_In_LLMs.git
cd Bias_Detection_And_Mitigation_In_LLMs-main
```

2. Install required dependencies:
```bash
pip install -r requirements.txt
```

3. (Optional) Install Jupyter for running notebooks:
```bash
pip install jupyter notebook
```

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Folder Structure
```
Bias_Detection_And_Mitigation_In_LLMs-main/
│
├── Code/
│   ├── Stereotype_Score_Calculation.ipynb    # Bias quantification using log-probability
│   └── Toxicity_Score_Calculation.ipynb      # Toxicity analysis using Evaluate library
│
├── Data/
│   └── crows_pairs_anonymized.csv            # CrowS-Pairs benchmark dataset
│
├── requirements.txt                           # Python dependencies
├── research_paper.pdf                         # Detailed research documentation
└── README.md                                  # Project documentation
```

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Usage

### Running Bias Analysis

1. **Stereotype Score Calculation:**
   ```bash
   jupyter notebook Code/Stereotype_Score_Calculation.ipynb
   ```
   This notebook calculates stereotype and anti-stereotype scores for various language models using log-probability metrics.

2. **Toxicity Score Calculation:**
   ```bash
   jupyter notebook Code/Toxicity_Score_Calculation.ipynb
   ```
   This notebook evaluates model outputs for toxic and offensive content using the Hugging Face Evaluate library.

### Dataset
The project uses the **CrowS-Pairs** dataset, which contains sentence pairs designed to measure stereotypical biases across nine categories including race, gender, age, religion, and more.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Technologies Used
[![Python](https://img.shields.io/badge/Python-FFD43B?style=for-the-badge&logo=python&logoColor=blue)](https://www.python.org/)
[![HuggingFace](https://img.shields.io/badge/HuggingFace-FF9900?style=for-the-badge)](https://huggingface.co/docs/transformers/en/model_doc/bert)
[![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)](https://pytorch.org/)

**Key Libraries:**
- `transformers` - Pre-trained language model implementations
- `torch` - Deep learning framework
- `evaluate` - Model evaluation metrics
- `datasets` - Dataset loading and processing
- `pandas` & `numpy` - Data manipulation

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Problem Statement
Large Language models are trained with a large amount of unsupervised data. If the training data used for LLMs contain unrepresentative samples or biases, naturally, the model will inherit and learn these biases. These can result in potential bias when the end user uses these biased models.

**Project Objectives:**
- **Bias Identification** - Detect and categorize gender, racial, and cultural biases in model outputs
- **Bias Quantification** - Compare bias levels across different LLMs using standardized metrics
- **Bias Mitigation** - Evaluate data preprocessing, fine-tuning, and post-processing techniques

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Methodology

Our three-phase approach systematically addresses bias in LLMs:

### 1. Scrutinize - Detecting Bias
Craft targeted prompts to trigger biased responses (e.g., gender stereotypes, sociopolitical stances) and manually inspect outputs across multiple models for unfair bias patterns.

### 2. Quantify - Measuring Bias
Use benchmark datasets (CrowS-Pairs, BOLD) to evaluate models with:
- **Toxicity Scores** - Measure unsafe/offensive content
- **Stereotype Scores** - Quantify stereotypical vs. anti-stereotypical associations using log-probability metrics

### 3. Mitigate - Reducing Bias
Implement strategies to minimize bias:
- **Counterfactual Data Augmentation (CDA)** - Generate counterfactual examples during fine-tuning
- **AI Fairness 360** - Apply pre-processing, in-processing, and post-processing fairness methods
<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Results

### Models Evaluated
- **ALBERT** - Exhibited highest bias levels across metrics
- **BERT** - Moderate bias with balanced performance
- **XLNet** - Lower bias but limited capacity
- **GPT** - Best performance with minimal bias

### Key Findings

**Phase 1: Bias Detection**
Pre-trained language models demonstrate diverse viewpoints on social and economic issues, revealing underlying biases in their responses to targeted prompts.

**Phase 2: Bias Quantification**
- Models show varying degrees of bias when evaluated using the CrowS-Pairs dataset
- Stereotype log-probability scores effectively quantify stereotypical vs. anti-stereotypical associations
- Toxicity scores from Evaluate library measure offensive content generation

**Phase 3: Mitigation Strategies**
- **Counterfactual Data Augmentation**: Generate non-stereotypical examples (e.g., "John, a skilled nurse, gently tended to the elderly patient's wounds")
- **AI Fairness 360**: Comprehensive toolkit for detecting and mitigating bias throughout the AI lifecycle

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Conclusion

The evaluation reveals varying degrees of bias across language models:
- **ALBERT** shows the highest bias levels, possibly due to its extensive parameter count amplifying biases from pre-training data
- **GPT** demonstrates the best performance with minimal bias
- Trade-off exists between model size and bias: smaller models (XLNet) show reduced bias but may have limited capabilities

**Recommendations:**
- Implement counterfactual data augmentation during training
- Use AI Fairness 360 for systematic bias detection and mitigation
- Balance model capacity with fairness considerations
- Continuously evaluate models on diverse benchmark datasets

<p align="right">(<a href="#readme-top">back to top</a>)</p>
