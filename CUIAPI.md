---
layout: default
title: "CUIAPI Usage Guide"
---

# CUIAPI Usage Guide

The `CUIAPI` in the `UMLS Python Client` provides methods to interact with Concept Unique Identifiers (CUIs) in UMLS. This guide walks you through different functionalities using the `CUIAPI`.

## Prerequisites

Before using the API, ensure you have your API key to interact with the UMLS database. If you don't have an API key, you can obtain one from the [UMLS User Authentication page](https://documentation.uts.nlm.nih.gov/rest/authentication.html).

## Setting Up

Here's how to set up the `CUIAPI` class:

```python
import os
from umls_python_client import UMLSClient

# Set the API KEY
API_KEY = "YOUR_API_KEY_HERE"

# Folder path to save files
PATH = r"C:\path\to\your\output\directory"

# Initialize the CUIAPI class with your API key
cui_api = UMLSClient(api_key=API_KEY).cuiAPI
```

## Available Arguments for API Calls
- **return_indented**: Boolean to indicate if the response should be indented for readability.
- **save_to_file**: Boolean indicating if the result should be saved to a file.
- **file_path**: Path to the directory where the output files will be saved.

> **Note**: The `"rdf"` format will only work with the native UMLS APIs and not with additional functions. `cuiAPI` currently does not support `"rdf"`.

## 1. Fetch CUI Information

The `get_cui_info` method fetches detailed information about a specified CUI.

```python
# Fetch CUI Information
cui_info = cui_api.get_cui_info(cui="C0011849", save_to_file=True, file_path=PATH)
print(cui_info)
```

## 2. Fetch Atoms for a CUI

This method fetches atoms related to the specified CUI with additional filtering options.

```python
# Fetch Atoms for a CUI
cui_atoms = cui_api.get_atoms(
    cui="C0011849",
    sabs="SNOMEDCT_US",
    ttys="PT",
    language=None,
    include_obsolete=False,
    include_suppressible=False,
    page_number=1,
    page_size=25,
    save_to_file=True,
    file_path=PATH,
)
print(cui_atoms)
```

## 3. Fetch Definitions for a CUI

The `get_definitions` method retrieves definitions for the specified CUI.

```python
# Fetch Definitions for a CUI
cui_definition = cui_api.get_definitions(
    cui="C0011849",
    sabs="SNOMEDCT_US",
    page_number=1,
    page_size=25,
    save_to_file=True,
    file_path=PATH,
)
print(cui_definition)
```

## 4. Fetch Relations for a CUI

This method fetches relationships for the given CUI, including relation labels and additional filters.

```python
# Fetch Relations for a CUI
cui_relations = cui_api.get_relations(
    cui="C0011849",
    sabs="SNOMEDCT_US",
    include_relation_labels=None,
    include_additional_labels=None,
    include_obsolete=False,
    include_suppressible=False,
    page_number=1,
    page_size=25,
    save_to_file=True,
    file_path=PATH,
)
print(cui_relations)
```

Now you're all set to explore and retrieve data from UMLS using the `CUIAPI`. Make sure to experiment with different CUIs, filters, and parameters to fully utilize the power of this API.

