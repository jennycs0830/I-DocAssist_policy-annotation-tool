# Policy Annotation Tool

A web-based annotation tool for extracting and structuring medical insurance policy requirements.

## Features

- **Stage 1: Section Extraction** - Extract requirement sections from policy documents and classify them as General, Supplementary, or Exception
- **Stage 2: Atomic Breakdown** - Break down sections into logical tree structures with operators (ALL, ANY, NOT, IF, UNLESS)
- **Stage 3: CPT Mapping** - Map CPT/HCPCS codes to their relevant requirement sections

## For Annotators

1. Open the tool in your browser
2. Enter the document title you're annotating
3. Complete each stage sequentially
4. Click "Export JSON" when finished
5. Send the downloaded JSON file to the project lead

## Export Format

The exported JSON follows this schema:

```json
{
  "document_title": "Aetna CPB 0001",
  "sections": {
    "general": [{ "id": "g001", "text": "..." }],
    "supplementary": [{ "id": "s001", "text": "..." }],
    "exception": [{ "id": "e001", "text": "..." }]
  },
  "logic_trees": {
    "g001": {
      "type": "ALL",
      "children": [...]
    }
  },
  "cpt_mappings": {
    "27447": {
      "general": ["g001"],
      "supplementary": ["s001"],
      "exception": []
    }
  }
}
```
