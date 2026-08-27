# Hyperlink Extractor

**Turn document hyperlinks into clean, portable data.**

`hyperlink-extractor-jda` is a small cross-platform command-line tool that extracts **link text + URL pairs** from common document formats and exports them into formats that are easier to audit, transform, cite, or feed into another workflow.

It supports `.docx`, `.odt`, `.html`, and `.pdf` inputs, with output to `txt`, `csv`, `md`, `json`, or `xlsx`.

[![PyPI version](https://badge.fury.io/py/hyperlink-extractor-jda.svg)](https://pypi.org/project/hyperlink-extractor-jda/)

## Why I built it

A surprising amount of research and document work ends with the same tedious task: *give me the links, preserve their labels, and put them into something I can inspect.*

This utility is intentionally narrow. It does one job, works locally, and produces structured output that can be checked before it becomes part of a larger research or automation pipeline.

## Install

From PyPI:

```bash
pip install hyperlink-extractor-jda
```

From source:

```bash
git clone https://github.com/pqexpert/extract-links.git
cd extract-links
pip install .
```

Or run the CLI directly from the source tree:

```bash
python -m extract_links.cli input.docx
```

## Example

```bash
hyperlink-extractor-jda input.docx -o output --format csv --dedupe --sort
```

| Flag | Purpose |
| --- | --- |
| `input` | Source file: `.docx`, `.odt`, `.html`, or `.pdf` |
| `-o` | Output filename prefix |
| `--format` | `txt`, `csv`, `md`, `json`, or `xlsx` |
| `--dedupe` | Remove duplicate URLs |
| `--sort` | Sort results by link label |

Example CSV output:

```csv
Text,URL
Project Plan,https://example.com/plan
Resources,https://example.com/resources
```

Example Markdown output:

```md
[Project Plan](https://example.com/plan)
[Resources](https://example.com/resources)
```

## Format support

- `.docx` — `python-docx`
- `.odt` — `odfpy`
- `.html` — Beautiful Soup
- `.pdf` — PyMuPDF-based extraction and matching

## Windows standalone build

A Windows executable is available from the repository’s [Releases](https://github.com/pqexpert/extract-links/releases) page for users who do not want to install Python.

Typical use:

```powershell
extract-links.exe project_plan.docx -o output_links --format csv
```

## Operating assumptions

- Input documents are processed locally by the tool; the project does not require a hosted extraction service.
- Document parsers can encounter malformed or unusual files, so important results should still be reviewed before downstream use.
- PDF link extraction is inherently less uniform than extracting links from structured document formats; treat edge cases as data-quality problems, not invisible certainty.

## Project links

- [PyPI package](https://pypi.org/project/hyperlink-extractor-jda/)
- [GitHub repository](https://github.com/pqexpert/extract-links)
- [PQExpert.io](https://pqexpert.io/) — broader technical and professional portfolio

## License

MIT License.

Built by **pqexpert / Josh Allen** as a practical document-processing utility: small surface area, inspectable output, and no ceremony beyond what the problem requires.
