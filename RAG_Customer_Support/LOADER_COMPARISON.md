# PDF Loader Comparison & Test Notebooks

## Best loader by use case

| Use case | Best loader | Why |
|----------|-------------|-----|
| **Research papers** (diagrams, images, tables) | **PyMuPDF4LLM** | Converts to Markdown with correct reading order; detects **tables** (in page text + bbox metadata), **images/graphics** per page; rich metadata (`source`, `page_number`, `page_count`, `toc_items`). UnstructuredPDFLoader often misses tables/figures in dense papers. |
| **Manuals** (clean text + tables from `./Manuals`) | **pdfplumber** | Accurate text (e.g. via `extract_words()` for spacing), excellent **table** extraction with `extract_tables()`. |

## Other loaders (short)

- **PyPDFLoader** – Simple text only; no table/image extraction.
- **PyMuPDFLoader** – Fast text + can extract images; less element-level structure than Unstructured.
- **PyMuPDF4LLM** – Markdown output, table/image refs; good for RAG, less granular than Unstructured for element types.
- **PyPDFMinerLoader** – Text with layout; no native table/image extraction.

## Test notebooks

1. **`test_loader_research_papers.ipynb`**  
   - Loader: **UnstructuredPDFLoader** (mode=`"elements"`).  
   - Path: `./ResearchPapers` if it has PDFs, else `./input_docs`.  
   - Shows: element types, sample text/tables/images.

2. **`test_loader_manuals.ipynb`**  
   - Loader: **pdfplumber**.  
   - Path: `./Manuals` (falls back to `./input_docs` if empty).  
   - Shows: first 2 pages text, all tables in first 2 pages.

## How to run

- Put research PDFs in `./ResearchPapers` (or use existing `./input_docs`).
- Put manual PDFs in `./Manuals` (or use `./input_docs` for the test).
- Open each notebook and run all cells (install cell may take a minute for `unstructured[all-docs]`).
