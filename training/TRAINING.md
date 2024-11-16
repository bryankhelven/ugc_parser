
# Training the UGC Parser

This guide provides instructions on how to reproduce the training process to obtain the `ugc_parser.pt` model for dependency parsing using the **Stanza** library. The model is specifically trained on **user-generated content (UGC)**, leveraging the **DANTEStocks corpus V2**.

---

## Requirements

1. **Python 3.8+**
2. **PyTorch** (compatible with your hardware)
3. **Stanza** (installed with the provided `requirements.txt` file)

---

## File Structure

The `training` folder contains the following files:

- `pt_data.train.gold`: Gold-standard training data in CoNLL-U format.
- `pt_data.train.in`: Input training data in CoNLL-U format.
- `pt_data.dev.gold`: Gold-standard development/validation data.
- `pt_data.dev.in`: Input development/validation data.
- `pt_data.test.gold`: Gold-standard test data.
- `pt_data.test.in`: Input test data.

---

## Steps to Train the Parser

### 1. Install Dependencies

Navigate to the repository root and install the required dependencies:

```bash
pip install -r requirements.txt
```

---

### 2. Train the Parser

Run the training script to train the parser model:

```bash
python train_parser.py --train pt_data.train.in --dev pt_data.dev.in --gold_train pt_data.train.gold --gold_dev pt_data.dev.gold --output ugc_parser.pt
```

### Parameters:
- `--train`: Path to the input training data.
- `--dev`: Path to the input validation data.
- `--gold_train`: Path to the gold-standard training data.
- `--gold_dev`: Path to the gold-standard validation data.
- `--output`: Path to save the trained model file (e.g., `ugc_parser.pt`).

The training process will save the trained model in the root directory.

---

### 3. Evaluate the Parser

Once the model is trained, evaluate it using the test dataset:

```bash
python train_parser.py --eval --model ugc_parser.pt --test pt_data.test.in --gold_test pt_data.test.gold
```

### Parameters:
- `--eval`: Indicates evaluation mode.
- `--model`: Path to the trained model file.
- `--test`: Path to the input test data.
- `--gold_test`: Path to the gold-standard test data.

The script will output evaluation metrics such as:
- **Labelled Attachment Score (LAS)**
- **Unlabelled Attachment Score (UAS)**

---

### Why Do We Have `.gold` and `.in` Files?

1. **Input Files (`.in`)**:
   - These files are preprocessed with POS tags and serve as the input for training and testing.

2. **Gold-Standard Files (`.gold`)**:
   - These contain the correct dependency annotations for comparison during training and evaluation.


Ensure the input files (`.in`) are preprocessed to include POS tags before training.

---

## Acknowledgments

This work relies on the **DANTEStocks corpus V2** and the **Porttinari-base**, both annotated within the Universal Dependencies (UD) framework.

For further details, please visit:

- **Porttinari 2.0**
  - Repository: [https://sites.google.com/icmc.usp.br/poetisa/porttinari-2-0](https://sites.google.com/icmc.usp.br/poetisa/porttinari-2-0)

Please cite appropriately if you use this corpus in your research.
