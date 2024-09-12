
---
layout: default
title: "Home"
---

# Welcome to the UMLS Python Client

### Simplifying Healthcare Data Access with Python

The **UMLS Python Client** is a powerful and easy-to-use library designed for healthcare developers and researchers to interact seamlessly with **Unified Medical Language System (UMLS)** APIs. It offers a range of functionalities that allow you to perform searches, retrieve concept identifiers, map codes, explore semantic networks, and more.

This client serves as your bridge to access vast healthcare terminologies and concepts, ensuring quick and efficient integration of UMLS data into your Python applications.

---

## Key Features

### 🌟 Why Choose the UMLS Python Client?

- **Ease of Use**: Built with a simple and clean interface, allowing you to quickly integrate UMLS data into your applications.
- **Comprehensive API Coverage**: Supports five key UMLS APIs — **Search API**, **CUI API**, **Source API**, **Semantic Network API**, and **Crosswalk API**.
- **Flexible Output Formats**: Retrieve data in **JSON** or **RDF** formats based on your specific needs.
- **Optimized for Performance**: Efficiently fetch hierarchical data like parent-child relationships and attribute aggregation without compromising speed.
- **Extensible**: Supports custom enhancements and seamless integration with other tools.
- **Open Source**: Freely available for anyone to use and contribute, licensed under the **Apache 2.0 License**.

---

## 📘 UMLS Python Client API Groups

### 1. **Search API**
Effortlessly search through the UMLS Metathesaurus. Find concepts, codes, and source-asserted identifiers using human-readable terms.

- **Features**:
  - Perform basic, partial, or exact searches for concepts like "diabetes" or "hypertension".
  - Customize searches to include obsolete or suppressible terms.
  - Limit results to specific vocabularies like SNOMED-CT or RxNorm.

[Learn more about Search API](/umls-python-client-homepage/docs/search)

### 2. **CUI API**
Retrieve and work with **Concept Unique Identifiers (CUIs)**, which represent unique meanings and concepts in UMLS.

- **Features**:
  - Retrieve detailed CUI information like synonyms, relations, and hierarchical structures.
  - Compare CUIs and explore their relationships within the UMLS network.

[Learn more about CUI API](/umls-python-client-homepage/docs/cui)

### 3. **Source API**
Work with **source-asserted identifiers** and terminologies from popular healthcare systems like SNOMED-CT, RxNorm, and ICD-10.

- **Features**:
  - Retrieve attributes, relationships, and concept hierarchies from specific sources.
  - Explore how concepts are represented in multiple vocabularies.

[Learn more about Source API](/umls-python-client-homepage/docs/source)

### 4. **Semantic Network API**
Delve into the **UMLS Semantic Network** to explore semantic types and relationships between concepts.

- **Features**:
  - Query semantic types and relationships between medical concepts.
  - Use the semantic network to understand the classification of diseases, symptoms, and treatments.

[Learn more about Semantic Network API](/umls-python-client-homepage/docs/semantic-network)

### 5. **Crosswalk API**
Map concepts across different terminologies, making it easier to translate data from one healthcare system to another.

- **Features**:
  - Perform crosswalks between different coding systems like SNOMED-CT, ICD-10, and LOINC.
  - Ideal for data integration and healthcare interoperability.

[Learn more about Crosswalk API](/umls-python-client-homepage/docs/crosswalk)

---

## 🚀 Get Started Quickly

1. Install the UMLS Python Client:
   ```bash
   pip install umls-python-client
   ```

2. Initialize the client:
   ```python
   from umls_client import UMLSClient

   api_key = "your-umls-api-key"
   umls_client = UMLSClient(api_key)
   ```

3. Perform a search:
   ```python
   search_results = umls_client.searchAPI.search("diabetes")
   print(search_results)
   ```

For detailed examples and documentation, visit our [Getting Started Guide](/umls-python-client-homepage/docs).

---

## 🛠 Advanced Features

- **Family Tree Fetching**: Retrieve complete parent-child relationships for medical concepts.
- **Concept Pathways**: Explore hierarchical pathways for any UMLS concept.
- **Custom Query Parameters**: Tailor your API calls to return only the data you need, with filters for vocabularies, languages, and attributes.

---

## Contribute and Support

We welcome contributions from the community! Check out our [GitHub repository](https://github.com/palasht75/umls-client) to report issues, submit pull requests, or suggest new features.

Have questions or need help? Reach out via [GitHub Discussions](https://github.com/palasht75/umls-client/discussions) or open an [issue](https://github.com/palasht75/umls-client/issues).

---

## 📄 License

This project is licensed under the **Apache 2.0 License**.

Explore the [GitHub repository](https://github.com/palasht75/umls-client) for full details.

---

[Get Started](/umls-python-client-homepage/docs) | [About the Project](/umls-python-client-homepage/about)
