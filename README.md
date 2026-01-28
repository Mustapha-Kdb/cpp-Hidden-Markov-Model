# 🛰️ HMM-Engine: C++ Implementation of Hidden Markov Models

A high-performance C++ library for sequence labeling and probabilistic modeling based on **Hidden Markov Models (HMM)**. This engine is specifically designed for NLP tasks such as **Part-of-Speech (POS) Tagging**, supporting both supervised and unsupervised learning paradigms.

[Image of a Hidden Markov Model state diagram with transition and emission probabilities]

## 🧠 Core Algorithms

This engine provides full implementations of the three fundamental pillars of HMM theory:

1.  **Decoding (Viterbi Algorithm):** Efficiently finds the most likely sequence of hidden states (e.g., tags) for a given observation sequence (e.g., words).
2.  **Learning (Baum-Welch / EM):** An unsupervised Expectation-Maximization approach to estimate model parameters from unlabeled data.
3.  **Evaluation (Forward-Backward):** Calculates the total probability of an observation sequence and computes posterior probabilities.

## ✨ Technical Highlights

* **Log-Domain Computation:** All probabilities are calculated using **log-transforms** to prevent numerical underflow, a common issue in long sequences.
* **Numerical Stability:** Includes a custom `ln_of_sum` function to perform additions in the log-space accurately.
* **EOS & UNK Management:** * Supports an **End of Sentence (EOS)** token for improved sequence boundary modeling.
    * Implements a threshold-based **Unknown Word (UNK)** handler for Out-of-Vocabulary (OOV) tokens.
* **Dual Training Modes:** * **Supervised:** Maximum Likelihood Estimation (MLE) using labeled data.
    * **Unsupervised:** Baum-Welch training for raw data discovery.

## 📁 Project Structure

| File | Description |
| :--- | :--- |
| `model.cpp/h` | The core engine: Matrix management ($A$, $B$, $\pi$), Viterbi, and Baum-Welch logic. |
| `use_hmm.cpp/h` | CLI Interface and specialized data parser for POS tagging files. |
| `compErrors.py` | Python evaluation tool to calculate global accuracy and error-by-state metrics. |
| `Makefile` | Build system for automated compilation. |

## 🛠️ Getting Started

### Compilation
Build the executable using the provided Makefile:
```bash
make
