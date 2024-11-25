
# UGC Parser

**UGC Parser** is a dependency parser specifically trained on user-generated content (UGC) in Brazilian Portuguese, leveraging the **DANTEStocks corpus**. This repository provides the tools to use the parser, evaluate it, and reproduce its training.

---

## Features

- **Specialized for UGC**: Tailored for tweets and other non-canonical text in Brazilian Portuguese.
- **Customizable**: Includes tools for training on new datasets and fine-tuning.
- **Stanza-Based**: Built using the Stanford NLP Group's [Stanza](https://stanfordnlp.github.io/stanza/) library.

---

## Requirements

- **Python 3.8+**
- **PyTorch**
- Additional dependencies listed in `requirements.txt`.

---

## Repository Contents

- `README.md`: Instructions on how to use and train the parser.
- `requirements.txt`: Python dependencies for the project.
- `download_model.py`: Script to download the trained UGC parser model.
- `run_parser.py`: Script to parse `.conllu` files using the model.
- `training/`: Directory containing training data and scripts.
- `example.conllu`: Example input file for testing the parser.

---

## Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/your_username/ugc_parser.git
cd ugc_parser
```

---

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

---

### 3. Download the Trained Model

Run the following command to download the UGC parser model:

```bash
python download_model.py
```

This will place the model in the `models/` directory.

---

### 4. Test the Parser

Use the provided example file to test the parser:

```bash
python run_parser.py example.conllu
```

The output will be saved as `output.conllu` in the current directory.

---

### 5. Parse Your Own Files

To parse your own `.conllu` files, use:

```bash
python run_parser.py path/to/your_file.conllu
```

---

### 6. Reproduce the Training

If you wish to train or fine-tune the parser, navigate to the `training/` directory and follow the instructions in `TRAINING.md`.

---

## Additional Information

- The scripts are compatible with Python 3.8 and have been tested on Windows and Linux.
- For more information about Stanza and its capabilities, visit the [Stanza Documentation](https://stanfordnlp.github.io/stanza/).

## Troubleshooting

If you encounter any issues or have questions, please open an issue in this repository.


---

**Note:**

- The UGC parser model (`ugc_parser.pt`) is hosted on GitHub Releases and will be downloaded automatically by the `download_model.py` script.
- Ensure that you have an internet connection when running the script to download the model.
- The model file is larger than usual for git (approximately 150MB), so the download may take some time depending on your internet speed.


## Acknowledgments

- This work was carried out at the Center for Artificial Intelligence of the University of São Paulo (C4AI - [http://c4ai.inova.usp.br/](http://c4ai.inova.usp.br/)), with support by the São Paulo Research Foundation (FAPESP grant #2019/07665-4) and by the IBM Corporation. The project was also supported by the Ministry of Science, Technology and Innovation, with resources of Law N. 8.248, of October 23, 1991, within the scope of PPI-SOFTEX, coordinated by Softex and published as Residence in TIC 13, DOU 01245.010222/2022-44.

- UGC parser was developed using the [Stanza](https://stanfordnlp.github.io/stanza/) library. We thank the Stanford NLP Group for providing this tool for the NLP community.


- This work relies on the **DANTEStocks corpus V2** and the **Porttinari-base**, both annotated within the Universal Dependencies (UD) framework.

For further details, please visit **Porttinari 2.0** website at:
- [https://sites.google.com/icmc.usp.br/poetisa/porttinari-2-0](https://sites.google.com/icmc.usp.br/poetisa/porttinari-2-0)

---

## How to cite

Barbosa, B.K.S. (2024). Descrição sintático-semântica de nomes predicadores em tweets do mercado financeiro em português. MSc Dissertation. Universidade Federal de São Carlos, São Carlos/SP, 208p.

Di Felippo, Nunes, M.G.V.; Barbosa, B.K.S. (2024). A Dependency Treebank of Tweets in Brazilian Portuguese: Syntactic Annotation Issues and Approach. In the Proceedings of the 15th Symposium in Information and Human Language Technology (STIL). November, 17-21. p. 192-201. DOI: https://doi.org/10.5753/stil.2024.245383.


