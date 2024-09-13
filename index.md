---
layout: default
title: "Home"
---

# Welcome to the UMLS Python Client

The **UMLS Python Client** is a comprehensive and user-friendly API client for healthcare developers and researchers.
This client offers seamless access to UMLS data, making it easier to interact with various healthcare terminologies and codes. 
Our client provides five distinct groups of APIs to meet diverse healthcare needs.

## Why UMLS Python Client Stands Out
- **Comprehensive API Coverage**: Supports multiple UMLS APIs including Search, Source, CUI, Semantic Network, and Crosswalk.
- **Ease of Use**: Simple and intuitive interface for developers and non-developers alike.
- **Highly Customizable**: Flexible query parameters to meet specific requirements.
- **RDF Support**: Convert UMLS data into RDF format for semantic web applications.
- **Open Source**: Fully open for collaboration and improvement by the community.

## Available APIs

### 1. Search API
Search for concepts using various parameters such as words, exact matches, and codes across UMLS terminologies.
- Perform basic, partial, and exact searches.
- Support for specific vocabularies like **SNOMEDCT_US**, **LOINC**, etc.
- Retrieve identifiers like CUIs, source-asserted identifiers.

### 2. CUI API
Retrieve information for Concept Unique Identifiers (CUIs) from the UMLS Metathesaurus.
- Get details about a specific CUI.
- Fetch related atoms, ancestors, descendants, and relations for CUIs.

### 3. Source API
Fetch detailed information about source-asserted concepts or descriptors.
- Retrieve concepts and related terms from sources like **SNOMEDCT_US**, **LOINC**, and more.
- Fetch full hierarchies of concepts (ancestors, children, etc.).

### 4. Semantic Network API
Explore the UMLS semantic network and its relationships.
- Retrieve semantic type information for given TUIs (Type Unique Identifiers).
- Explore the relationships between different semantic types.

### 5. Crosswalk API
Map codes between different terminologies and vocabularies in healthcare.
- Translate between various vocabularies like SNOMED CT, ICD, and LOINC.
- Useful for interoperability between healthcare systems.

## Key Features
- **Automated Hierarchical Retrieval**: Fetch full hierarchies (ancestors, descendants) for any concept.
- **Logging Support**: Track requests and responses with detailed logging.
- **Error Handling**: Comprehensive error handling for invalid inputs, failed API requests, and more.
- **File Output**: Save your API responses directly into files for easy storage and access.
- **Customization**: Users can configure output formats (JSON, RDF) and save data as needed.

## How to Get Started

1. **Install the Package**  
   You can install the UMLS Python Client using pip:

   ```bash
   pip install umls-python-client
   ```

2. **Initialize the Client**  
   Initialize the UMLSClient with your API key:

   ```python
   from umls_python_client import UMLSClient
   api_key = "YOUR_API_KEY"
   umls_client = UMLSClient(api_key=api_key)
   ```

3. **Explore the APIs**  
   You can explore the available APIs as follows:

   - Search API: `umls_client.searchAPI`
   - Source API: `umls_client.sourceAPI`
   - CUI API: `umls_client.cuiAPI`
   - Semantic Network API: `umls_client.semanticNetworkAPI`
   - Crosswalk API: `umls_client.crosswalkAPI`

## Documentation
For complete API documentation and usage examples, visit the [UMLS Python Client GitHub Repository](https://github.com/palasht75/umls-client).

## Contribute
This project is open source, and contributions are welcome! If you have any improvements or new ideas, feel free to open a pull request.

[Get Started](/umls-python-client-homepage/docs) | [About the Project](/umls-python-client-homepage/about) | [Contributors](/umls-python-client-homepage/contributors)

