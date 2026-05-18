# Syllabus Citation Percentiles

**Live tool:** [ortutt.github.io/Syllabus_crcheck/](https://ortutt.github.io/Syllabus_crcheck/)

Syllabus Citation Percentiles is a web tool that takes a syllabus or reading list as input and returns the CrossRef citation percentile for every paper on it. Upload a PDF, Word, or text file; the tool extracts the citations, looks each one up against CrossRef, and ranks each paper against all articles in the same journal and year.

It is a companion tool to [Citation Compare](https://ortutt.github.io/citation-compare/), and uses the same journal-year percentile algorithm.

---

## What It Does

For any uploaded document, Syllabus Citation Percentiles:

- **Extracts candidate citations** from the file (PDF, DOCX, or TXT), based on year detection and structural heuristics
- **Lets you review and edit** the extracted list before processing
- **Matches each citation** against CrossRef using bibliographic search, restricted to journal articles
- **Computes a journal-year percentile** for each paper: where it ranks among all articles published in the same journal and year, by CrossRef citation count
- **Flags recent papers** (current year and previous year) as too recent to score
- **Flags likely mismatches** between the input citation and the CrossRef result, so they can be verified
- **Exports results** to XLSX with full metadata (citation, matched title and journal, DOI, citation count, percentile, corpus size, and median citations)

---

## Data Source

| Source | What it provides |
|---|---|
| [CrossRef](https://www.crossref.org) | Article metadata, citation count, journal/year percentile |

The CrossRef API is free and open. No API key is required. All processing happens client-side in the browser; the only data leaving your computer is the API calls to CrossRef.

---

## How to Use

1. Go to [ortutt.github.io/Syllabus_crcheck/](https://ortutt.github.io/Syllabus_crcheck/)
2. Upload a syllabus or reading list (`.pdf`, `.docx`, or `.txt`)
3. Review the extracted citations and edit if needed (remove headers, fix line breaks, add missed papers)
4. Click **Fetch percentiles**
5. Download the results as an XLSX file

Each row in the results table shows the matched CrossRef title underneath the input citation. Entries flagged with ⚠ may be wrong matches — if in doubt, look the paper up directly on [Citation Compare](https://ortutt.github.io/citation-compare/) to verify.

---

## Limitations

- Citation extraction is heuristic: it identifies lines that look like academic citations based on year, length, and structural cues. PDFs with multi-column layouts or tight line spacing may produce noisier extraction; the review step is the place to fix this.
- CrossRef bibliographic search returns the single best match; very short or ambiguous queries may match the wrong paper.
- Percentile calculations are restricted to articles indexed in CrossRef; journals with incomplete indexing may yield inaccurate percentiles.
- Papers published in the current year or the previous year are not scored, as too few citations have accumulated to be meaningful.
- The tool is designed for journal articles; books, chapters, and preprints will generally not match.

---

## How to Cite

If you use Syllabus Citation Percentiles in your research or reference it in academic work, please cite it as:

> Tuttnauer, O. (2026). *Syllabus Citation Percentiles* [Web application]. Retrieved from https://ortutt.github.io/Syllabus_crcheck/

Or in BibTeX:

```bibtex
@misc{tuttnauer2026citationpercentiles,
  author       = {Tuttnauer, Or},
  title        = {Citation Percentiles},
  year         = {2026},
  howpublished = {\url{https://ortutt.github.io/citation-percentiles/}},
  note         = {Web application}
}
```

---

## Author

Developed by [Or Tuttnauer](https://www.ortuttnauer.com), Postdoctoral Fellow at the Mannheim Centre for European Social Research (MZES), University of Mannheim, with assistance from Claude (Anthropic).
