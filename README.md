# DPRED

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)  
[![PyPI version](https://img.shields.io/pypi/v/DPRED)](https://pypi.org/project/DPRED/)  

**DPRED** is a command-line tool for automatic protein domain prediction and validation, based on Hidden Markov Models (HMMs). It fetches high-quality PDB structures for a user-specified PFAM domain, builds an HMM via HMMER, and evaluates predictive performance with k-fold cross-validation against UniProt sequences :contentReference[oaicite:0]{index=0}&#8203;:contentReference[oaicite:1]{index=1}.

---

## Features

- **Automated structure retrieval**: Downloads and filters PDB entries using Biopython.
- **Multiple structural alignment**: Leverages mTM-align to generate MSAs from 3D structures.
- **HMM construction**: Builds profile HMMs via HMMER’s `hmmbuild`.
- **Model validation**: Performs customizable k-fold cross-validation with HMMER’s `hmmsearch`.
- **Comprehensive metrics**: Reports Accuracy (ACC), Matthew’s Correlation Coefficient (MCC), Precision, Recall, F-Score, TPR, FPR, and confusion matrices.

---

## Dependencies
```python
import warnings
import sys
import requests
from requests.adapters import HTTPAdapter, Retry
import json
import re
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
import itertools
from collections import Counter
from sklearn import svm, preprocessing
from sklearn.metrics import (
    precision_recall_curve,
    matthews_corrcoef,
    accuracy_score,
    f1_score
)
from Bio.SeqUtils.ProtParam import ProteinAnalysis
import Bio.SeqUtils.ProtParamData
```

---

## Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/<YOUR_USERNAME>/DPRED.git
   cd DPRED
