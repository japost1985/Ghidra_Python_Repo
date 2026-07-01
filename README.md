# Ghidra Python Repository

This repository contains a collection of Python packages and dependencies for Ghidra reverse engineering development. It serves as a local package cache for offline development and version pinning.

## Contents

| Package          | Version       | Description                                     |
| ---------------- | ------------- | ----------------------------------------------- |
| **JPype1**       | 1.5.0         | Python-Java bridge for calling Java from Python |
| **kaitaistruct** | 0.10          | Declarative binary format parsing library       |
| **packaging**    | 26.0          | Core utilities for Python packages              |
| **pefile**       | 2023.2.7      | Portable Executable (PE) file parser            |
| **pyghidra**     | 3.0.2 / 3.1.0 | Python bindings for Ghidra                      |

## Structure

```
Ghidra_Python_Repo\
├── JPype1==1.5.0/          # Java-Python bridge
├── kaitaistruct==0.10/     # Binary format parser
├── packaging==26.0/        # Package utilities
├── pefile==2023.2.7/       # PE file parser
├── pyghidra==3.0.2/        # Ghidra Python bindings (v3.0.2)
└── pyghidra==3.1.0/        # Ghidra Python bindings (v3.1.0)
```

## Usage

### Installing from this repository

```bash
# Install a specific package
pip install --no-index --find-links=file:///PATH/TO/Ghidra_Python_Repo JPype1==1.5.0

# Or install all packages
pip install --no-index --find-links=file:///PATH/TO/Ghidra_Python_Repo -r requirements.txt
```

### For Ghidra Development

The `pyghidra` packages provide Python bindings to run Ghidra headlessly from Python:

```python
import pyghidra
pyghidra.start()
from ghidra.app.decompiler import DecompInterface
# ... use Ghidra APIs
```

## Requirements

- Python 3.8+
- Java 11+ (for JPype1 and pyghidra)
- Ghidra installation (for pyghidra to work)

## Notes

- This is a **local package cache** - packages are not developed here
- Multiple pyghidra versions are kept for compatibility testing
- Packages should be updated via pip from PyPI when new versions are needed
