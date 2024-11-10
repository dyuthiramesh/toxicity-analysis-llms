# Toxicity Analysis of Large Language Models (LLMs)

This repository contains a comprehensive analysis of large language models (LLMs) to assess their toxicity across various dimensions. The models evaluated include Llama-3.2-11b-text-preview, Mixtral-8x7b-32768, Gemma2-9b-it, and Llama3-groq-8b-8192-tool-use-preview. The analysis uses the RealToxicityPrompts dataset and the Detoxify toxicity detection tool to evaluate the models on metrics such as general toxicity, threat generation, severe toxicity, obscene content, insults, and identity attacks.

## Table of Contents

- [Introduction](#introduction)
- [Models Used](#models-used)
- [Dataset](#dataset)
- [Methodology](#methodology)
- [Results](#results)
- [Discussion](#discussion)
- [Installation](#installation)
- [Usage](#usage)
- [License](#license)

## Introduction

This research compares multiple state-of-the-art language models on their ability to generate toxic content. The goal is to understand how well different models handle harmful language and to explore the mitigation techniques available. The findings help inform best practices for the development of safer and more ethical AI systems.

## Models Used

The following LLMs were evaluated in this study:

- **Llama-3.2-11b-text-preview**
- **Mixtral-8x7b-32768**
- **Gemma2-9b-it**
- **Llama3-groq-8b-8192-tool-use-preview**

These models were selected for their diverse architectures, training data, and scales, enabling an analysis of how such factors influence the generation of toxic content.

## Dataset

This study uses the **RealToxicityPrompts** dataset, designed to probe LLMs for toxic language generation. It contains prompts crafted to elicit potentially harmful responses from models, providing a robust benchmark for toxicity assessment.

- **Dataset Source**: [RealToxicityPrompts](https://github.com/gehman/realtoxicityprompts)

## Methodology

1. **Data Collection**: We selected a subset of 100 prompts from the RealToxicityPrompts dataset to evaluate the models.
2. **Toxicity Detection**: The Detoxify library was used to measure toxicity across six dimensions: Toxicity, Threat, Severe Toxicity, Obscene Content, Insults, and Identity Attacks.
3. **Models Tested**: Four LLMs were evaluated on their responses to these prompts.

For further details, refer to the [Methodology section](#methodology).

## Results

### Toxicity Comparison

The average toxicity scores for each model across the six dimensions are summarized in the table below. Additionally, bar plots are provided for each metric to visually compare the models' performance.

| **Metric**            | **Llama-3.2-11b** | **Mixtral-8x7b** | **Gemma2-9b** | **Llama3-groq-8b** |
|-----------------------|-------------------|------------------|---------------|--------------------|
| **Toxicity**          | 0.0151            | 0.0039           | 0.0091        | 0.0039             |
| **Threat**            | 0.00024           | 0.00016          | 0.00016       | 0.00017            |
| **Severe Toxicity**   | 0.00029           | 0.00015          | 0.00015       | 0.00015            |
| **Obscene Content**   | 0.0111            | 0.0021           | 0.0031        | 0.0033             |
| **Insult**            | 0.0032            | 0.00037          | 0.00065       | 0.00054            |
| **Identity Attack**   | 0.00054           | 0.00023          | 0.00030       | 0.00022            |

Each metric has an associated bar plot for further comparison.

## Discussion

The results highlight significant differences in how the evaluated models handle various toxicity dimensions. For instance, **Llama-3.2-11b** exhibited higher toxicity across most metrics, indicating a need for improved toxicity control. On the other hand, models like **Mixtral-8x7b-32768** showed better moderation performance, suggesting that architecture and training data significantly impact a model's safety profile.

## Installation

### Requirements

- Python 3.7+
- Required libraries: `torch`, `transformers`, `detoxify`, `matplotlib`, `pandas`, `numpy`

### Setup

1. Clone this repository:
   ```bash
   git clone https://github.com/dyuthiramesh/toxicity-analysis-llms.git
   cd toxicity-analysis-llms
   ```

2. Run the ipynb notebook on colab:

The output will include toxicity scores and visualizations (bar plots) for each model across various metrics.


### Additional Notes

- **RealToxicityPrompts** and **Detoxify** libraries are integral to the analysis. For more details, refer to their respective documentation.
- You can modify the script to analyze additional models or use a different set of prompts.
- Feel free to contribute to this repository by submitting issues or pull requests.