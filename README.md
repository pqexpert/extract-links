🔗 hyperlink-extractor-jda

[![PyPI version]( https://badge.fury.io/py/hyperlink-extractor-jda.svg )]( https://pypi.org/project/hyperlink-extractor-jda/ )

**hyperlink-extractor-jda** is a command-line tool for extracting **text-label + hyperlink pairs** from `.docx`, `.odt`, `.html`, and `.pdf` files.

✨ Supports Windows, Linux, macOS  
✨ Outputs: `txt`, `csv`, `md`, `json`, `xlsx`  
✨ Optional deduplication & sorting  
✨ `.exe` available for Windows users — no Python required

---

📥 Install

From PyPI:
bash

pip install hyperlink-extractor-jda

From Source
Clone the repo and install:

bash

git clone https://github.com/pqexpert/extract-links.git
cd extract-links
pip install .

Or run the CLI directly from source:
bash

python -m extract_links.cli [input_file]

🚀 Usage
CLI example:
bash

hyperlink-extractor-jda input.docx -o output --format csv --dedupe --sort

Arguments:
| Flag       | Description                                   |
| ---------- | --------------------------------------------- |
| `input`    | Input file (`.docx`, `.odt`, `.html`, `.pdf`) |
| `-o`       | Output file prefix (without extension)        |
| `--format` | `txt`, `csv`, `md`, `json`, `xlsx`            |
| `--dedupe` | Deduplicate URLs                              |
| `--sort`   | Sort by label                                 |

📋 Output Example
CSV
Text,URL
Project Plan,https://example.com/plan
Resources,https://example.com/resources

Markdown
[Project Plan](https://example.com/plan)
[Resources](https://example.com/resources)

📚 Supported Formats
.docx → via python-docx

.odt → via odfpy

.html → via BeautifulSoup

.pdf → via PyMuPDF (bounding box + OCR-style matching)

🖥️ Windows Standalone .exe
For Windows users without Python, download the .exe from the GitHub Releases page. https://github.com/pqexpert/extract-links/releases 

Powershell Example:

extract-links.exe project_plan.docx -o output_links --format csv

Notes for .exe usage:
✅ Place extract-links.exe in the same folder as your input file, or
✅ Provide the full path to your input file when running

📦 Project Links
🔗 PyPI https://pypi.org/project/hyperlink-extractor-jda/
💻 GitHub https://github.com/pqexpert/extract-links

📜 License
MIT License

Built with ❤️ by pqexpert https://github.com/pqexpert ✨
