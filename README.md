# Single-molecule analysis of TEAD4

## Overview

This repository contains the R code used to perform single-molecule binding energy analysis of TEAD4 transcription factor on DNA sequences, as described in the associated publication.

The analysis computes the binding energy landscape of TEAD4 along a DNA template (lambda DNA) using a position weight matrix (PWM) model, scanning both forward and reverse complement strands.

## Repository Contents

| File | Description |
|------|-------------|
| `20260325.R` | Main R script for TEAD4 binding energy analysis |
| `MA0809.2.txt` | TEAD4 position weight matrix (PWM) from JASPAR (MA0809.2) |
| `lamda DNA.txt` | Lambda DNA sequence used as the DNA template |
| `lamda_e04.csv` | Output: computed binding energy values at each genomic position |

## Dependencies

The following R packages are required:

- `stringr`
- `tidyr`
- `reshape2`

Install them with:

```r
install.packages(c("stringr", "tidyr", "reshape2"))
```

## Usage

1. Clone this repository:
   ```bash
   git clone https://github.com/RenZhiyun/Single-molecule-analysis-of-TEAD4-
   ```

2. Open `20260325.R` in RStudio or any R environment.

3. Set the working directory to the repository folder.

4. Run the script. The output `lamda_e04.csv` will be generated with binding energy values along the lambda DNA sequence.

## Method Summary

- The TEAD4 PWM (MA0809.2) is used to enumerate all 8-mer sequences with log-likelihood score above a threshold.
- Both forward and reverse complement strands of lambda DNA are scanned.
- Binding energies are computed and normalized, and positions with energy above a cutoff (`8 × log(0.4)`) are reported.
- Results are visualized as a binding energy plot and saved to `lamda_e04.csv`.

## License

This code is released under the [MIT License](LICENSE).

## Citation

If you use this code, please cite the associated publication (details to be added upon acceptance).
