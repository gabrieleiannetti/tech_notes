# PDF

## pdfly

CLI tool for PDF processing.

**Install:** `pip3 install pdfly`

**Usage:**

```
➜  ~ pdfly --help
                                                                                     
 Usage: pdfly [OPTIONS] COMMAND [ARGS]...
                                                          
 pdfly is a pure-python cli application for manipulating PDF files.

╭─ Options ─────────────────────────────────────────────────────────────────────╮
│ --version                                                                     │
│ --help             Show this message and exit.                                │
╰───────────────────────────────────────────────────────────────────────────────╯
╭─ Commands ────────────────────────────────────────────────────────────────────╮
│ extract-images   Extract images from PDF without resampling or altering.      │
│ 2-up             Create a booklet-style PDF from a single input.              │
│ cat              Concatenate pages from PDF files into a single PDF file.     │
│ meta             Show metadata of a PDF file                                  │
│ pagemeta         Give details about a single page.                            │
│ extract-text     Extract text from a PDF file.                                │
│ compress         Compress a PDF.                                              │
│ x2pdf            Convert one or more files to PDF. Each file is a page.       │
╰───────────────────────────────────────────────────────────────────────────────╯
```
