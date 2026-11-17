# Lower Saxony, Bückeburg Archive, Documents (Jupyter Book 2)

Jupyter Book 2 (MyST) version of the
[sphinx-nla](https://github.com/kurt-krueckeberg/sphinx-nla) Jupyter Book 1 project:
transliterations and translations of Schaumburg-Lippe Rentkammer case files
from the Bückeburg branch of the Lower Saxony state archive.

All configuration, including the table of contents and the PDF export, is in `myst.yml`.
Tables with cells spanning rows or columns use the `flat-table` directive,
provided by the plugin `flat-table.mjs`.

## Requirements

- MyST, installed in a Python virtual environment:

  ```bash
  python3 -m venv .venv
  source .venv/bin/activate
  pip install mystmd
  ```

- Node.js 18 or later: `sudo dnf install nodejs`
- Typst, for the PDF: `sudo dnf install typst`

## Build

With the virtual environment active:

```bash
myst start          # serve the site as a MyST application (http://localhost:3000)
myst build --html   # static HTML in _build/html
myst build --pdf    # Typst PDF in exports/book.pdf
```

To view the static HTML locally:

```bash
python3 -m http.server 8000 -d _build/html   # then open http://localhost:8000
```
