# Organ Age Predictor

An organ age prediction tool based on proteomic data.

The predictor uses **Olink NPX proteomic measurements** together with sample metadata to generate predictions.

## System Requirements

The provided compiled module:

```text
pre.cp39-win_amd64.pyd
```

is built for:

* **Windows 64-bit**
* **CPython 3.9**

Python 3.9 is therefore recommended when using this release.

Install the required Python packages:

```bash
pip install pandas numpy cryptography
```

## Input Data

Two input files are required:

```text
metadata.csv
protein.csv
```

### 1. Metadata

`metadata.csv` should contain sample metadata.

* Sample IDs should be used as the row index.
* Chronological age should be provided in a column named `Age`.
* Age values should be numeric.

Example:

| Sample ID  | Age |
| ---------- | --: |
| Sample_001 |  52 |
| Sample_002 |  61 |
| Sample_003 |  47 |

### 2. Proteomic Data

`protein.csv` should contain the proteomic measurements.

* Sample IDs should be used as the row index.
* Protein names should be used as column names.
* Values should correspond to **Olink NPX measurements**.

Example:

| Sample ID  | Protein_A | Protein_B | Protein_C |
| ---------- | --------: | --------: | --------: |
| Sample_001 |      8.21 |      4.72 |      6.15 |
| Sample_002 |      7.95 |      4.91 |      5.88 |
| Sample_003 |      8.43 |      5.02 |      6.34 |

The sample IDs in the metadata and proteomic data should correspond to the same samples.

## Notes

### Python Version

The provided `.pyd` file is compiled specifically for CPython 3.9 on 64-bit Windows.

Using another Python version, such as Python 3.10, 3.11, or 3.12, may result in an import error.

You can check your Python version with:

```bash
python --version
```

A compatible environment should report Python 3.9.x.

### Platform Compatibility

The current binary release is intended for Windows 64-bit systems.

The provided `.pyd` file cannot be imported directly on Linux or macOS.
