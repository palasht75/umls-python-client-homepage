---
layout: default
title: "CrosswalkAPI Usage Guide"
---

# CrosswalkAPI Usage Guide

The `CrosswalkAPI` in the `UMLS Python Client` enables users to map concepts from one source terminology to another, which is essential for cross-referencing different medical coding systems. This guide provides an overview of how to use the `CrosswalkAPI` class effectively.

## Prerequisites

Before using the API, ensure you have your API key to interact with the UMLS database. If you don't have an API key, you can obtain one from the [UMLS User Authentication page](https://documentation.uts.nlm.nih.gov/rest/authentication.html).

## Setting Up

Here’s how to set up the `CrosswalkAPI`:

```python
import os
from umls_python_client import UMLSClient

# Set the API KEY
API_KEY = "YOUR_API_KEY_HERE"

# Folder path to save files
PATH = r"C:\path\to\your\output\directory"

# Initialize the CrosswalkAPI class with your API key
crosswalk_api = UMLSClient(api_key=API_KEY).crosswalkAPI
```
Replace `C:\path\to\your\output\directory` with the path where you want to save the output files.

## CrosswalkAPI Method: Retrieve Crosswalk Data

This method allows you to retrieve crosswalk data that maps a source concept identifier to target source vocabularies.

### Example Usage

```python
# Retrieve crosswalk data for a source and code
crosswalk_data = crosswalk_api.get_crosswalk(
    source="HPO",
    id="HP:0001947",
    target_source="SNOMEDCT_US",
    include_obsolete=False,
    page_number=1,
    page_size=10,
    return_indented=True,
    format="rdf",
    save_to_file=True,
    file_path=PATH
)
print(crosswalk_data)
```

In the above example:
- **source**: The source vocabulary (e.g., "HPO").
- **id**: The identifier in the source vocabulary (e.g., "HP:0001947").
- **target_source**: The target vocabulary to map to (e.g., "SNOMEDCT_US").
- **include_obsolete**: If `True`, includes obsolete mappings.
- **page_number**: The page of results to retrieve.
- **page_size**: The number of results per page.
- **return_indented**: If `True`, returns JSON in a readable indented format.
- **format**: Can be "json" or "rdf".
- **save_to_file**: If `True`, saves the output to a file.
- **file_path**: Path where the output will be saved.

## Arguments Overview

### `format`
- The `format` parameter accepts either "json" or "rdf". Note that "rdf" is only supported for native API calls, and not for additional functions.

### `return_indented`
- A boolean flag to decide if the returned JSON should be indented for readability.

### `save_to_file`
- A boolean flag to save the output directly to a file specified in `file_path`.

### `file_path`
- The path where the output file will be saved if `save_to_file` is set to `True`.

## Notes

- The `CrosswalkAPI` method provides a simple way to cross-reference different terminologies, making it easier to map between coding systems like HPO and SNOMEDCT_US.
- Ensure that the specified path in `file_path` exists to prevent file saving errors.
