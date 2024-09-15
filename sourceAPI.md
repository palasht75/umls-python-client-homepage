---
layout: default
title: "SourceAPI Usage Guide"
---

# SourceAPI Usage Guide

The `SourceAPI` in the `UMLS Python Client` provides a comprehensive set of methods for interacting with UMLS source-asserted identifiers. This guide will showcase how to use various functionalities provided by the `SourceAPI` class in a detailed manner.

## Prerequisites

Before using the API, ensure you have your API key to interact with the UMLS database. If you don't have an API key, you can get one from [User Authentication](https://documentation.uts.nlm.nih.gov/rest/authentication.html).

If you wish to run it right away, please follow this [Colab Notebook](https://colab.research.google.com/drive/1ICQFoZqfsW6YvcaoRo-DtZR2QAWmqFI0?usp=sharing).

## Setting Up

Here is how to set up the `SourceAPI` class:

```python
import os
from umls_python_client import UMLSClient

# Set the API KEY
API_KEY = "API_KEY_HERE"

# Folder path to save files
PATH = r"C:\path\to\your\output\directory"

# Initialize the SourceAPI class with your API key
source_api = UMLSClient(api_key=API_KEY).sourceAPI
```
Make sure to replace `C:\path\to\your\output\directory` with the path where you want to save the output files.

## Additional Arguments

- **`format`**: This argument determines the output format of the response. It accepts "json" or "rdf". Note that "rdf" will only work with native APIs and will not be applicable to additional utility functions.
- **`return_indented`**: A boolean flag to return the JSON output in an indented and human-readable form.
- **`save_to_file`**: When set to `True`, saves the API response to a specified file path.
- **`file_path`**: Path to the file where you want to save the output. Make sure this path is correct when `save_to_file` is `True`.

## Use Cases

### 1. Retrieve Source Concept Information

This functionality allows you to retrieve detailed information about a concept using its source and ID.

```python
# Specify the source (e.g., SNOMEDCT_US) and a concept ID
source = "SNOMEDCT_US"
source_id = "9468002"  # Example concept ID

# Retrieve Source Concept Information
concept_info = source_api.get_source_concept(
    source, source_id, return_indented=True, save_to_file=True, file_path=PATH
)
print(concept_info)
```
This code will fetch the concept's information and save it to a file in the specified directory.

### 2. Retrieve Atoms for a Source-Asserted Identifier

This method fetches atoms associated with the specified source and ID, including various filters.

```python
# Retrieve Atoms
atoms = source_api.get_source_atoms(
    source,
    source_id,
    sabs="SNOMEDCT_US",
    ttys="PT",
    language="ENG",
    include_obsolete=True,
    include_suppressible=False,
    page_number=1,
    page_size=10,
    format="rdf",
)
print(atoms)
```

### 3. Retrieve Immediate Parents for a Source-Asserted Identifier

Get the immediate parent concepts for the specified source and ID.

```python
# Retrieve Immediate Parents
parents = source_api.get_source_parents(
    source, source_id, format="rdf", save_to_file=True, file_path=PATH
)
print(parents)
```

### 4. Retrieve Immediate Children for a Source-Asserted Identifier

This retrieves the child concepts for the specified source and ID.

```python
# Retrieve Immediate Children
children = source_api.get_source_children(
    source, source_id, format="rdf", save_to_file=True, file_path=PATH
)
print(children)
```

### 5. Retrieve Ancestors for a Source-Asserted Identifier

Fetch all ancestors of a concept.

```python
# Retrieve Ancestors
ancestors = source_api.get_source_ancestors(
    source, source_id, save_to_file=True, file_path=PATH
)
print(ancestors)
```

### 6. Retrieve Descendants for a Source-Asserted Identifier

Get all descendants for the specified source and ID.

```python
# Retrieve Descendants
descendants = source_api.get_source_descendants(
    source, source_id, save_to_file=True, file_path=PATH
)
print(descendants)
```

### 7. Retrieve Attributes for a Source-Asserted Identifier

Fetch additional attributes for a specific source concept.

```python
# Retrieve Attributes
attributes = source_api.get_source_attributes(
    source, source_id, save_to_file=True, file_path=PATH
)
print(attributes)
```

### 8. Fetch Source Relations with Custom Parameters

Get the relations between the specified source and ID, allowing for custom parameters.

```python
# Fetch Source Relations
relations = source_api.get_source_relations(
    source,
    source_id,
    include_relation_labels=None,
    include_obsolete=False,
    include_suppressible=False,
    page_number=1,
    page_size=10,
    save_to_file=True,
    file_path=PATH
)
print(relations)
```

### 9. Retrieve Family Tree (Parent-Child Relationships)

Get the complete family tree of a concept (parents and children) up to a specified depth.

```python
# Retrieve Family Tree
family_tree = source_api.get_family_tree(
    source, source_id, max_depth=3, return_indented=True, save_to_file=True, file_path=PATH
)
print(family_tree)
```

### 10. Fetch Concept Pathways (Parent-Child Pathways)

Fetch pathways for the concept, which shows parent-child relationships.

```python
# Fetch Concept Pathways
pathways = source_api.get_concept_pathways(
    source, source_id, max_depth=0, return_indented=True, save_to_file=True, file_path=PATH
)
print(pathways)
```

### 11. Fetch Related Concepts Based on Relationship Type

Retrieve concepts that are related based on a specified relationship type (e.g., "RB" for broader relationships).

```python
# Fetch Related Concepts
relation_type = "RB"  # Broader relationship
related_concepts = source_api.get_related_concepts_by_relation_type(
    source, source_id, relation_type, return_indented=True, save_to_file=True, file_path=PATH
)
print(related_concepts)
```

### 12. Compare Two Concepts

Compare two concepts to explore their similarities or differences.

```python
# Compare Two Concepts
comparison = source_api.compare_concepts(
    source, id1=source_id, id2="9468003", return_indented=True, save_to_file=True, file_path=PATH
)
print(comparison)
```

### 13. Get Concept Coverage Across Medical Systems

Determine the coverage of the concept across different medical systems.

```python
# Get Concept Coverage
coverage = source_api.get_concept_coverage(
    source, source_id, return_indented=True, save_to_file=True, file_path=PATH
)
print(coverage)
```

### 14. Aggregate Children by Attribute

Aggregate the child concepts based on a specified attribute.

```python
# Aggregate Children by Attribute
aggregated_children = source_api.aggregate_children_by_attribute(
    source, source_id, "CTV3ID", return_indented=True, save_to_file=True, file_path=PATH
)
print(aggregated_children)
```

### 15. Retrieve Full Hierarchy Recursively

Fetch the complete parent-child hierarchy recursively up to a specified depth.

```python
# Retrieve Full Hierarchy Recursively
full_hierarchy = source_api.get_full_hierarchy_recursive(
    source,
    source_id,
    depth=1,
    return_indented=True,
    save_to_file=True,
    file_path=PATH
)
print(full_hierarchy)
```

> **Note**: The `"rdf"` format is only supported for native UMLS APIs and not for additional utility functions.
