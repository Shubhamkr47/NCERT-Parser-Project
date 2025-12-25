# NCERT Structured Data Extraction Pipeline

## Overview
This project is a robust data extraction pipeline designed to parse NCERT Class 10 Mathematics and Science textbooks into structured, machine-readable JSON formats. It handles complex PDF layouts, extracts hierarchical text (Book → Chapter → Section), and successfully recovers vector diagrams using a custom CMYK-to-RGB conversion engine.

##  Features
* **Hierarchy Preservation:** accurately maps content to chapters and sub-sections.
* **Robust Image Extraction:** Custom middleware handles "Print-Ready" CMYK PDFs, preventing data loss for over 1000+ diagrams.
* **Structured Output:** Delivers clean JSON with classified content blocks (Text, Tables).

##  Dependencies
* `pdfplumber`: For high-fidelity text and table extraction.
* `pymupdf` (fitz): For object-level image extraction and color-space conversion.

## ⚙️ How to Run
1.  **Install Requirements:**
    ```bash
    pip install pdfplumber pymupdf
    ```
2.  **Run the Pipeline:**
    Execute the `NCERT_Parser.ipynb` notebook.
3.  **Output:**
    Results will be generated in the `Output_Data/` directory, organized by subject and chapter.

## 📂 Output Structure
```json
{
    "book": "Science",
    "chapter": "ch1",
    "sections": [
        {
            "section_title": "Introduction",
            "content_blocks": [
                { "type": "paragraph_text", "content": "..." },
                { "type": "table", "content": [...] }
            ]
        }
    ]
}
