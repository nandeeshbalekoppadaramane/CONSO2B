# CONSO2B

A Streamlit tool that consolidates GSTR-2B data from multiple files into one clean dataset, with smart header detection and flexible export.

Useful when you have monthly or quarterly GSTR-2B downloads (from the GST portal or offline tool) spread across several Excel/CSV files and need a single consolidated sheet for review or further work.

## How it works

1. **Upload files** - one or more GSTR-2B files, uploaded in the order you want them consolidated.
2. **Select sheets** - the app lists every sheet found across the uploaded files; pick the ones that hold the data.
3. **Consolidate & export** - combine everything and download the result.

## Features

- **Smart header detection** - locates the real header row by searching for "GSTIN of supplier", handles two-row headers, sanitizes and de-duplicates column names.
- **Multi-file processing** - reads Excel (`.xls`, `.xlsx`, `.xlsm`, `.xlsb`) and CSV (`.csv`) files.
- **Data cleaning** - trims values, fills blanks, and keeps a processing activity log.
- **Flexible export** - download as Excel, either split into one worksheet per source sheet (default) or combined into a single sheet, or as CSV.
- **Live status** - sidebar shows files loaded, sheets available/selected, and total consolidated rows.

## Requirements

```bash
pip install -r requirements.txt
```

Dependencies: `streamlit`, `pandas`, `numpy`, `openpyxl`, `xlrd`, `pyxlsb`.

## Run

```bash
streamlit run CONSO2B.py
```

Then open the local URL Streamlit prints (default `http://localhost:8501`).

## Files

| File | Purpose |
|---|---|
| `CONSO2B.py` | The complete application (UI, parsing, consolidation, export) |
| `requirements.txt` | Python dependencies |

## Notes

- Files are processed in upload order.
- When run locally, uploads are processed by the local Streamlit server. A hosted deployment processes uploads on its host.
- Personal project.
