---
icon: lucide/hard-drive-download
title: Dataset access
---

## Python download and import

We have prepared a Python package, [nwesdap](https://github.com/nwesdap/nwesdap-python), that automatically downloads and imports the NWESDAP dataset as a [pandas DataFrame](https://pandas.pydata.org/docs/dev/user_guide/dsintro.html#dataframe).

### Installation

To install, use either of the following:
```
pip install nwesdap
```
```
conda install conda-forge::nwesdap
```

You'll also need to install either [pyarrow](https://arrow.apache.org/docs/python/index.html) or [fastparquet](https://fastparquet.readthedocs.io/en/latest/index.html) separately.

### Usage

!!! warning "Stable version not yet available"

    The version of NWESDAP currently published on Zenodo is a *release candidate* and not yet finalised.
    
    It's fine for setting up workflows, but it should NOT be used for any research!

All you need is:

```python
from nwesdap import get_nwesdap

df = get_nwesdap()
```

`get_nwesdap()` takes the following steps:

1. Check if the latest NWESDAP dataset is already saved on your computer.
2. Download it from the [Zenodo archive](#zenodo-archive) if not.
3. Import the dataset as a pandas DataFrame (`df`).
4. Rename the columns to be more consistent with the [GLODAP dataset](https://github.com/mvdh7/glodap#glodap).

See the function's docstring for more details on the contents of the DataFrame.

!!! info "`get_nwesdap` keyword arguments"
    
    - `path_nwesdap`: defaults to `"~/.nwesdap"`, where `~` is the output of `pathlib.Path.home()`.
    
    *The path to the directory where NWESDAP files are saved.*

    - `rename_like_glodap`: defaults to `True`.
    
    *Whether to rename the DataFrame columns to be more like the GLODAP dataset.*

## Zenodo archive

!!! warning "Stable version not yet available"

    The version of NWESDAP currently published on Zenodo is a *release candidate* and not yet finalised.
    
    It's fine for setting up workflows, but it should NOT be used for any research!

If you're not working in Python, you can download the data files directly from the [Zenodo archive](https://doi.org/10.5281/zenodo.23495660).  The main NWESDAP dataset is available in CSV, XLSX and Parquet formats.

The specific citation for the current most recent version of the dataset is below.

!!! abstract "NWESDAP dataset citation"

    Brandon, M., Humphreys, M. P., Koek, A. C. (Cuun), Ádler, M. A., Bakker, D. C. E., Becker, M., Bittig, H. C., Bozec, Y., Chierici, M., Darelius, E., Findlay, H. S., Gkritzalis, T., Ivimey-Cook, R., Jones, E. M., Knockaert, M., Lange, N., Leseurre, C., Lødemel, H. H., Macovei, V. A., McGovern, E., McGrath, T., Metzl, N., O’Donnell, G., O’Sullivan, E. M., Ourradi, Y., Petton, S., Salvanes, A. G. V., Skjelvan, I., and Voynova, Y. G.: Northwest European Shelf Data Analysis Product (NWESDAP), version 1.2026rc2, Zenodo, https://doi.org/10.5281/zenodo.23555137, 2026.
