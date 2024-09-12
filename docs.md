---
layout: default
title: "Documentation"
---

# UMLS API Client Documentation

This documentation provides details on how to use the UMLS API Client, its features, and examples.

## Getting Started

1. **Installation**: First, install the package using pip:

    ```bash
    pip install umls-python-client
    ```

2. **Usage Example**:

    ```python
    from umls_python_client.umls_client import UMLSClient

    # Initialize the UMLS Client
    api_key = "YOUR_API_KEY"
    client = UMLSClient(api_key)

    # Perform a search
    result = client.searchAPI.search("diabetes")
    print(result)
    ```

## API Features

- **Search API**: Enables searching through UMLS data.
- **CUI API**: Retrieve Concept Unique Identifiers (CUIs).
- **Crosswalk API**: Map codes between terminologies.
- **Semantic Network API**: Access semantic relationships.

For more details, visit the [GitHub repository](https://github.com/palasht75/umls-client).
