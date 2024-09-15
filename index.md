---
layout: default
title: "Home"
---
# Welcome to the UMLS Python Client

The **UMLS Python Client** is a comprehensive, modular, and user-friendly API client designed for healthcare developers and researchers. It offers seamless access to UMLS data, simplifying interactions with various healthcare terminologies and codes. Our client provides five distinct groups of APIs, encompassing every single REST API from UMLS with all query parameters and additional features.

## Why Choose UMLS Python Client

- **Modular Design**: Unlike other packages, our client is modular, providing separate APIs for each UMLS service. This modularity allows for easy integration and customization to meet your specific needs.

- **Comprehensive Coverage**: A one-stop destination that includes every UMLS REST API, ensuring you have access to all necessary endpoints and functionalities.

- **Enhanced Functionality**: Additional features like response formatting in RDF or JSON, file saving options, and extended functions built on top of existing endpoints enhance your development experience.

- **Best Practices Implementation**: Built using the latest best practices, including type hinting for improved code readability and proper error logging for easier debugging.

- **Future-Proof**: We promise support for all future changes to UMLS APIs, ensuring your projects remain up-to-date with the latest developments.

- **Comprehensive Documentation and Notebooks**: We provide detailed documentation and interactive Jupyter notebooks, which are not offered by others, to help you get started quickly and efficiently.

- **Open Source Collaboration**: Fully open for collaboration and improvement by the community. Your contributions are welcome to make this project even better.

## Available APIs

Our client divides all REST APIs into five main parts for better organization and ease of use:

### 1. Search API

Search for concepts using various parameters such as words, exact matches, and codes across UMLS terminologies.

- Perform basic, partial, and exact searches.
- Support for specific vocabularies like **SNOMEDCT_US**, **LOINC**, etc.
- Retrieve identifiers like CUIs and source-asserted identifiers.

### 2. CUI API

Retrieve information for Concept Unique Identifiers (CUIs) from the UMLS Metathesaurus.

- Get detailed information about specific CUIs.
- Fetch related atoms, ancestors, descendants, and relations for CUIs.

### 3. Source API

Fetch detailed information about source-asserted concepts or descriptors.

- Retrieve concepts and related terms from sources like **SNOMEDCT_US**, **LOINC**, and more.
- Access full hierarchies of concepts (ancestors, children, etc.).

### 4. Semantic Network API

Explore the UMLS Semantic Network and its relationships.

- Retrieve semantic type information for given TUIs (Type Unique Identifiers).
- Explore relationships between different semantic types.

### 5. Crosswalk API

Map codes between different terminologies and vocabularies in healthcare.

- Translate between various vocabularies like **SNOMED CT**, **ICD**, and **LOINC**.
- Facilitate interoperability between healthcare systems.

## Key Features

- **Automated Hierarchical Retrieval**: Fetch full hierarchies (ancestors, descendants) for any concept effortlessly.
- **Enhanced Response Formatting**: Convert UMLS data into RDF or JSON formats for semantic web applications and easy data manipulation.
- **File Output Support**: Save your API responses directly into files for easy storage and access.
- **Logging and Error Handling**: Track requests and responses with detailed logging and comprehensive error handling for invalid inputs, failed API requests, and more.
- **Type Hinting**: Code is written with type hints for better code readability and easier maintenance.
- **Customization**: Configure output formats and save data as needed to suit your workflow.

## How to Get Started

### 1. Install the Package

Install the UMLS Python Client using pip:

```bash
pip install umls-python-client
```

### 2. Initialize the Client

Initialize the \`UMLSClient\` with your API key:

```python
from umls_python_client import UMLSClient

api_key = "YOUR_API_KEY"
umls_client = UMLSClient(api_key=api_key)
```

### 3. Explore the APIs

You can explore the available APIs below:

| API Name               | Description                                      | Documentation Link                                             | Colab Notebook Link                                                                                                 |
|------------------------|--------------------------------------------------|----------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------|
| **SearchAPI**          | Search the UMLS database for terms and concepts. | [/searchAPI](/umls-python-client-homepage/searchAPI)           | [Open in Colab](https://colab.research.google.com/drive/1ICQFoZqfsW6YvcaoRo-DtZR2QAWmqFI0)                          |
| **CUIAPI**             | Retrieve Concept Unique Identifier information.  | [/CUIAPI](/umls-python-client-homepage/CUIAPI)                 | [Open in Colab](https://colab.research.google.com/drive/1ICQFoZqfsW6YvcaoRo-DtZR2QAWmqFI0)                          |
| **SourceAPI**          | Access source-specific content in UMLS.          | [/sourceAPI](/umls-python-client-homepage/sourceAPI)           | [Open in Colab](https://colab.research.google.com/drive/1ICQFoZqfsW6YvcaoRo-DtZR2QAWmqFI0)                          |
| **SemanticNetworkAPI** | Explore semantic relationships.                  | [/semanticNetworkAPI](/umls-python-client-homepage/semanticNetworkAPI) | [Open in Colab](https://colab.research.google.com/drive/1ICQFoZqfsW6YvcaoRo-DtZR2QAWmqFI0)                          |
| **CrosswalkAPI**       | Map concepts across vocabularies.                | [/crosswalkAPI](/umls-python-client-homepage/crosswalkAPI)     | [Open in Colab](https://colab.research.google.com/drive/1ICQFoZqfsW6YvcaoRo-DtZR2QAWmqFI0)                          |

*Click on the documentation links to learn more about each API and use the Colab notebooks to try them out interactively.*
## Example Usage

Here's a quick example of how to use the **SearchAPI** to find information about "diabetes":

```python
from umls_python_client import SearchAPI

api_key = "YOUR_API_KEY"
search_api = SearchAPI(api_key=api_key)

results = search_api.search_terms(query="diabetes", source="SNOMEDCT_US")
print(results)
```

*For more examples, please refer to our [documentation](/umls-python-client-homepage/searchAPI) and interactive notebooks.*
## Documentation and Resources

- **PyPI Package**: [UMLS Python Client on PyPI](https://pypi.org/project/umls-python-client/1.0.3/)
- **UMLS REST APIs Home**: [UMLS API Documentation](https://documentation.uts.nlm.nih.gov/rest/home.html)
- **Project Repository**: [GitHub Repository](https://github.com/your-repo/umls-python-client)

## Contribute

We welcome contributions from the community! If you have any improvements or new ideas, feel free to open a pull request or an issue on our GitHub repository.

- [About the Project](/umls-python-client-homepage/about)
- [Contributors](/umls-python-client-homepage/contributors)

## Support and Future Updates

We are committed to maintaining and updating this client to support all future changes in the UMLS APIs. If you encounter any issues or have feature requests, please open an issue on our [GitHub repository](https://github.com/your-repo/umls-python-client).

## Contact Us

For any questions or support, please contact us at [palasht75@gmail.com](palasht75@gmail.com).

---
