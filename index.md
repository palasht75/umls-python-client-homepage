---
layout: default
title: "Home"
---


# UMLS Python Client

Welcome to the **UMLS Python Client** - your comprehensive toolkit for integrating and interacting with UMLS (Unified Medical Language System) data in Python. This client enables healthcare developers, researchers, and data scientists to access, manipulate, and work with various UMLS data resources in an efficient and intuitive manner.

## Why UMLS Python Client Stands Out

The **UMLS Python Client** is not just another API client. It's designed specifically with the needs of healthcare professionals and researchers in mind. Here's what makes it unique:

- **Comprehensive API Coverage**: This package groups five major API functionalities into one:
    - **Search API**: Quickly and efficiently perform searches for healthcare-related terms, concepts, and codes.
    - **CUI API**: Retrieve Concept Unique Identifiers (CUIs) that represent unique concepts in the UMLS.
    - **Source API**: Access source-asserted data, which allows you to retrieve healthcare data from multiple terminologies.
    - **Crosswalk API**: Seamlessly map healthcare codes between various terminologies.
    - **Semantic Network API**: Dive into the relationships between different concepts with the UMLS Semantic Network.

- **Ease of Use**: Each API is easily accessible through a clear and intuitive interface. The client abstracts complex API interactions into simple function calls.

- **Flexibility**: Handle results in JSON or RDF format, and control the depth of the search in recursive queries. You can also easily save the output to files for further processing.

- **Customization Options**: With flexible query parameters, users can fine-tune searches and fetches to match their exact needs.

- **Ready for Production**: Designed for scalability, this client works efficiently in both research and production environments. It’s built to handle large-scale healthcare data retrieval and mapping tasks.

## APIs Included in the UMLS Python Client

### 1. Search API
Perform searches in the UMLS metathesaurus with various parameters. Search by words, exact match, or even partial matches and get results for concepts, source vocabularies, and more.

### 2. CUI API
The CUI API helps retrieve detailed information about Concept Unique Identifiers. You can explore all related concepts, find attributes, relationships, and more.

### 3. Source API
Explore source-asserted data. This API allows you to fetch source-based concepts, relationships, and hierarchies, making it easier to interact with specific terminologies like SNOMEDCT_US, ICD-10, etc.

### 4. Crosswalk API
The Crosswalk API is crucial for mapping codes between different healthcare terminologies. This allows you to transform codes from one system to another, ensuring data interoperability.

### 5. Semantic Network API
The Semantic Network API enables the exploration of the semantic structure within the UMLS. It helps you understand how concepts relate to each other, including hierarchical relationships like parent-child and broader-narrower.

## Key Features

- **Highly Customizable**: Modify query parameters such as source vocabularies, languages, and search types to match your research or development needs.
- **Logging Support**: Every request made through the client is logged for transparency, making it easier to debug and track API interactions.
- **Save Outputs**: Save the results of searches, hierarchy retrieval, and mappings to files in multiple formats for later use or analysis.
- **Easy-to-Understand Outputs**: Structured JSON and RDF outputs for easy data manipulation in Python.

## How to Get Started

1. **Installation**: You can install the UMLS Python Client via pip:
   ```
   pip install umls-python-client
   ```

2. **Setup**: Once installed, initialize the client with your UMLS API key:
   ```python
   from umls_python_client.umls_client import UMLSClient
   client = UMLSClient(api_key='YOUR_API_KEY')
   ```

3. **Perform a Search**:
   ```python
   search_results = client.searchAPI.search(search_string="diabetes")
   print(search_results)
   ```

4. **Retrieve CUIs**:
   ```python
   cui_info = client.cuiAPI.get_cui_info("C0011849")
   print(cui_info)
   ```

## License

The UMLS Python Client is licensed under the **Apache License 2.0**, ensuring that you can freely use, modify, and distribute this client while attributing the original authors.

## Contribution

We welcome contributions! Feel free to submit pull requests or raise issues on our [GitHub repository](https://github.com/palasht75/umls-client).

For more details on how to contribute or report issues, visit the repository and browse through the issues section or submit new suggestions!

---

Thank you for using UMLS Python Client. This project aims to simplify your work with UMLS data so you can focus more on your research or application development. If you have any questions or need further support, feel free to explore the documentation or reach out via GitHub.

