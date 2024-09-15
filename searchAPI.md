---
layout: default
title: "SearchAPI Usage Guide"
---

# SearchAPI Usage Guide

The `SearchAPI` in the `UMLS Python Client` provides a variety of search capabilities to query UMLS Metathesaurus data. This guide provides examples demonstrating different search functionalities using the `SearchAPI`.

## Prerequisites

Before using the API, ensure you have your API key to interact with the UMLS database. If you don't have an API key, you can obtain one from the [UMLS User Authentication page](https://documentation.uts.nlm.nih.gov/rest/authentication.html).

## Setting Up

Here's how to set up the `SearchAPI` class:

```python
import os
from umls_python_client import UMLSClient

# Set the API KEY
API_KEY = "YOUR_API_KEY_HERE"

# Folder path to save files
PATH = r"C:\path\to\your\output\directory"

# Initialize the SearchAPI class with your API key
search_api = UMLSClient(api_key=API_KEY).searchAPI
```

## Available Arguments for API Calls
- **format**: Specifies the response format. Supported values: `"json"`, `"rdf"`.
- **return_indented**: Boolean to indicate if the response should be indented for readability.
- **save_to_file**: Boolean indicating if the result should be saved to a file.
- **file_path**: Path to the directory where the output files will be saved.

> **Note**: The `"rdf"` format will only work with the native UMLS APIs and not with additional functions.

## 1. Perform a Basic Search

The basic search method retrieves UMLS data for a given term.

```python
# Perform a Basic Search
search_results = search_api.search(
    search_string="diabetes",  # The term to search for
    input_type=None,  # None implies search for any input type
    include_obsolete=False,  # Don't include obsolete terms
    include_suppressible=False,  # Don't include suppressible terms
    return_id_type="concept",  # Return UMLS Concept Unique Identifiers (CUIs)
    search_type="words",  # Search using word-based matching
    page_number=1,  # Start from the first page
    page_size=10,  # Limit the result to 10 items per page
    save_to_file=True,
    file_path=PATH
)
print(search_results)
```

## 2. Search with Specific Vocabularies

You can limit the search to a specific vocabulary source, such as SNOMEDCT_US.

```python
# Search with Specific Vocabularies
search_results_vocab = search_api.search(
    search_string="hypertension",  # Search for 'hypertension'
    sabs="SNOMEDCT_US",  # Limit the search to SNOMEDCT_US vocabulary
    return_id_type="concept",  # Return CUIs
    page_number=1,  # Start from the first page
    page_size=10,  # Limit to 10 results per page
    save_to_file=True,
    file_path=PATH
)
print(search_results_vocab)
```

## 3. Perform an Exact Match Search

Use the `"exact"` search type to look for an exact match of the search term.

```python
# Perform an Exact Match Search
search_results_exact = search_api.search(
    search_string="myocardial infarction",  # Search for the exact term
    search_type="exact",  # Use exact matching
    return_id_type="concept",  # Return CUIs
    page_number=1,  # Start from the first page
    page_size=10,  # Limit to 10 results per page
    save_to_file=True,
    file_path=PATH
)
print(search_results_exact)
```

## 4. Perform a Partial Search

Enable partial search to look for terms that contain the search string.

```python
# Perform a Partial Search
search_results_partial = search_api.search(
    search_string="fracture",  # Search for 'fracture'
    partial_search=True,  # Enable partial search
    return_id_type="concept",  # Return CUIs
    page_number=1,  # Start from the first page
    page_size=10,  # Limit to 10 results per page
    save_to_file=True,
    file_path=PATH
)
print(search_results_partial)
```

## 5. Perform a Search Including Obsolete Terms

You can include obsolete terms in the search results by setting `include_obsolete` to `True`.

```python
# Perform a Search Including Obsolete Terms
search_results_obsolete = search_api.search(
    search_string="insulin",  # Search for 'insulin'
    include_obsolete=True,  # Include obsolete terms in the search
    return_id_type="concept",  # Return CUIs
    page_number=1,  # Start from the first page
    page_size=10,  # Limit to 10 results per page
    format="rdf",
    save_to_file=True,
    file_path=PATH
)
print(search_results_obsolete)
```
