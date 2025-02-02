# TOPSIS Implementation for Model Evaluation

This repository contains a Python implementation of the **TOPSIS (Technique for Order Preference by Similarity to Ideal Solution)** method. The code evaluates multiple models based on given criteria and ranks them using TOPSIS scores.

## Table of Contents
1. [Introduction](#introduction)
2. [Input Data](#input-data)
3. [TOPSIS Algorithm](#topsis-algorithm)
4. [Usage](#usage)
5. [Output](#output)
6. [Dependencies](#dependencies)
7. [License](#license)

---

## Introduction

TOPSIS is a multi-criteria decision analysis method that ranks alternatives based on their similarity to the ideal solution. In this implementation, we evaluate language models (`GPT-2`, `GPT-2 Medium`, `GPT-2 Large`, `GPT-NEO`, `T5`) based on four criteria:
- **Coherence**
- **Fluency**
- **Relevance**
- **Perplexity**

The goal is to rank the models based on their performance across these criteria.

---

## Input Data

The input data is provided in a CSV file (`models.csv`) with the following format:

| Model       | Coherence | Fluency | Relevance | Perplexity |
|-------------|-----------|---------|-----------|------------|
| GPT-2       | 7         | 8       | 7         | 25         |
| GPT-2 Medium| 8         | 9       | 8         | 20         |
| GPT-2 Large | 9         | 9       | 9         | 15         |
| GPT-NEO     | 8         | 8       | 8         | 18         |
| T5          | 9         | 9       | 9         | 12         |

- **Model**: Name of the model.
- **Coherence**, **Fluency**, **Relevance**: Higher values indicate better performance.
- **Perplexity**: Lower values indicate better performance.

---

## TOPSIS Algorithm

The TOPSIS method involves the following steps:
1. **Normalization**: Normalize the decision matrix to ensure all criteria are on the same scale.
2. **Weighting**: Apply weights to the normalized matrix (equal weights in this case).
3. **Ideal Solutions**: Determine the ideal best and ideal worst solutions based on the impact of each criterion.
4. **Distance Calculation**: Calculate the Euclidean distance of each alternative from the ideal and negative-ideal solutions.
5. **TOPSIS Score**: Compute the TOPSIS score for each alternative.
6. **Ranking**: Rank the alternatives based on their TOPSIS scores.

---

## Usage

### Step 1: Save the Input Data
Save the input data in a CSV file named `models.csv` (as shown above).

### Step 2: Install Dependencies
Ensure you have the required Python libraries installed:
```bash
pip install numpy pandas
```

### Step 3: Run the Code
Save the provided Python code in a file (e.g., `topsis.py`) and run it:
```bash
python topsis.py
```

### Step 4: View the Output
The program will output a table with TOPSIS scores and ranks for each model.

---

## Output

The output will be a table with the following columns:
- **Model**: Name of the model.
- **Coherence**, **Fluency**, **Relevance**, **Perplexity**: Original scores.
- **TOPSIS Score**: Relative performance score (higher is better).
- **Rank**: Rank of the model based on TOPSIS score (1 is the best).

Example output:
```
          Model  Coherence  Fluency  Relevance  Perplexity  TOPSIS Score  Rank
0         GPT-2          7        8          7          25      0.321429     5
1  GPT-2 Medium          8        9          8          20      0.500000     4
2   GPT-2 Large          9        9          9          15      0.714286     2
3       GPT-NEO          8        8          8          18      0.571429     3
4           T5          9        9          9          12      0.857143     1
```

---

## Dependencies

- Python 3.x
- Libraries:
  - `numpy`
  - `pandas`

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---
