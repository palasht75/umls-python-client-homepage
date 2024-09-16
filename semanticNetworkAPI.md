---
layout: default
title: "SemanticNetworkAPI Usage Guide"
---

# SemanticNetworkAPI Usage Guide

The `SemanticNetworkAPI` in the `UMLS Python Client` allows you to retrieve semantic type information using the TUI (Type Unique Identifier). This guide will demonstrate how to use the `SemanticNetworkAPI` class effectively.

## Prerequisites

Before using the API, ensure you have your API key to interact with the UMLS database. If you don't have an API key, you can obtain one from the [UMLS User Authentication page](https://documentation.uts.nlm.nih.gov/rest/authentication.html).

## Setting Up

Below is how to set up the `SemanticNetworkAPI` class:

```python
import os
from umls_python_client import UMLSClient

# Set the API KEY
API_KEY = "API_KEY_HERE"

# Folder path to save files
PATH = r"C:\path\to\your\output\directory"

# Initialize the SemanticNetworkAPI class with your API key
semantic_network_api = UMLSClient(api_key=API_KEY).semanticNetworkAPI
```

Replace `C:\path\to\your\output\directory` with the actual directory where you want to save the files.

## 1. Retrieve Semantic Type Information for TUI

This functionality allows you to retrieve semantic type information based on a specific TUI (Type Unique Identifier).

```python
# Fetch Semantic Type Information
tui = "T109"  # TUI for 'Anatomical Structure'
semantic_type_info = semantic_network_api.get_semantic_type(
    tui, save_to_file=True, file_path=PATH
)
print(semantic_type_info)
```
This example retrieves semantic type information for the TUI "T109" and saves it to the specified file.

## 2. Retrieve Semantic Type Information for Another TUI

You can retrieve semantic type information for a different TUI and choose to return it in RDF format as well.

```python
# Fetch Semantic Type Information for a different TUI and in RDF format
tui = "T121"  # TUI for 'Pharmacologic Substance'
semantic_type_info_2 = semantic_network_api.get_semantic_type(
    tui, format="rdf", save_to_file=True, file_path=PATH
)
print(semantic_type_info_2)
```

This example retrieves the semantic type information for the TUI "T121" and returns it in RDF format.

## Arguments Used

- `format`: Can be `"json"` or `"rdf"`. Use `"rdf"` only when supported by native APIs. 
- `save_to_file`: If set to `True`, the output will be saved to a specified file path.
- `file_path`: Path to save the output file.

These arguments help control the output format and allow the user to save the results to a file.

## Notes
- The `"rdf"` format only works with native APIs, and not with additional or custom functions.
- Make sure to set a valid file path when using `save_to_file` to avoid errors.
