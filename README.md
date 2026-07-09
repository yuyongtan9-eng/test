# test

Public synthetic test dataset for the epinet training/data-loading code.

This repository contains generated random `.npy` samples only. It does not contain real clinical, patient, or research data.

## Contents

- `synthetic_epinet_test.csv`: sample index used by `train.py`
- `data/synthetic_epinet_0000.npy` to `data/synthetic_epinet_0449.npy`
- Each sample is a NumPy `float32` array with shape `(29, 2000)`
- Total data payload is about 100 MiB

## Minimal usage

From an epinet checkout, point the code at this clone:

```bash
EPINET_DATA_FILE=/path/to/test/synthetic_epinet_test.csv \
EPINET_DATA_ROOT=/path/to/test \
EPINET_N_FOLD=1 \
EPINET_EPOCHS=1 \
EPINET_BATCH_SIZE=8 \
EPINET_VALID_BATCH_SIZE=8 \
EPINET_PROCESS_NUM=0 \
python train.py
```

This dataset is intended for smoke tests and pipeline checks, not model quality.
