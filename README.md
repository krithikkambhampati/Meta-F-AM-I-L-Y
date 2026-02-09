# Meta-F-AM-I-L-Y

MetaFam family Knowledge Graph analysis project containing graph exploration, clustering, rule mining, and link prediction tasks.

---

## Directory Structure

```
Meta-F-AM-I-L-Y/
│
|── README.md                   # This file
├── requirements.txt            # Python dependencies
│
├── task1/
│   ├── task1.ipynb            # Dataset exploration notebook
│   └── train.txt              # Training data (family relationship triples)
│
├── task2/
│   ├── task2.ipynb            # Community detection notebook
│   └── train.txt              # Training data
│
├── task3/
│   ├── task3.ipynb            # Rule mining notebook
│   └── train.txt              # Training data
│
└── task4/
    ├── task4.ipynb            # Link prediction notebook
    ├── diff_configs/          # Alternative model configurations
    │   ├── task4_v1.ipynb
    │   ├── task4_v2.ipynb
    │   ├── task4_v3.ipynb
    │   ├── task4_v4.ipynb
    │   └── task4_v5.ipynb
    └── model_checkpoint/      # Saved model files
        ├── config.pkl         # Model configuration
        ├── test_factory.pkl   # Test data factory
        ├── train_factory.pkl  # Training data factory
        └── transe_model.pth   # Trained model weights
        
        
```

---

## Setup Instructions

### 1. Install Dependencies

Navigate to the Meta-F-AM-I-L-Y directory and install all required packages:

```bash
cd Meta-F-AM-I-L-Y
pip install -r requirements.txt
```

This installs:
- NetworkX (graph analysis)
- Matplotlib, Seaborn (visualization)
- Pandas, NumPy (data manipulation)
- PyKEEN (knowledge graph embeddings)
- PyTorch (deep learning)
- Jupyter Lab (notebook environment)
- Additional support libraries

### 2. Verify Installation

Start Jupyter Lab to verify:

```bash
jupyter lab
```

---

## Running the Notebooks

### Task 1: Dataset Exploration

**Location**: `task1/task1.ipynb`

**Steps**:
1. Navigate to task1 directory:
   ```bash
   cd task1
   ```

2. Start Jupyter Lab:
   ```bash
   jupyter lab task1.ipynb
   ```

3. Execute cells in order from top to bottom

4. The notebook processes `train.txt` and generates:
   - Graph statistics
   - Relationship distributions
   - Network visualizations
   - Centrality analysis
   - Generational structure analysis


---

### Task 2: Family Clusters

**Location**: `task2/task2.ipynb`

**Steps**:
1. Navigate to task2 directory:
   ```bash
   cd task2
   ```

2. Start Jupyter Lab:
   ```bash
   jupyter lab task2.ipynb
   ```

3. Execute cells sequentially

4. The notebook performs:
   - Community detection using multiple algorithms
   - Modularity calculations
   - Community structure analysis
   - Bridge node identification


---

### Task 3: Rule Mining

**Location**: `task3/task3.ipynb`

**Steps**:
1. Navigate to task3 directory:
   ```bash
   cd task3
   ```

2. Start Jupyter Lab:
   ```bash
   jupyter lab task3.ipynb
   ```

3. Execute cells sequentially

4. The notebook performs:
   - Logical rule discovery
   - Rule validation (confidence, support, coverage)
   - Example instance extraction
   - Pattern visualization


---

### Task 4: Link Prediction

**Location**: `task4/task4.ipynb`

**Important**: This notebook was originally designed for Google Colab and requires modifications for local execution.

**Steps**:

1. Navigate to task4 directory:
   ```bash
   cd task4
   ```

2. Start Jupyter Lab:
   ```bash
   jupyter lab task4.ipynb
   ```

3. **Modify the notebook before running**:
   
   - **Skip or comment out Cell 1** (Google Drive mount):
     ```python
     # from google.colab import drive
     # drive.mount('/content/drive')
     ```
   
   - **Skip or comment out Cell 2** (pip install):
     ```python
     # !pip install pykeen torch pandas matplotlib
     ```
   
   - **Update file paths** (approximately line 19-20):
     ```python
     # Original:
     # train_path = "/content/drive/MyDrive/graphs-precog/train.txt"
     # test_path  = "/content/drive/MyDrive/graphs-precog/test.txt"
     
     # Updated for local (adjust paths to your actual data location):
     train_path = "path/to/your/train.txt"
     test_path  = "path/to/your/test.txt"
     ```

4. Execute remaining cells sequentially

5. The notebook performs:
   - Knowledge graph embedding training (TransE/DistMult/RotatE)
   - Model evaluation
   - Metric calculation (MRR, Hits@1, Hits@10)
   - Loss visualization
   - Model checkpoint saving to `model_checkpoint/`


**Hardware Note**: GPU recommended but not required. PyTorch will automatically use CUDA/MPS if available.

**Alternative Configurations**: The `diff_configs/` directory contains variants (task4_v1 through task4_v5) with different hyperparameters or architectures.

---

## Data Format

All `train.txt` files contain family relationship triples in the format:

```
head_entity    relation    tail_entity
```

Example:
```
Alice    motherOf    Bob
Bob      fatherOf    Charlie
```



